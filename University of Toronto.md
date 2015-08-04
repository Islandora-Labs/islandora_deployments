# [Collections U of T](http://collections.library.utoronto.ca/)

## Overview:

Collections U of T is deployed on three virtual machines

Islandora Server
* Ubuntu 12.04.5 LTS
* 8 CPUs @ 2.8Ghz
* 8Gb Memory

Tomcat Server
* Ubuntu 12.04.5 LTS
* 8 CPUs @ 2.8Ghz
* 32Gb Memory
* 4 Tb local disk

MySQL Server
* Ubuntu 12.04.5 LTS
* 4 CPUs @ 3.3Ghz
* 12Gb Memory
* SSD disks

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.22-1ubuntu1.10
* Drupal: 7.38
* ffmpeg: 0.8.17
* Islandora: 7.x-1.4
* Java: 1.6 (OpenJDK)
* jQuery: 1.8.3
* jQuery UI: 1.10.2
* Fedora: 3.6.2
* Fedora GSearch: 2.6
* MySQL: 5.5.43-0ubuntu0.12.04.1
* Solr: 4.2.1
* Tesseract: 3.2.02
* Tomcat: 6

## Settings:

* ffmpeg: --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS="$DEBUG -Djava.awt.headless=true -Xmx30g -Xms10g -XX:MaxPermSize=512M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=8 -Dkakadu.home=$KAKADU_HOME -Djava.library.path=$LIBPATH/$PLATFORM $KAKADU_LIBRARY_PATH"
* PHP memory limit: 6144M
* Tesseract : leptonica-1.71 libjpeg 8b : libpng 1.2.46 : libtiff 3.9.5 : zlib 1.2.3.4

## Fedora XACML policies:

```
└── repository-policies
    ├── default
    │   ├── permit-anything-to-administrator.xml
    │   ├── permit-apia-unrestricted.xml
    │   ├── permit-apim-to-authenticated.xml
    │   ├── permit-dsstate-check-unrestricted.xml
    │   ├── permit-oai-unrestricted.xml
    │   ├── permit-serverStatus-unrestricted.xml
    └── islandora
        ├── permit-apim-to-anonymous-user.xml
        ├── permit-apim-to-authenticated-user.xml
        ├── permit-getDatastreamHistory-unrestricted.xml
        ├── permit-getDatastream-unrestricted.xml
        ├── permit-upload-to-anonymous-user.xml
        ├── permit-upload-to-authenticated-user.xml
```

## Drupal Modules:

```
 Administration                       Drupal Remote Dashboard - Server (drd_server)                                  Module  Enabled        7.x-2.5        
 Administration                       Module filter (module_filter)                                                  Module  Enabled        7.x-2.0        
 Chaos tool suite                     Chaos tools (ctools)                                                           Module  Enabled        7.x-1.7        
 Chaos tool suite                     Page manager (page_manager)                                                    Module  Enabled        7.x-1.7        
 Core                                 Block (block)                                                                  Module  Enabled        7.38           
 Core                                 Color (color)                                                                  Module  Enabled        7.38           
 Core                                 Comment (comment)                                                              Module  Enabled        7.38           
 Core                                 Contextual links (contextual)                                                  Module  Enabled        7.38           
 Core                                 Dashboard (dashboard)                                                          Module  Enabled        7.38           
 Core                                 Database logging (dblog)                                                       Module  Enabled        7.38           
 Core                                 Field (field)                                                                  Module  Enabled        7.38           
 Core                                 Field SQL storage (field_sql_storage)                                          Module  Enabled        7.38           
 Core                                 Field UI (field_ui)                                                            Module  Enabled        7.38           
 Core                                 File (file)                                                                    Module  Enabled        7.38           
 Core                                 Filter (filter)                                                                Module  Enabled        7.38           
 Core                                 Help (help)                                                                    Module  Enabled        7.38           
 Core                                 Image (image)                                                                  Module  Enabled        7.38           
 Core                                 List (list)                                                                    Module  Enabled        7.38           
 Core                                 Locale (locale)                                                                Module  Enabled        7.38           
 Core                                 Menu (menu)                                                                    Module  Enabled        7.38           
 Core                                 Node (node)                                                                    Module  Enabled        7.38           
 Core                                 Number (number)                                                                Module  Enabled        7.38           
 Core                                 Options (options)                                                              Module  Enabled        7.38           
 Core                                 Overlay (overlay)                                                              Module  Enabled        7.38           
 Core                                 Path (path)                                                                    Module  Enabled        7.38           
 Core                                 RDF (rdf)                                                                      Module  Enabled        7.38           
 Core                                 Search (search)                                                                Module  Enabled        7.38           
 Core                                 Shortcut (shortcut)                                                            Module  Enabled        7.38           
 Core                                 System (system)                                                                Module  Enabled        7.38           
 Core                                 Taxonomy (taxonomy)                                                            Module  Enabled        7.38           
 Core                                 Text (text)                                                                    Module  Enabled        7.38           
 Core                                 Toolbar (toolbar)                                                              Module  Enabled        7.38           
 Core                                 Update manager (update)                                                        Module  Enabled        7.38           
 Core                                 User (user)                                                                    Module  Enabled        7.38           
 Custom breadcrumbs                   Custom breadcrumbs (custom_breadcrumbs)                                        Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs API (custom_breadcrumbsapi)                                 Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs for panels (custom_breadcrumbs_panels)                      Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs for paths (custom_breadcrumbs_paths)                        Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs for taxonomy (custom_breadcrumbs_taxonomy)                  Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs for views (custom_breadcrumbs_views)                        Module  Enabled        7.x-2.0-beta1  
 Custom breadcrumbs                   Custom breadcrumbs identifiers (custom_breadcrumbs_identifiers)                Module  Enabled        7.x-2.0-beta1  
 Features                             Features (features)                                                            Module  Enabled        7.x-2.5        
 Fields                               Field collection (field_collection)                                            Module  Enabled        7.x-1.0-beta8  
 Fields                               Field Group (field_group)                                                      Module  Enabled        7.x-1.4        
 Islandora                            Islandora (islandora)                                                          Module  Enabled        7.x-1.4        
 Islandora                            Islandora Book Batch (islandora_book_batch)                                    Module  Enabled        7.x-1.4        
 Islandora                            Islandora Object Locking (islandora_object_lock)                               Module  Enabled                       
 Islandora                            Islandora Solr Facet Pages (islandora_solr_facet_pages)                        Module  Enabled        7.x-1.4        
 Islandora                            Islandora Solr Metadata (islandora_solr_metadata)                              Module  Enabled        7.x-1.4        
 Islandora Dependencies               Islandora XML Form API (xml_form_api)                                          Module  Enabled        7.x-1.4        
 Islandora Dependencies               Islandora XML Form Elements (xml_form_elements)                                Module  Enabled        7.x-1.4        
 Islandora Dependencies               Islandora XML Schema API (xml_schema_api)                                      Module  Enabled        7.x-1.4        
 Islandora Dependencies               Objective Forms (objective_forms)                                              Module  Enabled        7.x-1.4        
 Islandora Dependencies               PHP Lib (php_lib)                                                              Module  Enabled        7.x-1.4        
 Islandora Search                     Islandora Solr (islandora_solr)                                                Module  Enabled        7.x-1.4        
 Islandora Search                     Islandora Solr display profiles (islandora_solr_config)                        Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Bibutils (bibutils)                                                            Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Citation Exporter (citation_exporter)                                          Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Citeproc (citeproc)                                                            Module  Enabled        7.x-1.4        
 Islandora Solution Packs             DOI Importer (doi_importer)                                                    Module  Enabled        7.x-1.4        
 Islandora Solution Packs             EndNoteXML Importer (endnotexml_importer)                                      Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Audio (islandora_audio)                                              Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora basic collection (islandora_basic_collection)                        Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora basic image (islandora_basic_image)                                  Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Bibliography (islandora_bibliography)                                Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Book Solution Pack (islandora_book)                                  Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora compound object (islandora_compound_object)                          Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Google Scholar (islandora_google_scholar)                            Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Large Image Solution Pack (islandora_large_image)                    Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora newspaper (islandora_newspaper)                                      Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Paged Content (islandora_paged_content)                              Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora PDF (islandora_pdf)                                                  Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Scholar (islandora_scholar)                                          Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Scholar Embargo (islandora_scholar_embargo)                          Module  Enabled                       
 Islandora Solution Packs             Islandora Video Solution Pack (islandora_video)                                Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Islandora Web ARChive Solution Pack (islandora_web_archive)                    Module  Enabled        7.x-1.4        
 Islandora Solution Packs             Pubmed Importer (pmid_importer)                                                Module  Enabled        7.x-1.4        
 Islandora Solution Packs             RIS Importer (ris_importer)                                                    Module  Enabled        7.x-1.4        
 Islandora Tools                      CSL (csl)                                                                      Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Batch (islandora_batch)                                              Module  Enabled        7.x-dev        
 Islandora Tools                      Islandora Batch Importer (islandora_importer)                                  Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Binary Object Storage (islandora_binary_object)                      Module  Enabled        7.x-dev        
 Islandora Tools                      Islandora Bookmark (islandora_bookmark)                                        Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Checksum (islandora_checksum)                                        Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Checksum Checker (islandora_checksum_checker)                        Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora FITS (islandora_fits)                                                Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Image Annotation (islandora_image_annotation)                        Module  Enabled                       
 Islandora Tools                      Islandora OAI Provider (islandora_oai)                                         Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora OCR (islandora_ocr)                                                  Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora PREMIS (islandora_premis)                                            Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Simple Workflow (islandora_simple_workflow)                          Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora Usage Stats (islandora_usage_stats)                                  Module  Enabled        7.x-1.3        
 Islandora Tools                      Islandora Xacml Api (islandora_xacml_api)                                      Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora XACML Editor (islandora_xacml_editor)                                Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora XML Form Builder (xml_form_builder)                                  Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora XML Forms (xml_forms)                                                Module  Enabled        7.x-1.4        
 Islandora Tools                      Islandora XML sitemap (islandora_xmlsitemap)                                   Module  Enabled                       
 Islandora Tools                      Islandora XQuery (islandora_xquery)                                            Module  Enabled        7.x-dev        
 Islandora Tools                      Zip File Importer (zip_importer)                                               Module  Enabled        7.x-1.4        
 Islandora Viewers                    Islandora Internet Archive BookReader (islandora_internet_archive_bookreader)  Module  Enabled        7.x-1.4        
 Islandora Viewers                    Islandora JW Player (islandora_jwplayer)                                       Module  Enabled        7.x-1.4        
 Islandora Viewers                    Islandora OpenSeadragon (islandora_openseadragon)                              Module  Enabled        7.x-1.4        
 Media                                IMCE (imce)                                                                    Module  Enabled        7.x-1.9        
 Other                                AES (aes)                                                                      Module  Enabled        7.x-1.9        
 Other                                Block Class (block_class)                                                      Module  Enabled        7.x-2.1        
 Other                                Colorbox (colorbox)                                                            Module  Enabled        7.x-2.8        
 Other                                DC to MODS (dc2mods)                                                           Module  Enabled                       
 Other                                Entity API (entity)                                                            Module  Enabled        7.x-1.6        
 Other                                Google Fonts (google_fonts)                                                    Module  Enabled        7.x-2.3        
 Other                                ImageMagick (imagemagick)                                                      Module  Enabled        7.x-1.0        
 Other                                Islandora Solr Redirect (islandorasolrredirect)                                Module  Enabled                       
 Other                                Islandora Sync (islandora_sync)                                                Module  Enabled        7.x-1.3        
 Other                                Islandora Sync Field Collection (islandora_sync_field_collection)              Module  Enabled                       
 Other                                Islandora Sync Relation (islandora_sync_relation)                              Module  Enabled                       
 Other                                Libraries (libraries)                                                          Module  Enabled        7.x-2.2        
 Other                                Login Security (login_security)                                                Module  Enabled        7.x-1.9        
 Other                                Parent Collection (parent_collection)                                          Module  Enabled                       
 Other                                Pathauto (pathauto)                                                            Module  Enabled        7.x-1.2        
 Other                                Redirect (redirect)                                                            Module  Enabled        7.x-1.0-rc1    
 Other                                Security Review (security_review)                                              Module  Enabled        7.x-1.2        
 Other                                Subform (subform)                                                              Module  Enabled        7.x-1.0-alpha2 
 Other                                Token (token)                                                                  Module  Enabled        7.x-1.6        
 Panels                               Mini panels (panels_mini)                                                      Module  Enabled        7.x-3.5        
 Panels                               Panels (panels)                                                                Module  Enabled        7.x-3.5        
 Relation                             Relation (relation)                                                            Module  Enabled        7.x-1.0-rc7    
 Relation                             Relation Endpoints Field (relation_endpoint)                                   Module  Enabled        7.x-1.0-rc7    
 Relation                             Relation Select (relation_select)                                              Module  Enabled        7.x-1.x-dev    
 Search Toolkit                       Apache Solr framework (apachesolr)                                             Module  Enabled        7.x-1.7        
 Search Toolkit                       Apache Solr search (apachesolr_search)                                         Module  Enabled        7.x-1.7        
 SEO                                  Metatag (metatag)                                                              Module  Enabled        7.x-1.5        
 Statistics                           Google Analytics (googleanalytics)                                             Module  Enabled        7.x-2.1        
 tb_megamenu                          TB Mega Menu (tb_megamenu)                                                     Module  Enabled        7.x-1.0-beta5  
 User interface                       CKEditor (ckeditor)                                                            Module  Enabled        7.x-1.16       
 User interface                       jQuery Update (jquery_update)                                                  Module  Enabled        7.x-2.6        
 UTL Library                          Collections Display (collections_display)                                      Module  Enabled                       
 Variable                             Variable (variable)                                                            Module  Enabled        7.x-2.5        
 Views                                BxSlider - Views Integration (bxslider_views_slideshow)                        Module  Enabled        7.x-1.51       
 Views                                Draggableviews (draggableviews)                                                Module  Enabled        7.x-2.1        
 Views                                Views (views)                                                                  Module  Enabled        7.x-3.11       
 Views                                Views Slideshow (views_slideshow)                                              Module  Enabled        7.x-3.1        
 Views                                Views UI (views_ui)                                                            Module  Enabled        7.x-3.11       
 XML sitemap                          XML sitemap (xmlsitemap)                                                       Module  Enabled        7.x-2.2        
 XML sitemap                          XML sitemap custom (xmlsitemap_custom)                                         Module  Enabled        7.x-2.2        
```

## Build Scripts:

Servers are currently built predominantly with chef, however we're in the process of completely refactoring and automating the deployment.