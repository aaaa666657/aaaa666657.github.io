# QTCreator Using on OS X:  dyld: Symbol not found: __cg_jpeg_resync_to_restart


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
