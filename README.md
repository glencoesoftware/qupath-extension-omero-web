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

## Compatibility

The extension is intended for use with QuPath v0.5 and v0.6. 

## Relationship to Official QuPath Extension

This extension is a fork of the original QuPath OMERO extension, maintained by Glencoe Software. 

While the [QuPath community extension](https://github.com/qupath/qupath-extension-omero) has recently been updated to support similar features, this repository is maintained to ensure maximum stability and performance for **OMERO Plus** environments using Glencoe Software's microservices.

## Docs

General documentation for working with OMERO in QuPath can be found at https://qupath.readthedocs.io/en/0.6/docs/advanced/omero.html.

> **Note:** The official QuPath documentation refers to the standard community extension. While the user installation, interface, and general workflows (e.g., browsing projects, importing images) are similar, the backend connectivity mechanisms and image retrieval differ in this version.
