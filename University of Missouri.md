# [University of Missouri System](https://dl.mospace.umsystem.edu)

## Overview:

University of Missouri System Digital Library's production environment is on a bare metal machine, with a development/staging environment on a virtual machine.

* Red Hat Enterprise Linux Server release 6.6 (Santiago)
* CPU: 2 threads per core, 6 cores per socket, 2 sockets
* 64G RAM

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedor GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.15
* Drupal: 7.36
* ffmpeg: 1.1.1
* Islandora: HEAD
* Java: 1.6.0_38
* Fedora: 3.6.2
* MySQlL: 5.1.73
* Solr: 3.6.2
* Tesseract: 3.02.02
* Tomcat: 6.0.35

## Settings:

* Listing on settings/configurations
* that you use.
* Example:
* ffmpeg: --prefix=/usr/local/stow/ffmpeg-1.1.4 --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS:"$DEBUG -Djava.awt.headless=true -Xms12288M -Xmx12288M -XX:MaxPermSize=512M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=4 -Dkakadu.home=$KAKADU_HOME -Djava.library.path=$LIBPATH/$PLATFORM $KAKADU_LIBRARY_PATH"
* PHP memory limit: 8192M
* Tesseract:  leptonica-1.69 libgif 4.1.6 : libjpeg 8b : libpng 1.2.46 : libtiff 3.9.5 : zlib 1.2.3.4

## Fedora XACML policies:
CODEBLOCK

repository-policies
+-- default
¦   +-- deny-reloadPolicies-if-not-localhost.xml
¦   +-- deny-unallowed-file-resolution.xml
¦   +-- permit-anything-to-administrator.xml
¦   +-- permit-apia-unrestricted.xml
¦   +-- permit-apim-to-authenticated-user.xml
¦   +-- permit-apim-to-authenticated.xml
¦   +-- permit-dsstate-check-unrestricted.xml
¦   +-- permit-getDatastreamHistory-unrestricted.xml
¦   +-- permit-getDatastream-unrestricted.xml
¦   +-- permit-oai-unrestricted.xml
¦   +-- permit-serverStatus-unrestricted.xml
¦   +-- permit-upload-to-authenticated-user.xml
¦   +-- readme.txt
+-- islandora_policies
¦   +-- permit-apim-to-authenticated-user.xml
¦   +-- permit-getDatastreamHistory-unrestricted.xml
¦   +-- permit-getDatastream-unrestricted.xml
¦   +-- permit-upload-to-authenticated-user.xml

## Drupal Modules:

contrib

* admin_menu
* advanced_help
* block_class
* chart
* coder
* colorbox
* ctools
* devel
* entity
* entityreference
* exclude_node_title
* extlink
* features
* features_extra
* feeds
* galleria
* git_deploy
* google_analytics
* i18n
* image_field_caption
* image_link_formatter
* imagemagick
* jquery_update
* ldap
* libraries
* link
* linkchecker
* node_export
* oauth
* openid_selector
* securelogin
* strongarm
* uuid
* variable
* views
* views_slideshow
* views_slideshow_galleria

islandora

* google_analytics_reports
* islandora
* islandora_bagit
* islandora_batch
* islandora_book_batch
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_fits
* islandora_ga_reports
* islandora_image_annotation
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_ip_embargo
* islandora_jodconverter
* islandora_jwplayer
* islandora_mapping
* islandora_marcxml
* islandora_oai
* islandora_ocr
* islandora_openseadragon
* islandora_paged_content
* islandora_plupload
* islandora_premis
* islandora_scholar
* islandora_simple_workflow
* islandora_solr_facet_pages
* islandora_solr_metadata
* islandora_solr_search
* islandora_solr_views
* islandora_solution_pack_audio
* islandora_solution_pack_book
* islandora_solution_pack_collection
* islandora_solution_pack_compound
* islandora_solution_pack_document
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
* objective_forms
* php_lib
