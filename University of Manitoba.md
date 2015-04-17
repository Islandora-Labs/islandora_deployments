# UM Digital Collections

## Overview:

This system is not currently in production and will be used to replace the current [Amazon instance](http://digitalcollections.lib.umanitoba.ca) in spring 2015.

UM Digital Collections consists of a back-end server for ingest and data manipulation by staff (_[juno.lib.umanitoba.ca](#juno)_) and a front-end system strictly for public access and browsing (_[syn.lib.umanitoba.ca](#syn)_).

Both are virtual machines and share the Fedora data directory which is deployed to a 50 TB NFS mount.

## <a name="juno"></a>Juno.lib.umanitoba.ca

Juno is a normal functioning Fedora/Islandora instance that allows for CRUD actions and has the GSearch client to update the Solr index.

* RedHat Enterprise Linux Server release 6.6 (Santiago)
* 2 CPUs
* 6 GB RAM

### Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

### Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.15 
* Drupal: 7.32
* ffmpeg: N-60902-gbc249bd
* FITS: 0.8.0
* Islandora: 7.x-1.4
* Java: 1.7.0_45 (Oracle)
* jQuery: 1.4.4
* jQuery UI: 1.8.7
* Fedora: 3.7.0
* Fedora GSearch: 2.7
* MySQL: 5.6.10-log
* Solr: 4.6.0
* Tesseract: 3.02.02

### Settings:

* ffmpeg: --enable-nonfree --enable-libfaac --enable-gpl --enable-libx264 --prefix=/usr/local
* JAVA_OPTS="-Xms2048m -Xmx3072m -XX:+UseConcMarkSweepGC -XX:+CMSClassUnloadingEnabled -XX:+AggressiveOpts -XX:PermSize=128m -XX:MaxPermSize=512m -server -Djava.awt.headless=true"
* PHP memory limit: 2048M
* Tesseract: leptonica-1.69 -> libjpeg 6b : libpng 1.2.49 : libtiff 3.9.4 : zlib 1.2.3

### Fedora XACML policies:

```
repository-policies
├── default
│   ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
│   ├── deny-reloadPolicies-if-not-localhost.xml
│   ├── deny-unallowed-file-resolution.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-apim-to-authenticated.xml
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-getDatastreamHistory-unrestricted.xml
│   ├── permit-getDatastream-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   ├── permit-upload-to-authenticated-user.xml
│   └── readme.txt
│
└── islandora
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    └── permit-upload-to-authenticated-user.xml
```

### Drupal Modules:

* Administration menu (admin_menu)
* Administration menu Toolbar style (admin_menu_toolbar)
* Alternative PHP Cache (apc)
* Automated Logout (autologout)
* Block (block)
* CAPTCHA (captcha)
* Chaos tools (ctools)
* Colorbox (colorbox)
* Color (color)
* Comment (comment)
* Contextual links (contextual)
* Dashboard (dashboard)
* Database logging (dblog)
* Devel (devel)
* Entity API (entity)
* Field (field)
* Field SQL storage (field_sql_storage)
* Field UI (field_ui)
* File (file)
* Filter (filter)
* Git Deploy (git_deploy)
* Google Analytics (googleanalytics)
* Help (help)
* Image CAPTCHA (image_captcha)
* Image (image)
* ImageMagick (imagemagick)
* Islandora Audio (islandora_audio)
* Islandora basic collection (islandora_basic_collection)
* Islandora basic image (islandora_basic_image)
* Islandora Batch (islandora_batch)
* Islandora Book Batch (islandora_book_batch)
* Islandora Book Solution Pack (islandora_book)
* Islandora Collection Search (islandora_collection_search)
* Islandora compound object (islandora_compound_object)
* Islandora FITS (islandora_fits)
* Islandora Internet Archive BookReader (islandora_internet_archive_bookreader)
* Islandora (islandora)
* Islandora JW Player (islandora_jwplayer)
* Islandora Large Image Solution Pack (islandora_large_image)
* Islandora newspaper (islandora_newspaper)
* Islandora OCR (islandora_ocr)
* Islandora OpenSeadragon (islandora_openseadragon)
* Islandora Paged Content (islandora_paged_content)
* Islandora PDF (islandora_pdf)
* Islandora Restricted (islandora_restricted)
* Islandora Solr display profiles (islandora_solr_config)
* Islandora Solr (islandora_solr)
* Islandora Video Solution Pack (islandora_video)
* Islandora Xacml Api (islandora_xacml_api)
* Islandora XACML Editor (islandora_xacml_editor)
* Islandora XML Form API (xml_form_api)
* Islandora XML Form Builder (xml_form_builder)
* Islandora XML Form Elements (xml_form_elements)
* Islandora XML Forms (xml_forms)
* Islandora XML Schema API (xml_schema_api)
* LDAP Authentication (ldap_authentication)
* LDAP Servers (ldap_servers)
* LDAP User Module (ldap_user)
* Libraries (libraries)
* List (list)
* Login Security (login_security)
* Manidora (manidora)
* Memcache Admin (memcache_admin)
* Memcache (memcache)
* Menu (menu)
* Node (node)
* Number (number)
* Objective Forms (objective_forms)
* Options (options)
* Path (path)
* PDF version (print_pdf)
* PHP filter (php)
* PHP Lib (php_lib)
* Printer-friendly pages (print)
* purge (purge)
* Queue UI (queue_ui)
* RDF (rdf)
* reCAPTCHA (recaptcha)
* Search (search)
* Secure Login (securelogin)
* Session Limit (session_limit)
* Shortcut (shortcut)
* simplehtmldom API (simplehtmldom)
* System (system)
* Taxonomy (taxonomy)
* Text (text)
* UofM Batch Index (uofm_batch_index)
* UofM Derivative Fixer (uofm_derivative_fixer)
* UofM Drush Ingest (uofmingest)
* UofM Newspaper Batch (uofm_newspaper_batch)
* UofM Newspaper Solr Display (uofm_newspaper_solr)
* Update manager (update)
* User (user)
* Views UI (views_ui)
* Views (views)

## <a name="syn"></a>Syn.lib.umanitoba.ca

Syn provides read-only access to the objects in the repository. It has it's own Fedora instance which shares the objectStore and datastreamStore with Juno (but with read-only access). It has it's own resource index and Solr index, both of which are synchronized from Juno at 15 minute intervals.

* RedHat Enterprise Linux Server release 6.6 (Santiago)
* 2 CPUs
* 6 GB RAM

### Tomcat webapps:

* Adore-Djatoka
* Fedora
* Solr

### Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.15 
* Drupal: 7.32
* Islandora: 7.x-1.4
* Java: 1.7.0_45 (Oracle)
* jQuery: 1.4.4
* jQuery UI: 1.8.7
* Fedora: 3.7.0
* MySQL: 5.6.10-log
* Solr: 4.6.0

### Settings:

* JAVA_OPTS="-Xms2048m -Xmx3072m -XX:+UseConcMarkSweepGC -XX:+CMSClassUnloadingEnabled -XX:+AggressiveOpts -XX:PermSize=128m -XX:MaxPermSize=512m -server -Djava.awt.headless=true"
* PHP memory limit: 2048M

### Fedora XACML policies:

```
repository-policies
├── default
│   ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
│   ├── deny-reloadPolicies-if-not-localhost.xml
│   ├── deny-unallowed-file-resolution.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-apim-to-authenticated.xml
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-getDatastreamHistory-unrestricted.xml
│   ├── permit-getDatastream-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   ├── permit-upload-to-authenticated-user.xml
│   └── readme.txt
│
└── islandora
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    └── permit-upload-to-authenticated-user.xml
```

### Drupal Modules:

* Administration menu (admin_menu)
* Administration menu Toolbar style (admin_menu_toolbar)
* APC - Alternative PHP Cache (apc)
* Automated Logout (autologout)
* Block (block)
* Cache Expiration (expire)
* CAPTCHA (captcha)
* Chaos tools (ctools)
* Colorbox (colorbox)
* Color (color)
* Comment (comment)
* Contextual links (contextual)
* Dashboard (dashboard)
* Database logging (dblog)
* Devel (devel)
* Entity API (entity)
* Entity tokens (entity_token)
* Field (field)
* Field SQL storage (field_sql_storage)
* Field UI (field_ui)
* File (file)
* Filter (filter)
* Help (help)
* Image CAPTCHA (image_captcha)
* Image (image)
* ImageMagick (imagemagick)
* Islandora Audio (islandora_audio)
* Islandora basic collection (islandora_basic_collection)
* Islandora basic image (islandora_basic_image)
* Islandora Batch (islandora_batch)
* Islandora Book Batch (islandora_book_batch)
* Islandora Book Solution Pack (islandora_book)
* Islandora Collection Search (islandora_collection_search)
* Islandora compound object (islandora_compound_object)
* Islandora FITS (islandora_fits)
* Islandora Internet Archive BookReader (islandora_internet_archive_bookreader)
* Islandora (islandora)
* Islandora JW Player (islandora_jwplayer)
* Islandora Large Image Solution Pack (islandora_large_image)
* Islandora newspaper (islandora_newspaper)
* Islandora OpenSeadragon (islandora_openseadragon)
* Islandora Paged Content (islandora_paged_content)
* Islandora PDF (islandora_pdf)
* Islandora Restricted (islandora_restricted)
* Islandora Solr Customizations (islandora_custom_solr)
* Islandora Solr display profiles (islandora_solr_config)
* Islandora Solr (islandora_solr)
* Islandora Video Solution Pack (islandora_video)
* Islandora Xacml Api (islandora_xacml_api)
* Islandora XACML Editor (islandora_xacml_editor)
* LDAP Authentication (ldap_authentication)
* LDAP Servers (ldap_servers)
* LDAP User Module (ldap_user)
* Libraries (libraries)
* List (list)
* Login Destination (login_destination)
* Login Security (login_security)
* Manidora (manidora)
* Memcache Admin (memcache_admin)
* Memcache (memcache)
* Menu (menu)
* Node (node)
* Number (number)
* Objective Forms (objective_forms)
* Options (options)
* Path (path)
* PDF version (print_pdf)
* PHP filter (php)
* PHP Lib (php_lib)
* Printer-friendly pages (print)
* Printer-friendly pages UI (print_ui)
* RDF (rdf)
* reCAPTCHA (recaptcha)
* Search (search)
* Secure Login (securelogin)
* Session Limit (session_limit)
* Shortcut (shortcut)
* simplehtmldom API (simplehtmldom)
* System (system)
* Taxonomy (taxonomy)
* TCPDF library handler (print_pdf_tcpdf)
* Text (text)
* Update manager (update)
* User (user)
* Varnish (varnish)
* Views UI (views_ui)
* Views (views)
