# [University of Tennessee Libraries, Digital Library](http://digital.lib.utk.edu/collections)

## Overview:

The Islandora repo, "digital", is deployed on a Dell PowerEdge 715 rack mount server.

* Red Hat Enterprise Linux 7.1 x64
* 24 cores
* 64G RAM
* 4TB RAID

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.4.6-31
* Drupal: 7.35
* ffmpeg: git-2015-01-27-3c831fb
* FITS: 0.8.5
* Islandora: 7.x-1.4
* Java: 1.7 (Oracle)
* jQuery: 
* jQuery UI: 
* Fedora: 3.7.1
* Fedora GSearch: 2.7
* MariaDB: 5.5.41
* Solr: 4.2.0
* Tesseract: 3.02.02
* Tomcat: 6.0.35
 

## Settings:

* ffmpeg:  --enable-gpl --enable-nonfree --enable-libmp3lame --enable-libvorbis --enable-libvpx --enable-libx264
* JAVA_OPTS= -server -Xmx4096m -Xms4096m
 -XX:MaxPermSize=512m
 -XX:+CMSClassUnloadingEnabled
 -Djavax.net.ssl.trustStore=/vhosts/fedora/server/truststore
 -Djavax.net.ssl.trustStorePassword=tomcat
 -Djava.awt.headless=true
 -Dkakadu.home=/opt/adore-djatoka/bin/Linux-x86-64
 -Djava.library.path=/opt/adore-djatoka/lib/Linux-x86-64
 -DLD_LIBRARY_PATH=/opt/adore-djatoka/lib/Linux-x86-64
 
* PHP memory limit: 4096M
* Tesseract 3.03 : leptonica-1.71  libjpeg 6b : libpng 1.5.13 : libtiff 4.0.3 : zlib 1.2.7 : libwebp 0.3.0

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

* collection_sort
* colorbox
* ctools
* imagemagick
* islandora
* islandora_batch
* islandora_binary_object
* islandora_book_batch
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_collection_search
* islandora_collection_sort
* islandora_fits
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_oai
* islandora_ocr
* islandora_openseadragon
* islandora_paged_content
* islandora_paged_tei_seadragon
* islandora_pdfjs
* islandora_premis
* islandora_rest
* islandora_solr_facet_pages
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
* islandora_videojs
* islandora_xacml_editor
* islandora_xml_forms
* libraries
* objective_forms
* php_lib
* piwik
* simple_ldap
* views

## Drupal Libraries:

* bookreader
* colorbox
* flexslider
* JAIL
* jquery
* jquery.cycle
* jstree 3.1.1
* jwplayer
* openseadragon 1.1.1
* pdfjs 0.8.0
* superfish
* tuque
* utk
* video-js

