# [Atkins Library, UNC Charlotte](http://goldmine.uncc.edu)

## Overview:

[System Schematic](UNC_Charlotte.pdf)

UNC Charlotte is deployed on two AWS EC2 servers configured in a master/slave model.

Fedora's datastreamStore is mounted on AWS S3 using [YAS3FS](https://github.com/danilop/yas3fs), which also leverages a SSD-based temporary drive for OS-level caching.  "Goldmine.uncc.edu", our public-facing server, mounts the same S3-based Fedora datastreamStore read-only.

[Islandora BagIT](https://github.com/Islandora/islandora_bagit) is configured to "Create Bag on object ingest", which results in a zipped bag being created for 100% of objects ingested.  Zipped bags are swept nightly into AWS Glacier using [mt-aws-glacier](https://github.com/vsespb/mt-aws-glacier).  Islandora BagIT is also configured to "Create bag on object modification", which generates a fresh bag when metadata is updated.  mt-aws-glacier is configured to sweep the freshened bag into AWS Glacier and remove the previous version of the bag it is replacing on success.

Servers share a centralized AWS RDS MySQL instance, however "Island1" is mounted read/write while the public-facing "Goldmine.uncc.edu" utilizes an effectively read-only replication of the data.

# Servers

## Linux 3.2.0-4-amd64 #1 SMP Debian 3.2.63-2+deb7u1 x86_64 GNU/Linux
* AWS EC2 "m3.2xlarge"
* 8 vCPU
* 30GiB RAM
* AWS EBS (SSDs) for OS, "Islandora Loading Dock", temp, documentroot, Fedora objectStore, and SOLR index


## Tomcat webapps:

* Fedora
* Fedora GSearch
* Apache SOLR using the best schemas and transforms from both [discoverygarden/basic-solr-config](https://github.com/discoverygarden/basic-solr-config) and [yorkulibraries/basic-solr-config](https://github.com/yorkulibraries/basic-solr-config), which contains [TECHMD indexing](https://github.com/yorkulibraries/basic-solr-config/blob/kappa/islandora_transforms/slurp_all_FITS_to_solr.xslt)
* Adore-Djatoka

## Settings:

* Brad's Rule="50% of physical RAM to JVM"
* JAVA_OPTS="-Xloggc:/var/log/islandora/java/java_gc.log -XX:+PrintGCDetails -XX:+PrintGCTimeStamps -XX:ErrorFile=/var/log/islandora/java/java_error%p.log -Xms15g -Xmx15g -XX:MaxPermSize=1g -XX:+DisableExplicitGC -XX:+UseParallelGC -XX:+UseParallelOldGC"
* Parallel garbage collector provides **one thread of garbage collection per processor**, our server has eight (8), resulting in very high throughput, which is required for big data object ingests.  The _single-threaded_ CMS collector was incapable of bailing out the "old generation" memory space fast enough, resulting in Tomcat out of memory errors and total failure... 
* PHP CLI memory limit: -1
