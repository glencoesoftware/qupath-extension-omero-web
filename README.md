# QuPath OMERO extension with raw tiles support

Welcome to the Glencoe Software's version of the OMERO extension for [QuPath](http://qupath.github.io)!

This adds support for accessing images hosted on an [OMERO](https://www.openmicroscopy.org/omero/) 
server.  If microservices are available on the OMERO server, then they will be used to retrieve
image data; all data types are supported in this case, and uncompressed image data is provided to QuPath.

If microservices are not available, then the OMERO web API is used. In this case, only uint8 images
with 3 or fewer channels are supported.

> **Important!**
> 
> The use of the web API means that all images are 
JPEG-compressed.
This effectively means it is most useful for viewing and annotating RGB images 
(including whole slide images), but is not suitable for quantitative analysis 
where JPEG compression artifacts would be problematic.

The extension is intended for QuPath 0.5.x.
It is not compatible with earlier QuPath versions.

## Installing

To install the OMERO extension, download the latest `qupath-extension-omero-[version].jar` file from [releases](https://github.com/glencoesoftware/qupath-extension-omero/releases) and drag it onto the main QuPath window.

If you haven't installed any extensions before, you'll be prompted to select a QuPath user directory.
The extension will then be copied to a location inside that directory.

You might then need to restart QuPath (but not your computer).


## Building

You can build the extension using OpenJDK 17 or later with

```bash
gradlew clean build
```

The output will be under `build/libs`.
You can drag the jar file on top of QuPath to install the extension.
