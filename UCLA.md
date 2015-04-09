# [UCLA Library Digital Collections](http://digital.library.ucla.edu/collections/islandora/object/islandora%3Aroot)

## Overview:

This document describes what we have now, not what we'd like to have. We're working to split all our services (Solr, Fedora, Apache / Drupal, Djatoka, etc.) out onto different virtual machines.

We currently have testing, staging, and production environments.  We use Jenkins and a GitHub repository to move versions of the codebase from Testing to Staging and then to Production.

### Testing
* Red Hat Enterprise Linux Server release 6.6 (Santiago)
* 2 CPU
* 4 GB RAM

### Staging
* Red Hat Enterprise Linux Server release 6.6 (Santiago)
* 4 CPU
* 4 GB RAM

### Production
* Red Hat Enterprise Linux Server release 6.6 (Santiago)
* 4 CPU
* 16 GB RAM

## Tomcat webapps:

We currently use an external Tomcat on our `Testing` machine and the one that's internal to Islandora/Fedora on our `Staging` and `Production` machines. The list of webapps running are the same across all three environments.

* [Adore-Djatoka](http://projects.freelibrary.info/freelib-djatoka/) (we plan to use a different fork of Djatoka once we split the image server out onto its own machine)
* [Fedora](http://www.fedora-commons.org/)
* [GSearch](https://github.com/fcrepo3/gsearch)
* [FOP](https://xmlgraphics.apache.org/fop/)
* [Solr](https://lucene.apache.org/solr/)

## Software versions:

* Apache/2.2.15
* Solr 4.2
* Fedora 3.5
* GSearch 2.4.1
* Adore-Djatoka 1.1
* Islandora 7.x-1.4
* Wowza Streaming Server 2.2.0.4709
* OpenJDK 64-Bit Server VM 1.7.0_75
* MySQL  Ver 14.14 Distrib 5.1.73
* Tomcat 7.0.33

## Settings:

* ffmpeg: --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS: "-Xmx8192m -XX:MaxPermSize=256m -Djava.awt.headless=true -Dkakadu.home=/opt/adore-djatoka/bin/Linux-x86-64 -Djava.library.path=/opt/adore-djatoka/lib/Linux-x86-64"
* PHP memory limit: 512M

## Fedora XACML policies:

    /usr/local/fedora/data/fedora-xacml-policies
    └── repository-policies
        └── default
            ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
            ├── deny-policy-management-if-not-administrator.xml
            ├── deny-purge-datastream-if-active-or-inactive.xml
            ├── deny-purge-object-if-active-or-inactive.xml
            ├── deny-unallowed-file-resolution.xml
            ├── permit-anything-to-administrator.xml
            ├── permit-apia-unrestricted.xml
            ├── permit-dsstate-check-unrestricted.xml
            ├── permit-oai-unrestricted.xml
            └── permit-serverStatus-unrestricted.xml

## Drupal Modules:

* actions_permissions
* addthis
* addthis_displays
* admin_devel
* admin_menu
* admin_menu_toolbar
* admin_theme
* backup_migrate
* bartik
* bean
* bean_admin_ui
* bean_uuid
* block_class
* ckeditor
* colorbox
* ctools
* ctools_custom_content
* diff
* entity
* entity_token
* features
* features_diff
* field
* field_collection
* field_group
* field_sql_storage
* file
* file_entity
* filter
* image
* imagemagick
* islandora
* islandora_audio
* islandora_basic_collection
* islandora_basic_image
* islandora_batch
* islandora_binary_object
* islandora_book
* islandora_book_batch
* islandora_collection_search
* islandora_compound_object
* islandora_image_annotation
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_large_image
* islandora_manuscript
* islandora_newspaper
* islandora_ocr
* islandora_openseadragon
* islandora_paged_content
* islandora_paged_tei_seadragon
* islandora_pdf
* islandora_rest
* islandora_solr
* islandora_solr_config
* islandora_solr_facet_pages
* islandora_solr_metadata
* islandora_solr_views
* islandora_video
* islandora_xacml_api
* islandora_xacml_editor
* islandora_xmlsitemap
* jcarousel
* jquery_update
* level_2_images_view
* level_2_v1_0_stage
* libraries
* list
* media
* media_internet
* menu
* module_filter
* node
* node_embed
* nodequeue
* nodequeue_pager
* objective_forms
* options
* page_manager
* panels
* path
* pathauto
* pdf
* php_lib
* print
* relation
* relation_endpoint
* relation_select
* seven
* sharethis
* strongarm
* subform
* system
* taxonomy
* taxonomy_breadcrumb
* tempmodsdisplay
* text
* token
* ucla_migration
* ucla_pdf
* update
* user
* uuid
* uuid_features
* views
* views_content
* views_field_view
* views_php
* views_ui
* wysiwyg_filter
* xml_form_api
* xml_form_builder
* xml_form_elements
* xml_forms
* xml_schema_api
* xmlsitemap
* xmlsitemap_custom
* xmlsitemap_engines
* xmlsitemap_menu
* xmlsitemap_node
* xsl_formatter
* zip_importer

## Build Scripts:

* Repository for our [base multisite](https://github.com/UCLALibrary/islandora_drupal_base) Drupal (the `scripts` dir has some build scripts used by Jenkins)
* Our [Solr configuration](https://github.com/UCLALibrary/basic-solr-config) repository

## Future Plans

We'd like to have a [Packer.io](https://packer.io/) build for each of our services (Solr, Fedora, Apache / Drupal, etc.) and a way to orchestrate them so we could move towards the goal of an [immutable server](http://martinfowler.com/bliki/ImmutableServer.html).  We also plan to use Drush Make instead of our current all-in-one repository.