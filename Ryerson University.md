# [RULA Digital Repository](https://digital.library.ryerson.ca)

## Overview:

RULA Digital Repository is deployed on a single virtual machine, and the Fedora data directory is deployed to a 500GB SAN partition.

* Ubuntu 12.04.5 LTS x64
* 2 CPUs
* 8GB RAM

## Tomcat webapps:

* Adore-Djatoka
* Fedora
* Fedora GSearch
* Solr

## Software versions:

* Adore-Djatoka: 1.1
* Apache: 2.2.22
* Drupal: 7.31
* ffmpeg: 0.8.15
* FITS: 0.6.2
* Islandora: HEAD
* Java: 1.7.0_55 (OpenJDK)
* jQuery: 1.10.2
* jQuery UI: 1.10.2
* Fedora: 3.7.0
* Fedora GSearch: 2.6
* MySQL: 5.5.38
* Solr: 4.2.0
* Tesseract: 3.2.02

## Settings:

* JAVA_OPTS:"$DEBUG -Djava.awt.headless=true -Xms4096M -Xmx4096M -XX:MaxPermSize=128M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC"
* PHP memory limit: 256M

## Fedora XACML policies:

```
repository-policies
└── default
    ├── deny-apim-if-not-localhost.xml
    ├── deny-inactive-or-deleted-objects-or-datastreams-if-not-administrator.xml
    ├── deny-policy-management-if-not-administrator.xml
    ├── deny-reloadPolicies-if-not-localhost.xml
    ├── deny-unallowed-file-resolution.xml
    ├── permit-anything-to-administrator.xml
    ├── permit-apia-unrestricted.xml
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-dsstate-check-unrestricted.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    ├── permit-oai-unrestricted.xml
    ├── permit-serverStatus-unrestricted.xml
    ├── permit-upload-to-authenticated-user.xml
    └── readme.txt
```

## Drupal Modules:

* advanced_help
* bibutils
* citation_exporter
* citeproc
* csl
* customerror
* doi_importer
* endnotexml_importer
* help_example
* imagemagick
* imagemagick_advanced
* islandora
* islandora_audio
* islandora_basic_collection
* islandora_basic_image
* islandora_batch
* islandora_bibliography
* islandora_book
* islandora_bookmark
* islandora_checksum
* islandora_checksum_checker
* islandora_fits
* islandora_google_scholar
* islandora_handle
* islandora_importer
* islandora_internet_archive_bookreader
* islandora_jwplayer
* islandora_marcxml
* islandora_oai
* islandora_ocr
* islandora_paged_content
* islandora_pdf
* islandora_premis
* islandora_scholar
* islandora_scholar_embargo
* islandora_solr
* islandora_solr_config
* islandora_solr_facet_pages
* islandora_solr_geo
* islandora_solr_metadata
* islandora_solr_views
* islandora_usage_stats
* islandora_video
* islandora_xacml_api
* islandora_xacml_editor
* islandora_xmlsitemap
* jquery_update
* libraries
* objective_forms
* php_lib
* pmid_importer
* ris_importer
* rula_islandora_oai
* token
* views
* views_ui
* xmlsitemap
* xml_forms
* xml_form_api
* xml_form_builder
* xml_form_elements
* xml_schema_api
* zip_importer
