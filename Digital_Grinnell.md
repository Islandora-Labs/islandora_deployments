# [Digital Grinnell](https://digital.grinnell.edu)
##
## Overview:

In production since 2012, https://Digital.Grinnell.edu is a 2-server configuration, with Fedora 3.6.2 on the back-end server and Islandora v7 on the front-end.  There is also a dev/test staging server (https://DigitalX.Grinnell.edu) with a configuration which is identical to the production front-end.

All servers are configured and maintained using Puppet Apply with system specs including:

* Ubuntu Linux 14.04 LTS
* 2 CPUs
* 24G RAM
* PHP Version 5.5.9-1ubuntu4.9

# Repository7.Grinnell.edu
This is the back-end server configured to run Fedora and Solr.

## Tomcat:
Apache Tomcat Version 6.0.35 runs in Java on the back-end server and is accessible only from either of the two front-end servers.

Java and Tomcat specs include:

Java(TM) SE Runtime Environment (build 1.7.0_80-b15)

* CATALINA\_HOME=/usr/local/fedora/tomcat
* JRE\_HOME=/usr/lib/jvm/java-7-oracle/jre
* JAVA\_OPTS=-Xms2048m -Xmx4096m -XX:MaxPermSize=512m -Djavax.net.ssl.trustStore=/usr/local/fedora/server/truststore -Djavax.net.ssl.trustStorePassword=tomcat
* JAVA\_HOME=/usr/lib/jvm/java-7-oracle

Tomcat webapps on the back-end include:

* Adore-Djatoka v1.1
* Fedora v3.6.2
* FedoraGSearch
* Solr v4.2.1

## Fedora v3.6.2:
Fedora runs on the back-end server only.  Specs include:

* FEDORA_HOME=/usr/local/fedora
* KAKADU\_LIBRARY\_PATH=/opt/adore-djatoka-1.1/lib/Linux-x86-64

## Other Back-End Apps
* ntpd - NTP daemon program - Ver. 4.2.6p5


#Digital.Grinnell.edu
This is the front-end server configured to run Islandora v7 on Drupal v7.37.

## Software versions:
* Java(TM) SE Runtime Environment (build 1.7.0_80-b15) is installed here, primarly to run a Handle Server, v7.1.

> java -server -Xmx200M -cp :/hs/hsj-7.1/bin/../lib/admintool.jar:/hs/hsj-7.1/bin/../lib/cnriutil.jar:/hs/hsj-7.1/bin/../lib/handle.jar:/hs/hsj-7.1/bin/../lib/icu4j-4_2_1-idna.jar:/hs/hsj-7.1/bin/../lib/je-3.3.96.jar:/hs/hsj-7.1/bin/../lib/json_simple-1.1.jar:/hs/hsj-7.1/bin/../lib/jython-2.2.1.jar:/hs/hsj-7.1/bin/../lib/oldadmintool.jar:/hs/hsj-7.1/bin/../lib/*/*.jar:/hs/hsj-7.1/bin/../lib/amazons3/*.jar net.handle.server.Main /hs/srv_1

* Webmin v1.740

* Apache Webserver v2.4.7

* MySQL Server v5.5.43

* OpenSSH v6.6.1

* Memcached runs here with parameters "/usr/bin/memcached -m 64 -p 11211 -u memcache -l 127.0.0.1"

* ffmpeg v2.5.3

* Tesseract v3.03 [leptonica-1.70
  libgif 4.1.6(?) : libjpeg 8d : libpng 1.2.50 : libtiff 4.0.3 : zlib 1.2.8 : webp 0.4.0]
  
## Other Settings:

* PHP memory limit: 8192M

## Fedora XACML policies:

Tree output of repository-policies drectory (`tree /path/to/repository-policies`) is yet to be documented.

## Active Drupal (version 7.37) Modules:

* Add another (addanother) version: 7.x-1.2
* Advanced help (advanced_help)
* Backup and Migrate (backup_migrate)
* CKEditor (ckeditor)
* Color (color)
* Comment (comment)
* Context layouts (context_layouts)
* Context UI (context_ui)
* Contextual links (contextual)
* Dashboard (dashboard)
* Database logging (dblog)
* Date All Day (date_all_day)
* Date Popup (date_popup)
* Date Repeat Field (date_repeat_field)
* Date Tools (date_tools)
* Date Views (date_views)
* Delete content and users (delete_all)
* Devel (devel)
* Digital Grinnell v7 Code (dg7)
* Drupal-to-Drupal migration (migrate_d2d)
* Entity tokens (entity_token)
* Fast Permissions Administration (fpa)
* Fedora Import Control (FIC) (fic)
* Fedora Object Control (FOC) (foc)
* Git Deploy (git_deploy)
* Global Redirect (globalredirect)
* Help (help)
* ImageMagick Advanced (imagemagick_advanced)
* IMCE (imce)
* Islandora Audio (islandora_audio)
* Islandora basic image (islandora_basic_image)
* Islandora Bibliography (islandora_bibliography)
* Islandora Binary Object Storage(islandora_binary_object)
* Islandora Book Solution Pack (islandora_book)
* Islandora Compound Object (islandora_compound_object)
* Islandora Entities (islandora_entities)
* Islandora Google Scholar (islandora_google_scholar)
* Islandora Health Check (IHC) (ihc)
* Islandora Internet Archive BookReader(islandora_internet_archive_bookreader)
* Islandora JW Player (islandora_jwplayer)
* Islandora Large Image Solution Pack (islandora_large_image)
* Islandora Mods Display Changes (islandora_mods_display)
* Islandora OAI Provider (islandora_oai)
* Islandora OCR (islandora_ocr)
* Islandora OpenSeadragon (islandora_openseadragon)
* Islandora PDF (islandora_pdf)
* Islandora pdf.js Reader (islandora_pdfjs_reader)
* Islandora Scholar (islandora_scholar)
* Islandora Solr Display Profiles (islandora_solr_config)
* Islandora Solr Facet Pages (islandora_solr_facet_pages)
* Islandora Sync Field Collection (islandora_sync_field_collection)
* Islandora Sync Relation (islandora_sync_relation)
* Islandora Video Solution Pack (islandora_video)
* Islandora Web ARChive Solution Pack (islandora_web_archive)
* Islandora Webform (islandora_webform)
* Islandora XACML Editor (islandora_xacml_editor)
* Islandora XQuery (islandora_xquery)
* Islandora XML Forms (xml_forms)
* jQuery Update (jquery_update)
* Login Destination (login_destination)
* Maillog / Mail Developer (maillog)
* Masquerade (masquerade)
* Memcache (memcache)
* Memcache Admin (memcache_admin)
* Menu (menu)
* Migrate UI (migrate_ui)
* Module filter (module_filter)
* Overlay (overlay)
* Page Title (page_title)
* Pathauto (pathauto)
* PHP filter (php)
* PHPMailer (phpmailer)
* RDF (rdf)
* Redirect 403 to User Login (r4032login)
* Remove Generator (remove_generator)
* Search (search)
* Shortcut (shortcut)
* simplehtmldom API (simplehtmldom)
* Statistics (statistics)
* Syslog (syslog)
* Token Filter (token_filter)
* Toolbar (toolbar)
* Transliteration (transliteration)
* Update manager (update)
* Views Bulk Operations (views_bulk_operations)
* Views UI (views_ui)

## Build Scripts:
Later.







