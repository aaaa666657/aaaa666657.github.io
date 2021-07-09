---
title: "QTCreator Using on OS X:  dyld: Symbol not found: __cg_jpeg_resync_to_restart"
subtitle: ""
date: 2021-07-09T10:02:01+08:00
lastmod: 2021-07-09T10:02:01+08:00
draft: false
author: "KAI"
authorLink: ""
description: ""

tags: [QT]
categories: []

hiddenFromHomePage: false
hiddenFromSearch: false

featuredImage: ""
featuredImagePreview: ""

toc:
  enable: true
math:
  enable: false
lightgallery: false
license: ""
---

<!--more-->
## Using on OS X: dyld: Symbol not found: __cg_jpeg_resync_to_restart
- 原因在於 mac 上的 lib 有未對上之情況

- 解決辦法 : delete the symlinks and create new symlinks to right libs
```bash
mv libjpeg.dylib libjpeg.dylib.bak 

ln -s /System/Library/Frameworks/ImageIO.framework/Resources/libJPEG.dylib libJPEG.dylib                                                                       

mv libtiff.dylib.backup libtiff.dylib.bak

ln -s /System/Library/Frameworks/ImageIO.framework/Resources/libTIFF.dylib libTIFF.dylib 

mv libpng.dylib libpng.dylib.bak   

ln -s /System/Library/Frameworks/ImageIO.framework/Resources/libPng.dylib libPNG.dylib                  

mv libgif.dylib libgif.dylib.bak                                                                                                                              

ln -s /System/Library/Frameworks/ImageIO.framework/Resources/libGif.dylib libGIF.dylib