# [Colorado Alliance of Research Libraries] (http://www.coalliance.org)

## Description
The Colorado Alliance of Research Libraries has hosted a consortial multisite Islandora 7 with sites in production since 2014. 

## Member Sites using Islandora 7
* [Digital UW - University of Wyoming] (http://uwyo.coalliance.org)
* [Digital UNC - University of Northern Colorado) (http://digitalunc.coalliance.org)

## Overview:

The multisite Islandora is split across two virtual servers, the Fedora VM and the Drupal VM.

## Fedora VM

* Ubuntu 12.04.04 LTS x64
* 8 CPUs
* 32 GB RAM
* 80 GB OS Drive
* 12 TB NFS-mounted SAN
* 1 TB staging storage for ingest (NFS-mounted SAN)

### Tomcat webapps

* Adore-djatoka
* Fedora
* FedoraGSearch
* Saxon
* Solr

### Software versions

* Apache 2.2
* Fedora 3.7.1
* FedoraGSearch 2.6
* Solr 3.6.2

### Settings

Java(TM) SE Runtime Environment (build 1.7.0_51)

* CATALINA_HOME=/opt/tomcat
* FEDORA_HOME=/opt/fedora
* JAVA_OPTS="-Xms1024m -Xmx22000m -XX:MaxPermSize=512m -XX:+CMSClassUnloadingEnabled -Djavax.net.ssl.trustStore=/opt/fedora/server/truststore -Djavax.net.ssl.trustStorePassword=tomcat -Dsolr.solr.home=/opt/solr"

### Fedora XACML policies

CODEBLOCK

repository-policies
├── default
│   ├── deny-reloadPolicies-if-not-localhost.xml
│   ├── deny-unallowed-file-resolution.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   └── readme.txt
└── islandora
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    └── permit-upload-to-authenticated-user.xml

## Drupal VM

* Ubuntu 12.04.04 LTS x64
* 8 CPUs
* 20 GB RAM
* 80 GB OS Drive

### Software versions

* Apache 2.2
* Drupal 7.35 
* Islandora 7.x-1.4
* ffmpeg 1.1.1

### Settings

* PHP memory limit: 512M
* ffmpeg: --enable-gpl --enable-libass --enable-libfaac --enable-libfdk-aac --enable-libmp3lame --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-librtmp --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-nonfree --enable-version3 --enable-libopus
* Tesseract: tesseract 3.02.02 leptonica-1.69  libjpeg 8b : libpng 1.2.46 : libtiff 3.9.5 : zlib 1.2.3.4

### Drupal Modules (in GitHub)

[Modules shared by all sites in the multisite Drupal] (https://github.com/co-alliance/adr)

[Modules installed only in UWYO] (https://github.com/co-alliance/uwyo)

[Modules installed only in UNC] (https://github.com/co-alliance/digitalunc)

## Development servers

We also have a 2-server development setup that is part of our deployment workflow.

### Development Fedora VM

* Ubuntu 12.04.05 LTS x64
* 6 CPUs
* 20 GB RAM
* 280 GB storage (OS + Fedora data)

### Development Drupal VM

* Ubuntu 12.04.05 LTS x64
* 4 CPUs
* 8 GB RAM
* 280 GB OS drive

### Continuous integration (for development sites from github repos)

* Jenkins
* Capistrano



