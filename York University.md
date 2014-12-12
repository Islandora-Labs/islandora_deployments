# [York University Digital Library](https://digital.library.yorku.ca)

## Overview:

YUDL is deployed on a single bare metal machine, and the Fedora data directory is symlinked to a 7T NFS mount.

* Ubuntu 14.04.01 LTS x64
* 8 CPUs
* 64G RAM

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Open Wayback
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.4.7 
* Drupal: 7.35
* ffmpeg: 1.1.4
* FITS: 0.8.0
* Islandora: HEAD
* Java: 1.7 (Oracle)
* jQuery: 1.10.
* jQuery UI: 1.10.2
* Fedora: 3.8.0
* Fedora GSearch: HEAD
* MySQL: 5.5.40-0ubuntu0.14.04.1
* Open Wayback: 2.0.0.BETA.2
* Solr: 4.2.0
* Tesseract: 3.2.02
* Tomcat: 7

## Settings:

* ffmpeg: --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS="$DEBUG -Djava.awt.headless=true -Xmx30g -Xms10g -XX:MaxPermSize=512M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=8 -Dkakadu.home=$KAKADU_HOME -Djava.library.path=$LIBPATH/$PLATFORM $KAKADU_LIBRARY_PATH"
* PHP memory limit: 8192M
* Tesseract : leptonica-1.70 libgif 4.1.6(?) : libjpeg 8d : libpng 1.2.50 : libtiff 4.0.3 : zlib 1.2.8 : webp 0.4.0

## Fedora XACML policies:

```
repository-policies
├── default
│   ├── deny-reloadPolicies-if-not-localhost.xml
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

* advanced_help
* chart
* chosen
* coder
* colorbox
* ctools
* devel
* entity
* features
* fontawesome
* geofield
* geophp
* git_deploy
* google_analytics
* i18n
* icon
* imagemagick
* islandora
* islandora_batch
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_fits
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_marcxml
* islandora_oai
* islandora_object_lock
* islandora_ocr
* islandora_openseadragon
* islandora_paged_content
* islandora_pathauto
* islandora_plupload
* islandora_premis
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
* islandora_solution_pack_newspaper
* islandora_solution_pack_pdf
* islandora_solution_pack_video
* islandora_solution_pack_web_archive
* islandora_videojs
* islandora_xacml_editor
* islandora_xml_forms
* islandora_xmlsitemap
* islandora_xquery
* jquery_update
* ldap
* leaflet
* libraries
* markdown
* mollom
* nagios
* oauth
* objective_forms
* pathauto
* php_lib
* plupload
* redirect
* remove_generator
* schemaorg
* securelogin
* site_verify
* smart_ip
* smtp
* subpathauto
* superfish
* tabtamer
* token
* variable
* views
* views_infinite_scroll
* views_slideshow
* webform
* xmlsitemap
