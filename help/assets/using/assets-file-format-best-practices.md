---
title: Assets file format best practices
seo-title: Assets file format best practices
description: Best practices for file support in AEM Assets.
seo-description: Best practices for file support in AEM Assets.
uuid: 0f6910b1-7a70-4ff4-9008-0a83f5bc052d
contentOwner: asgupta
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
discoiquuid: 3e73b79c-53a7-4a5c-b9ea-cffaca00fa96
index: y
internal: n
snippet: y
---

# Assets file format best practices{#assets-file-format-best-practices}

AEM Assets supports many proprietary and third-party file format libraries to cater to diverse file support requirements of users. The supported Adobe libraries include, Adobe Camera Raw, Gibson, Adobe PDF Rasterizer, and Adobe InDesign Server. In addition, AEM Assets supports third-party libraries, including ImageMagick, TwelveMonkeys, and so on.

For the supported file formats, see [Assets supported formats](../../assets/using/assets-formats.md).

## Adobe Camera Raw library {#adobe-camera-raw-library}

For optimal performance, Adobe recommends using Adobe Camera Raw library for:

* RAW
* DNG

The Adobe Camera Raw library supports CMYK color profile as input. However, it generates the output in RGB colorspace and supports output in JPEG format only. It does not retain the source file colorspace (for example CMYK) in the thumbnails.

For more information, see [Camera Raw support](../../assets/using/camera-raw.md) in AEM Assets.

## Adobe PDF Rasterizer library {#adobe-pdf-rasterizer-library}

For best results, Adobe recommends using the Adobe PDF Rasterizer library for the following files:

* Heavy, content intensive PDF files
* AI files with thumbnails not generated out of the box
* For AI files with SPOT (PMS) colors

Thumbnails and previews generated using PDF Rasterizer are better in quality compared to out-of-the-box raster output. The Adobe PDF Rasterizer library does not support any color space conversion. Irrespective of the color space of the source PDF file, Adobe PDF Rasterizer generates RGB output only. 

## Adobe InDesign CC Server {#adobe-indesign-cc-server}

Adobe recommends that you use Adobe InDesign CC Server to extract Adobe InDesign-specific renditions, such as IDML and HTML. For more information, see [Adding AEM assets as references in Adobe InDesign](../../assets/using/managing-linked-subassets.md#addingaemassetsasreferencesinadobeindesign).

## Dynamic Media  {#dynamic-media}

Dynamic Media generates and delivers multiple variations of rich content in real time through its global, scalable, and performance-optimized network. It serves interactive viewing experiences and streamlines the digital campaign management process. For details around enabling Dynamic Media, see [Configuring Dynamic Media](../../assets/using/config-dynamic.md).

Currently, Dynamic Media can support videos up to 20 GB of content per file.

## ImageMagick library {#imagemagick-library}

Adobe recommends using the ImageMagick library in the following scenarios:

* To generate thumbnail renditions for EPS files
* To preserve image profile information
* To preserve transparency
* To process PSD and PSB files

To know how to set up the ImageMagic library in AEM, see [Using ImageMagick](../../assets/using/media-handlers.md#main-pars-title-2). For optimum usage, see [Best Practices for Configuring ImageMagick](../../assets/using/best-practices-for-imagemagick.md).

## Image Transcoding Library {#image-transcoding-library}

The Adobe Imaging Transcoding Library is an image-processing solution that performs core image-handling functions, including image encoding, transcoding, resampling, resizing, and so on.

Imaging Transcoding library supports the following MIME types:

* JPG/JPEG
* PNG (8 bit and 16 bit)
* GIF
* BMP
* TIFF/Compressed TIFF (apart from 32 Bit Tiffs and PTiffs).  
* ICO
* ICN

For details, see [Imaging Transcoding Library](../../assets/using/imaging-transcoding-library.md).