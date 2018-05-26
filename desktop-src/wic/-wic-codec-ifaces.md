---
Description: This section contains information about the Windows Imaging Component (WIC) interfaces.
ms.assetid: 542a6194-38fd-4592-bc25-5a41f5cd9cb7
title: Interfaces
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Interfaces

This section contains information about the Windows Imaging Component (WIC) interfaces.

## In this section



| Topic                                                                                                    | Description                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| [**IWICBitmap**](/windows/win32/Wincodec/nn-wincodec-iwicbitmap?branch=master)<br/>                                                   | Defines methods that add the concept of writeability and static in-memory representations of bitmaps to [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master). <br/>                                                                                                                                                               |
| [**IWICBitmapClipper**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapclipper?branch=master)<br/>                                     | Exposes methods that produce a clipped version of the input bitmap for a specified rectangular region of interest.<br/>                                                                                                                                                                                                              |
| [**IWICBitmapCodecInfo**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapcodecinfo?branch=master)<br/>                                 | Exposes methods that provide information about a particular codec.<br/>                                                                                                                                                                                                                                                              |
| [**IWICBitmapCodecProgressNotification**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapcodecprogressnotification?branch=master)<br/> | Exposes methods used for progress notification for encoders and decoders.<br/>                                                                                                                                                                                                                                                       |
| [**IWICBitmapDecoder**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapdecoder?branch=master)<br/>                                     | Exposes methods that represent a decoder.<br/>                                                                                                                                                                                                                                                                                       |
| [**IWICBitmapDecoderInfo**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapdecoderinfo?branch=master)<br/>                             | Exposes methods that provide information about a decoder.<br/>                                                                                                                                                                                                                                                                       |
| [**IWICBitmapEncoder**](/windows/win32/wincodec/nn-wincodec-iwicbitmapencoder?branch=master)<br/>                                     | Defines methods for setting an encoder's properties such as thumbnails, frames, and palettes.<br/>                                                                                                                                                                                                                                   |
| [**IWICBitmapEncoderInfo**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapencoderinfo?branch=master)<br/>                             | Exposes methods that provide information about an encoder.<br/>                                                                                                                                                                                                                                                                      |
| [**IWICBitmapFlipRotator**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapfliprotator?branch=master)<br/>                             | Exposes methods that produce a flipped (horizontal or vertical) and/or rotated (by 90 degree increments) bitmap source. Rotations are done before the flip.<br/>                                                                                                                                                                     |
| [**IWICBitmapFrameDecode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframedecode?branch=master)<br/>                             | Defines methods for decoding individual image frames of an encoded file.<br/>                                                                                                                                                                                                                                                        |
| [**IWICBitmapFrameEncode**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapframeencode?branch=master)<br/>                             | Represents an encoder's individual image frames.<br/>                                                                                                                                                                                                                                                                                |
| [**IWICBitmapLock**](/windows/win32/Wincodec/nn-wincodec-iwicbitmaplock?branch=master)<br/>                                           | Exposes methods that support the [**Lock**](/windows/win32/Wincodec/nf-wincodec-iwicbitmap-lock?branch=master) method.<br/>                                                                                                                                                                                                                                             |
| [**IWICBitmapScaler**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapscaler?branch=master)<br/>                                       | Represents a resized version of the input bitmap using a resampling or filtering algorithm.<br/>                                                                                                                                                                                                                                     |
| [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master)<br/>                                       | Exposes methods that refers to a source from which pixels are retrieved, but cannot be written back to.<br/>                                                                                                                                                                                                                         |
| [**IWICBitmapSourceTransform**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsourcetransform?branch=master)<br/>                     | Exposes methods for offloading certain operations to the underlying [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master) implementation.<br/>                                                                                                                                                                                     |
| [**IWICColorContext**](/windows/win32/Wincodec/nn-wincodec-iwiccolorcontext?branch=master)<br/>                                       | Exposes methods for color management.<br/>                                                                                                                                                                                                                                                                                           |
| [**IWICColorTransform**](/windows/win32/Wincodec/nn-wincodec-iwiccolortransform?branch=master)<br/>                                   | Exposes methods that transforms an [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master) from one color context to another.<br/>                                                                                                                                                                                                   |
| [**IWICComponentFactory**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwiccomponentfactory?branch=master)<br/>                               | Exposes methods that create components used by component developers. This includes metadata readers, writers and other services for use by codec and metadata handler developers.<br/>                                                                                                                                               |
| [**IWICComponentInfo**](/windows/win32/Wincodec/nn-wincodec-iwiccomponentinfo?branch=master)<br/>                                     | Exposes methods that provide component information.<br/>                                                                                                                                                                                                                                                                             |
| [**IWICDdsDecoder**](/windows/win32/Wincodec/nn-wincodec-iwicddsdecoder?branch=master)<br/>                                                      | Provides information and functionality specific to the DDS image format.<br/>                                                                                                                                                                                                                                                        |
| [**IWICDdsEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicddsencoder?branch=master)<br/>                                                      | Enables writing DDS format specific information to an encoder.<br/>                                                                                                                                                                                                                                                                  |
| [**IWICDevelopRaw**](/windows/win32/Wincodec/nn-wincodec-iwicdevelopraw?branch=master)<br/>                                           | Exposes methods that provide access to the capabilites of a raw codec format.<br/>                                                                                                                                                                                                                                                   |
| [**IWICDevelopRawNotificationCallback**](/windows/win32/Wincodec/nn-wincodec-iwicdeveloprawnotificationcallback?branch=master)<br/>   | Exposes a callback method for raw image change nofications.<br/>                                                                                                                                                                                                                                                                     |
| [**IWICDdsFrameDecode**](/windows/win32/Wincodec/nn-wincodec-iwicddsframedecode?branch=master)<br/>                                              | Provides access to a single frame of DDS image data in its native [**DXGI\_FORMAT**](https://msdn.microsoft.com/library/windows/desktop/bb173059) form, as well as information about the image data.<br/>                                                                                                                                                               |
| [**IWICEnumMetadataItem**](/windows/win32/Wincodec/nn-wincodec-iwicenummetadataitem?branch=master)<br/>                               | Exposes methods that provide enumeration services for individual metadata items.<br/>                                                                                                                                                                                                                                                |
| [**IWICFastMetadataEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicfastmetadataencoder?branch=master)<br/>                         | Exposes methods used for in-place metadata editing. A fast metadata encoder enables you to add and remove metadata to an image without having to fully re-encode the image.<br/>                                                                                                                                                     |
| [**IWICFormatConverter**](/windows/win32/Wincodec/nn-wincodec-iwicformatconverter?branch=master)<br/>                                 | Represents an [**IWICBitmapSource**](/windows/win32/Wincodec/nn-wincodec-iwicbitmapsource?branch=master) that converts the image data from one pixel format to another, handling dithering and halftoning to indexed formats, palette translation and alpha thresholding. <br/>                                                                                         |
| [**IWICFormatConverterInfo**](/windows/win32/Wincodec/nn-wincodec-iwicformatconverterinfo?branch=master)<br/>                         | Exposes methods that provide information about a pixel format converter.<br/>                                                                                                                                                                                                                                                        |
| [**IWICImageEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicimageencoder?branch=master)<br/>                                                  | Encodes [**ID2D1Image**](https://msdn.microsoft.com/library/windows/desktop/hh446803) interfaces to an [**IWICBitmapEncoder**](-wic-imp-iwicbitmapencoder.md). <br/>                                                                                                                                                                                                        |
| [**IWICImagingFactory**](/windows/win32/Wincodec/nn-wincodec-iwicimagingfactory?branch=master)<br/>                                   | Exposes methods used to create components for the WIC such as decoders, encoders and pixel format converters.<br/>                                                                                                                                                                                                                   |
| [**IWICImagingFactory2**](/windows/win32/Wincodec/nn-wincodec-iwicimagingfactory2?branch=master)<br/>                                            | An extension of the WIC factory interface that includes the ability to create an [**IWICImageEncoder**](/windows/win32/Wincodec/nn-wincodec-iwicimageencoder?branch=master). <br/>                                                                                                                                                                                                 |
| [**IWICJpegFrameDecode**](/windows/win32/Wincodec/nn-wincodec-iwicjpegframedecode?branch=master)<br/>                                            | Exposes methods for decoding JPEG images. Provides access to the Start Of Frame (SOF) header, Start of Scan (SOS) header, the Huffman and Quantization tables, and the compressed JPEG JPEG data. Also enables indexing for efficient random access. <br/>                                                                           |
| [**IWICJpegFrameEncode**](/windows/win32/Wincodec/nn-wincodec-iwicjpegframeencode?branch=master)<br/>                                            | Exposes methods for writing compressed JPEG scan data directly to the WIC encoder's output stream. Also provides access to the Huffman and quantization tables.<br/>                                                                                                                                                                 |
| [**IWICMetadataBlockReader**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatablockreader?branch=master)<br/>                         | Exposes methods that provide access to all of the codec's top level metadata blocks.<br/>                                                                                                                                                                                                                                            |
| [**IWICMetadataBlockWriter**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatablockwriter?branch=master)<br/>                         | Exposes methods that enable the encoding of metadata. This interface is implemented by the decoder and its image frames.<br/>                                                                                                                                                                                                        |
| [**IWICMetadataHandlerInfo**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatahandlerinfo?branch=master)<br/>                         | Exposes methods that provide basic information about the registered metadata handler.<br/>                                                                                                                                                                                                                                           |
| [**IWICMetadataQueryReader**](/windows/win32/Wincodec/nn-wincodec-iwicmetadataqueryreader?branch=master)<br/>                         | Exposes methods for retrieving metadata blocks and items from a decoder or its image frames using a metadata query expression.<br/>                                                                                                                                                                                                  |
| [**IWICMetadataQueryWriter**](/windows/win32/Wincodec/nn-wincodec-iwicmetadataquerywriter?branch=master)<br/>                         | Exposes methods for setting or removing metadata blocks and items to an encoder or its image frames using a metadata query expression.<br/>                                                                                                                                                                                          |
| [**IWICMetadataReader**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatareader?branch=master)<br/>                                   | Exposes methods that provide access to underlining metadata content. This interface is implemented by independent software vendors (ISVs) to create new metadata readers.<br/>                                                                                                                                                       |
| [**IWICMetadataReaderInfo**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatareaderinfo?branch=master)<br/>                           | Exposes methods that provide basic information about the registered metadata reader.<br/>                                                                                                                                                                                                                                            |
| [**IWICMetadataWriter**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatawriter?branch=master)<br/>                                   | Exposes methods that provide access to writing metadata content. This is implemented by ISVs to create new metadata writers.<br/>                                                                                                                                                                                                    |
| [**IWICMetadataWriterInfo**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicmetadatawriterinfo?branch=master)<br/>                           | Exposes methods that provide basic information about the registered metadata writer.<br/>                                                                                                                                                                                                                                            |
| [**IWICPalette**](/windows/win32/Wincodec/nn-wincodec-iwicpalette?branch=master)<br/>                                                 | Exposes methods for accessing and building a color table, primarily for indexed pixel formats.<br/>                                                                                                                                                                                                                                  |
| [**IWICPersistStream**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicpersiststream?branch=master)<br/>                                     | Exposes methods that provide additional load and save methods that take [**WICPersistOptions**](/windows/win32/Wincodecsdk/ne-wincodecsdk-wicpersistoptions?branch=master).<br/>                                                                                                                                                                                              |
| [**IWICPixelFormatInfo**](/windows/win32/Wincodec/nn-wincodec-iwicpixelformatinfo?branch=master)<br/>                                 | Exposes methods that provide information about a pixel format.<br/>                                                                                                                                                                                                                                                                  |
| [**IWICPixelFormatInfo2**](/windows/win32/Wincodec/nn-wincodec-iwicpixelformatinfo2?branch=master)<br/>                               | Extends [**IWICPixelFormatInfo**](/windows/win32/Wincodec/nn-wincodec-iwicpixelformatinfo?branch=master) by providing additional information about a pixel format.<br/>                                                                                                                                                                                                 |
| [**IWICPlanarBitmapFrameEncode**](/windows/win32/Wincodec/nn-wincodec-iwicplanarbitmapframeencode?branch=master)<br/>                            | Allows planar component image pixels to be written to an encoder.<br/>                                                                                                                                                                                                                                                               |
| [**IWICPlanarBitmapSourceTransform**](/windows/win32/Wincodec/nn-wincodec-iwicplanarbitmapsourcetransform?branch=master)<br/>                    | Provides access to planar Y CbCr pixel formats where pixel components are stored in separate component planes.<br/>                                                                                                                                                                                                                  |
| [**IWICPlanarFormatConverter**](/windows/win32/Wincodec/nn-wincodec-iwicplanarformatconverter?branch=master)<br/>                                | Allows a format converter to be initialized with a planar source.<br/>                                                                                                                                                                                                                                                               |
| [**IWICProgressCallback**](/windows/win32/Wincodec/nn-wincodec-iwicprogresscallback?branch=master)<br/>                               | [**IWICProgressCallback**](/windows/win32/Wincodec/nn-wincodec-iwicprogresscallback?branch=master) interface is documented only for compliance; its use is not recommended and may be altered or unavailable in the future. Instead, and use [**RegisterProgressNotification**](/windows/win32/Wincodec/nf-wincodec-iwicbitmapcodecprogressnotification-registerprogressnotification?branch=master). <br/> |
| [**IWICProgressiveLevelControl**](/windows/win32/Wincodec/nn-wincodec-iwicprogressivelevelcontrol?branch=master)<br/>                 | Exposes methods for obtaining information about and controlling progressive decoding.<br/>                                                                                                                                                                                                                                           |
| [**IWICStream**](/windows/win32/Wincodec/nn-wincodec-iwicstream?branch=master)<br/>                                                   | Represents a WIC stream for referencing imaging and metadata content.<br/>                                                                                                                                                                                                                                                           |
| [**IWICStreamProvider**](/windows/win32/Wincodecsdk/nn-wincodecsdk-iwicstreamprovider?branch=master)<br/>                                   | Exposes methods for a stream provider.<br/>                                                                                                                                                                                                                                                                                          |



 

 

 



