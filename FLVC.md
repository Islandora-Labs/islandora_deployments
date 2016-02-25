# [Florida Virtual Campus](https://fsu.digital.flvc.org)

Version 1.1 2/25/2016

## Overview:

FLVC is implemented on a VMware cluster running VMWARE 5.5 all servers are virtualized, all run RHEL 6.5)
The CO-OP server is located at a different datacenter

Production
Main (fedora, drupal, solr, apache)
* 8 CPUs
* 18 GB RAM

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
* Fedora 3.7.1
* Drupal 7.41
* Postgres 9.1.20
* Solr 4.2
* Gsearch 2.8
* Tomcat 6.0.35

## Settings:

* JAVA_OPTS="$JAVA_OPTS -Xmx10G -Xms10G"
* JAVA_OPTS="$JAVA_OPTS -XX:MaxPermSize=256M"
* JAVA_OPTS="$JAVA_OPTS -Xloggc:/var/log/tomcat/java_gc.log"
* php.ini: memory_limit = 512M

## Drupal Modules:
```
* Chaos tool suite          Chaos tools (ctools)                                               Module  Enabled        7.x-1.9        
* Core                      Aggregator (aggregator)                                            Module  Enabled        7.41           
* Core                      Block (block)                                                      Module  Enabled        7.41           
* Core                      Color (color)                                                      Module  Enabled        7.41           
* Core                      Comment (comment)                                                  Module  Enabled        7.41           
* Core                      Contextual links (contextual)                                      Module  Enabled        7.41           
* Core                      Dashboard (dashboard)                                              Module  Enabled        7.41           
* Core                      Database logging (dblog)                                           Module  Enabled        7.41           
* Core                      Field (field)                                                      Module  Enabled        7.41           
* Core                      Field SQL storage (field_sql_storage)                              Module  Enabled        7.41           
* Core                      Field UI (field_ui)                                                Module  Enabled        7.41           
* Core                      File (file)                                                        Module  Enabled        7.41           
* Core                      Filter (filter)                                                    Module  Enabled        7.41           
* Core                      Help (help)                                                        Module  Enabled        7.41           
* Core                      Image (image)                                                      Module  Enabled        7.41           
* Core                      List (list)                                                        Module  Enabled        7.41           
* Core                      Menu (menu)                                                        Module  Enabled        7.41           
* Core                      Node (node)                                                        Module  Enabled        7.41           
* Core                      Number (number)                                                    Module  Enabled        7.41           
* Core                      Options (options)                                                  Module  Enabled        7.41           
* Core                      Overlay (overlay)                                                  Module  Enabled        7.41           
* Core                      Path (path)                                                        Module  Enabled        7.41           
* Core                      PHP filter (php)                                                   Module  Enabled        7.41           
* Core                      RDF (rdf)                                                          Module  Enabled        7.41           
* Core                      Search (search)                                                    Module  Enabled        7.41           
* Core                      Shortcut (shortcut)                                                Module  Enabled        7.41           
* Core                      System (system)                                                    Module  Enabled        7.41           
* Core                      Taxonomy (taxonomy)                                                Module  Enabled        7.41           
* Core                      Text (text)                                                        Module  Enabled        7.41           
* Core                      Toolbar (toolbar)                                                  Module  Enabled        7.41           
* Core                      Update manager (update)                                            Module  Enabled        7.41           
* Core                      User (user)                                                        Module  Enabled        7.41           
* FLVC Islandora            FLVC (flvc)                                                        Module  Enabled                       
* FLVC Islandora            FLVC Custom Display (flvc_custom_display)                          Module  Enabled                       
* Islandora                 FLVC Policy Reflector (flvc_policy_reflector)                      Module  Enabled        7.x-dev        
* Islandora                 Islandora (islandora)                                              Module  Enabled        7.x-1.4        
* Islandora Dependencies    Islandora XML Form API (xml_form_api)                              Module  Enabled        7.x-1.4        
* Islandora Dependencies    Islandora XML Form Elements (xml_form_elements)                    Module  Enabled        7.x-1.4        
* Islandora Dependencies    Islandora XML Schema API (xml_schema_api)                          Module  Enabled        7.x-1.4        
* Islandora Dependencies    Objective Forms (objective_forms)                                  Module  Enabled        7.x-1.4        
* Islandora Dependencies    PHP Lib (php_lib)                                                  Module  Enabled        7.x-1.4        
* Islandora Search          Islandora Solr (islandora_solr)                                    Module  Enabled        7.x-1.4        
* Islandora Search          Islandora Solr display profiles (islandora_solr_config)            Module  Enabled        7.x-1.4        
* Islandora Search          Islandora Solr Views (islandora_solr_views)                        Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora Audio (islandora_audio)                                  Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora basic collection (islandora_basic_collection)            Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora basic image (islandora_basic_image)                      Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora Book Solution Pack (islandora_book)                      Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora compound object (islandora_compound_object)              Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora Large Image Solution Pack (islandora_large_image)        Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora newspaper (islandora_newspaper)                          Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora Paged Content (islandora_paged_content)                  Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora PDF (islandora_pdf)                                      Module  Enabled        7.x-1.4        
* Islandora Solution Packs  Islandora Serial Solution Pack (islandora_serial_object)           Module  Enabled        7.x-dev        
* Islandora Solution Packs  Islandora Video Solution Pack (islandora_video)                    Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora Batch (islandora_batch)                                  Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora Batch Importer (islandora_importer)                      Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora Binary Object Storage (islandora_binary_object)          Module  Enabled        7.x-dev        
* Islandora Tools           Islandora Bookmark (islandora_bookmark)                            Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora IP Embargo (islandora_ip_embargo)                        Module  Enabled        7.x-dev        
* Islandora Tools           Islandora MARCXML (islandora_marcxml)                              Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora OAI Provider (islandora_oai)                             Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora OCR (islandora_ocr)                                      Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora Serial Solution Pack PDF ZIP Importer                    Module  Enabled        7.x-dev        
                           (islandora_serial_object_zip_pdf_importer)                                                               
* Islandora Tools           Islandora Xacml Api (islandora_xacml_api)                          Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora XACML Editor (islandora_xacml_editor)                    Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora XML Form Builder (xml_form_builder)                      Module  Enabled        7.x-1.4        
* Islandora Tools           Islandora XML Forms (xml_forms)                                    Module  Enabled        7.x-1.4        
* Islandora Tools           Zip File Importer (zip_importer)                                   Module  Enabled        7.x-1.4        
* Islandora Viewers         Islandora Internet Archive BookReader                              Module  Enabled        7.x-1.4        
                           (islandora_internet_archive_bookreader)                                                                  
* Islandora Viewers         Islandora JW Player (islandora_jwplayer)                           Module  Enabled        7.x-1.4        
* Islandora Viewers         Islandora OpenSeadragon (islandora_openseadragon)                  Module  Enabled        7.x-1.4        
* Internationalization                                                                                                               
* Other                     Colorbox (colorbox)                                                Module  Enabled        7.x-2.8        
* Other                     Entity API (entity)                                                Module  Enabled        7.x-1.6        
* Other                     Entity tokens (entity_token)                                       Module  Enabled        7.x-1.6        
* Other                     ImageMagick (imagemagick)                                          Module  Enabled        7.x-1.0        
* Other                     ImageMagick Advanced (imagemagick_advanced)                        Module  Enabled        7.x-1.0        
* Other                     Libraries (libraries)                                              Module  Enabled        7.x-2.1        
* Other                     Login Destination (login_destination)                              Module  Enabled        7.x-1.1        
* Other                     Menu attributes (menu_attributes)                                  Module  Enabled        7.x-1.0-rc2    
* Other                     RoleAssign (roleassign)                                            Module  Enabled        7.x-1.0        
* Rules                     Rules (rules)                                                      Module  Enabled        7.x-2.6        
* Rules                     Rules Scheduler (rules_scheduler)                                  Module  Enabled        7.x-2.6        
* Rules                     Rules UI (rules_admin)                                             Module  Enabled        7.x-2.6        
* Statistics                Google Analytics (googleanalytics)                                 Module  Enabled        7.x-1.3        
* Views                     Views (views)                                                      Module  Enabled        7.x-3.11       
* Views                     Views UI (views_ui)                                                Module  Enabled        7.x-3.11       
* Core                      Bartik (bartik)                                                    Theme   Enabled        7.41           
* Core                      Seven (seven)                                                      Theme   Enabled        7.41           
* Other                     Islandoratheme (islandoratheme)                                    Theme   Enabled        7.x-3.0-rc1    
```
## XACML policies

```

/usr/local/fedora/data/fedora-xacml-policies/repository-policies/
├── default
│   ├── deny-apim-if-not-localhost.xml.disabled
│   ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
│   ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml.orig
│   ├── deny-policy-management-if-not-administrator.xml.disabled
│   ├── deny-purge-datastream-if-active-or-inactive.xml.disabled
│   ├── deny-purge-object-if-active-or-inactive.xml.disabled
│   ├── deny-reloadPolicies-if-not-localhost.xml.disabled
│   ├── deny-unallowed-file-resolution.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-apim-to-authenticated.xml.disabled
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   └── readme.txt
├── disable_all_writes.xml.disabled
├── permit-anyone-upload.xml
└── permit-apim-to-everyone.xml
```
