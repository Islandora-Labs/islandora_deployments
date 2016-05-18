# [University of Tennessee Libraries, Digital Library](http://digital.lib.utk.edu/collections)

## Overview:

The Islandora repo, "digital", is deployed on a Dell PowerEdge 715 rack mount server.

* Red Hat Enterprise Linux 7.1 x64
* 24 cores
* 64G RAM
* 4TB RAID

A similar test server has the same versions of software.

There is also a "ingest client" server that was installed using the scripts
from these parts of the vagrant install scripts to allow ingests to the main fedora.

* Ubuntu
* Drupal
* Djatoka ( for kdu_compress)
* ImageMagick
* Tesseract
* FFMpeg and lame
* FITS


## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.4.6-31
* Drupal: 7.39
* ffmpeg: git-2015-01-27-3c831fb
* FITS: 0.8.5
* Islandora: HEAD
* Java: 1.7 (Oracle)
* jQuery: 
* jQuery UI: 
* Fedora: 3.7.1
* Fedora GSearch: 2.7
* MariaDB: 5.5.44
* Solr: 4.2.0
* Tesseract: 3.02.02
* Tomcat: 6.0.35
 

## Settings:

* ffmpeg:  --enable-gpl --enable-nonfree --enable-libmp3lame --enable-libvorbis --enable-libvpx --enable-libx264
* JAVA_OPTS= -server -Xmx4096m -Xms4096m
 -XX:MaxPermSize=1024m
 -XX:+UseParNewGC
 -XX:+UseConcMarkSweepGC
 -XX:+CMSClassUnloadingEnabled
 -Djavax.net.ssl.trustStore=/vhosts/fedora/server/truststore
 -Djavax.net.ssl.trustStorePassword=tomcat
 -Djava.awt.headless=true
 -Dkakadu.home=/opt/adore-djatoka/bin/Linux-x86-64
 -Djava.library.path=/opt/adore-djatoka/lib/Linux-x86-64
 -DLD_LIBRARY_PATH=/opt/adore-djatoka/lib/Linux-x86-64
 
* PHP memory limit: 4096M
* Tesseract 3.02.02 : leptonica-1.71  libjpeg 6b : libpng 1.5.13 : libtiff 4.0.3 : zlib 1.2.7 : libwebp 0.3.0

## Fedora XACML policies:
```
repository-policies
.
├── default
│   ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
│   ├── deny-policy-management-if-not-administrator.xml
│   ├── deny-reloadPolicies-if-not-localhost.xml
│   ├── deny-unallowed-file-resolution.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   └── readme.txt
└── islandora
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    └── permit-upload-to-authenticated-user.xml
```

## Drupal Modules:

* colorbox
* ctools
* date
* datepicker
* devel
* entity
* imagemagick
* islandora
* islandora_batch
* islandora_batch_derivative_trigger
* islandora_binary_object
* islandora_book_batch
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_collection_search
* islandora_datastream_exporter-7.x
* islandora_datastream_replace
* islandora_fits
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_oai
* islandora_ocr
* islandora_openseadragon
* islandora_paged_content
* islandora_paged_tei_seadragon
* islandora_patches
* islandora_pdfjs
* islandora_premis
* islandora_rest
* islandora_solr_metadata
* islandora_solr_search
* islandora_solr_views
* islandora_solution_pack_audio
* islandora_solution_pack_book
* islandora_solution_pack_collection
* islandora_solution_pack_compound
* islandora_solution_pack_image
* islandora_solution_pack_large_image
* islandora_solution_pack_manuscript
* islandora_solution_pack_newspaper
* islandora_solution_pack_pdf
* islandora_solution_pack_video
* islandora_usage_stats
* islandora_videojs
* islandora_xacml_editor
* islandora_xml_forms
* jquery_update
* libraries
* nagios
* objective_forms
* php_lib
* piwik
* rules
* securelogin
* simple_ldap
* views
* views_data_export

## Drupal Libraries:

* bookreader
* colorbox
* flexslider
* JAIL
* jquery
* jquery.cycle
* jstree
* jwplayer
* openseadragon
* pdfjs
* superfish
* tuque
* utk
* video-js

