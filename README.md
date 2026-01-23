# QuPath OMERO extension with raw tiles support

Welcome to Glencoe Software's version of the OMERO extension for [QuPath](http://qupath.github.io)!

This adds support for accessing images hosted on an [OMERO](https://www.openmicroscopy.org/omero/) 
server. If microservices are available on the OMERO server (OMERO Plus), they will be used to retrieve image data; all data types are supported in this case, and uncompressed image data is provided to QuPath.

If microservices are not available, then the standard OMERO web API is used. In this case, only uint8 images with 3 or fewer channels are supported.

> **Important!**
> 
> The use of the standard web API means that all images are JPEG-compressed.
This effectively means it is most useful for viewing and annotating RGB images 
(including whole slide images), but is not suitable for quantitative analysis 
where JPEG compression artifacts would be problematic.

## Compatibility

The extension is intended for use with **QuPath v0.5 and v0.6**.

**OMERO Plus Support**
While the [QuPath community extension](https://github.com/qupath/qupath-extension-omero) supports similar connectivity methods, this repository is maintained to ensure maximum stability and performance for OMERO Plus environments. It is specifically designed to leverage Glencoe Software's pixel data microservices for high-performance tile retrieval at scale.

## Docs

General documentation for working with OMERO in QuPath can be found at https://qupath.readthedocs.io/en/0.6/docs/advanced/omero.html.

> **Note:** The official QuPath documentation refers to the standard community extension. While the user installation, interface, and general workflows (e.g., browsing projects, importing images) are similar, this version differs in how it retrieves pixel data (using OMERO Plus microservices when present rather than JSON/JPEG web APIs).

## Installing

To install the OMERO extension, download the latest `qupath-extension-omero-web-[version].jar` file from [releases](https://github.com/glencoesoftware/qupath-extension-omero-web/releases) and drag it onto the main QuPath window.

If you haven't installed any extensions before, you'll be prompted to select a QuPath user directory. The extension will then be copied to a location inside that directory.

You might then need to restart QuPath (but not your computer).

## Building

You can build the extension using OpenJDK 17 or later with

```bash
gradlew clean build
```

The output will be under `build/libs`.
You can drag the jar file on top of QuPath to install the extension.
