# [Florida Virtual Campus](https://fsu.digital.flvc.org)

Version 1.0 5/18/2015

## Overview:

FLVC is implemented on a VMware cluster running VMWARE 5, all servers are virtualized, all run RHEL 6.5)
The CO-OP server is located at a different datacenter

Production
Main (fedora, drupal, solr, apache)
* 8 CPUs
* 16 GB RAM

Continuous Operation Server
* 4 CPUs
* 8 GB RAM

2 Load Servers ea:
* 4 CPUs
* 6 GB RAM

Dev and Test on 4 different VMs
* 1 CPU each (except for test load which has 4)
* Different amounts of RAM on each

## Tomcat webapps:

* adore-djatoka
* fedora
* fedoragsearch
* solr

## Software versions:

* Apache 2.2.15
* Fedora 3.4.2 (upgrade to 3.7.0 pending)
* Drupal 7.36
* Postgres 9.1.15
* 

## Settings:

* Listing on settings/configurations
* that you use.
* Example:
* JAVA_OPTS:" -Xmx1024M -Xms1024M -XX:MaxPermSize=128M -XX:PermSize=32M -d64 -server -verbose:gc -Xmx6G -Xms6G -XX:MaxPermSize=256M -XX:PermSize=64M -Dfile.encoding=UTF-8 "
* PHP memory limit: 512MB


## Drupal Modules:


* ctools
* aggregator
* block
* color
* comment
* contextual
* dashboard
* dblog
* field
* field_sql_storage
* field_ui
* file
* filter
* help
* image
* list
* menu
* node
* number
* options
* overlay
* path
* php
* rdf
* search
* shortcut
* system
* taxonomy
* text
* toolbar
* update
* user
* flvc
* flvc_custom_display
* flvc_policy_reflector
* islandora
* xml_form_api
* xml_form_elements
* xml_schema_api
* objective_forms
* php_lib
* islandora_solr
* islandora_solr_config
* islandora_solr_views
* islandora_audio
* islandora_basic_collection
* islandora_basic_image
* islandora_book
* islandora_compound_object
* islandora_large_image
* islandora_newspaper
* islandora_paged_content
* islandora_pdf
* islandora_serial_object
* islandora_video
* islandora_batch
* islandora_importer
* islandora_binary_object
* islandora_ip_embargo
* islandora_marcxml
* islandora_oai
* islandora_ocr
* islandora_serial_object_zip_pdf_importer
* islandora_xacml_api
* islandora_xacml_editor
* xml_form_builder
* xml_forms
* zip_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_openseadragon
* entity
* entity_token
* imagemagick
* imagemagick_advanced
* libraries
* login_destination
* menu_attributes
* roleassign
* rules
* rules_scheduler
* rules_admin
* googleanalytics
* views
* views_ui
