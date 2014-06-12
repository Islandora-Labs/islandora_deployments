# [York University Digital Library](https://digital.library.yorku.ca)

## Overview:

YUDL is deployed on a single virtual machine, and the Fedora data directory is deployed to a 2T NFS mount.

* Ubuntu 12.04.02 LTS x64
* 4 CPUs
* 24G RAM

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Open Wayback
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.22 
* Drupal: 7.28
* ffmpeg: 1.1.4
* FITS: 0.8.0
* Java: 1.7 (Oracle)
* jQuery: 1.8.2
* jQuery UI: 1.10.2
* Fedora: 3.6.2
* Fedora GSearch: 2.6
* MySQL: 5.5.29-0ubuntu0.12.04.2
* Open Wayback: 2.0.0.BETA.2
* Solr: 4.2.0
* Tesseract: 3.2.02

## Settings:

* ffmpeg: --prefix=/usr/local/stow/ffmpeg-1.1.4 --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS:"$DEBUG -Djava.awt.headless=true -Xms12288M -Xmx12288M -XX:MaxPermSize=512M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=4 -Dkakadu.home=$KAKADU_HOME -Djava.library.path=$LIBPATH/$PLATFORM $KAKADU_LIBRARY_PATH"
* PHP memory limit: 8192M
* Tesseract:  leptonica-1.69 libgif 4.1.6 : libjpeg 8b : libpng 1.2.46 : libtiff 3.9.5 : zlib 1.2.3.4

## Drupal Modules:

* advanced_help
* chart
* chosen
* coder
* ctools
* devel
* entity
* fontawesome
* git_deploy
* google_analytics
* i18n
* icon
* imagemagick
* islandora
* islandora_accordion_rotator_module
* islandora_bagit
* islandora_batch
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_featured_collection
* islandora_fits
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_marcxml
* islandora_ntriples
* islandora_oai
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
* islandora_stats
* islandora_videojs
* islandora_xacml_editor
* islandora_xml_forms
* islandora_xmlsitemap
* jquery_update
* ldap
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
* token
* variable
* views
* views_infinite_scroll
* webform
* xmlsitemap
