# Islandora Deployments

## Description

This repository consists of a variety of Islandora deployments from various institutions. If you would like to add a deployment, contact [Nick Ruest](https://github.com/ruebot) and he'll add you as a collaborator on the repo.

## Format

```markdown

# [Name of repository](https://example.sample)

## Overview:

Brief overview of the setup. Is it on a single machine, or multiple machines. Then list the OS, numbers CPUs, and RAM.

* Ubuntu 12.04.02 LTS x64
* 4 CPUs
* 24G RAM

## Tomcat webapps:

* List all
* Tomcat web applications
* You are running.
* Example:
* Adore-djatoka
* Fedora

## Software versions:

* List all of
* the version numbers
* of software you are running.
* Example:
* Apache 2.22
* Fedora 3.6.2

## Settings:

* Listing on settings/configurations
* that you use.
* Example:
* ffmpeg: --prefix=/usr/local/stow/ffmpeg-1.1.4 --enable-gpl --enable-version3 --enable-nonfree --enable-postproc --enable-libopencore-amrnb --enable-libopencore-amrwb --enable-libdc1394 --enable-libfaac --enable-libgsm --enable-libmp3lame --enable-libopenjpeg --enable-libschroedinger --enable-libspeex --enable-libtheora --enable-libvorbis --enable-libvpx --enable-libx264 --enable-libxvid
* JAVA_OPTS:"$DEBUG -Djava.awt.headless=true -Xms12288M -Xmx12288M -XX:MaxPermSize=512M -XX:+UseParNewGC -XX:+CMSParallelRemarkEnabled -XX:+UseConcMarkSweepGC -XX:ParallelGCThreads=4 -Dkakadu.home=$KAKADU_HOME -Djava.library.path=$LIBPATH/$PLATFORM $KAKADU_LIBRARY_PATH"
* PHP memory limit: 8192M
* Tesseract:  leptonica-1.69 libgif 4.1.6 : libjpeg 8b : libpng 1.2.46 : libtiff 3.9.5 : zlib 1.2.3.4

## Fedora XACML policies:

Tree output of your repository-policies directory (`tree /path/to/repository-policies`).

CODEBLOCK

repository-policies
├── default
│   ├── deny-reloadPolicies-if-not-localhost.xml
│   ├── permit-anything-to-administrator.xml
│   ├── permit-apia-unrestricted.xml
│   ├── permit-dsstate-check-unrestricted.xml
│   ├── permit-oai-unrestricted.xml
│   ├── permit-serverStatus-unrestricted.xml
│   └── readme.txt
└── islandora
    ├── permit-apim-to-authenticated-user.xml
    ├── permit-getDatastreamHistory-unrestricted.xml
    ├── permit-getDatastream-unrestricted.xml
    └── permit-upload-to-authenticated-user.xml

## Drupal Modules:

* A list of all of
* Your installed 
* Drupal modules
```
