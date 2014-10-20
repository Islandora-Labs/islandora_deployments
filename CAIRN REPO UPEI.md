# [CAIRN Repository - Hosted by Robertson Library UPEI](https://cairnrepo.org)

## Overview:

The CAIRN Repository is deployed on a Blade server, and the Fedora data directory is deployed to a 2T Fibre Channel SAN mount.  All derivate processing and the associated applications (ImageMagick, Tesseract, FITS, LAME, FFmpeg,Ghostscript) are deployed on a separate dedicated processing Blade running UPEI's [PHP Microservices](https://github.com/roblib/php_listeners). The microservices listen for messages from Fedora's JMS and Taverna workflows are triggered based on the messages received. Review the [wiki](https://github.com/roblib/php_listeners/wiki) for further documentation..

* Ubuntu 14.04.1 LTS (GNU/Linux 3.13.0-32-generic x86_64)
* 24 processors (Intel(R) Xeon(R) CPU X5650  @ 2.67GHz)
* 48G RAM

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.4.7 (Ubuntu)
* Drupal: 7.32
* PHP: 5.5.9-1ubuntu4.4
* Islandora: 7.x-1.4
* Java: 1.7.0_51 (Oracle)
* ? jQuery: 1.8.2
* ? jQuery UI: 1.10.2
* Fedora: 3.8.0
* Fedora GSearch: 2.7
* MySQL: 5.5.40-0ubuntu0.14.04.1
* Solr: 4.2.0
* Tomcat: 7.0.55

## Settings:

* JAVA_OPTS=-Xms1024m -Xmx1024m -XX:MaxPermSize=512m -XX:+CMSClassUnloadingEnabled -Djavax.net.ssl.trustStore=/usr/local/fedora/server/truststore -Djavax.net.ssl.trustStorePassword=tomcat -Dcom.sun.management.jmxremote=true
* PHP memory limit: 500M

## Fedora XACML policies:

```
repository-policies
├── default
│   ├── deny-apim-if-not-localhost.xml
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

*
* imagemagick
* islandora
* islandora_bagit
* islandora_batch
* islandora_bookmark
* islandora_fits
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_marcxml
* islandora_oai
* islandora_openseadragon
* islandora_paged_content
* islandora_pathauto
* islandora_premis
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
* islandora_videojs
* islandora_xacml_editor
* islandora_xml_forms
* islandora_xmlsitemap
* libraries
* objective_forms
* pathauto
* php_lib
* xmlsitemap
