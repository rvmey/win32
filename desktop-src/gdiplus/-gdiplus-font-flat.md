---
Description: Windows GDI+ exposes a flat API that consists of about 600 functions, which are implemented in Gdiplus.dll and declared in Gdiplusflat.h.
ms.assetid: fcc37af2-cd90-42e6-9b7f-20b123f8ab1f
title: Font Functions
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Font Functions

Windows GDI+ exposes a flat API that consists of about 600 functions, which are implemented in Gdiplus.dll and declared in Gdiplusflat.h. The functions in the GDI+ flat API are wrapped by a collection of about 40 C++ classes. It is recommended that you do not directly call the functions in the flat API. Whenever you make calls to GDI+, you should do so by calling the methods and functions provided by the C++ wrappers. Microsoft Product Support Services will not provide support for code that calls the flat API directly. For more information on using these wrapper methods, see [GDI+ Flat API](-gdiplus-flatapi-flat.md).

The following flat API functions are wrapped by the [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) C++ class.

## Font Functions and Corresponding Wrapper Methods



| Flat function                                                                                                                                                     | Wrapper method                                                                                                                                                           | Remarks                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| GpStatus WINGDIPAPI GdipCreateFontFromDC( HDC hdc, GpFont \*\*font )<br/>                                                                                   | [**Font::Font(IN HDC hdc)**](/windows/win32/Gdiplusheaders/?branch=master)                                                                                                          | Creates a [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object based on the GDI font object that is currently selected into a specified device context. This constructor is provided for compatibility with GDI.                                                                                                                                    |
| GpStatus WINGDIPAPI GdipCreateFontFromLogfontA( HDC hdc, GDIPCONST LOGFONTA \*logfont, GpFont \*\*font ) <br/>                                              | [**Font::Font(IN HDC hdc, IN const LOGFONTA\* logfont)**](/windows/win32/Gdiplusheaders/?branch=master)                                                        | Creates a [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object directly from a GDI logical font. The GDI logical font is a **LOGFONTA** structure, which is the one-byte character version of a logical font. This constructor is provided for compatibility with GDI.                                                                              |
| GpStatus WINGDIPAPI GdipCreateFontFromLogfontW( HDC hdc, GDIPCONST LOGFONTW \*logfont, GpFont \*\*font )<br/>                                               | [**Font::Font(IN HDC hdc, IN const LOGFONTW\* logfont)**](/windows/win32/Gdiplusheaders/?branch=master)                                                        | Creates a [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object directly from a GDI logical font. The GDI logical font is a **LOGFONTW** structure, which is the one-byte character version of a logical font. This constructor is provided for compatibility with GDI.                                                                              |
| GpStatus WINGDIPAPI GdipCloneFont(GpFont\* font, GpFont\*\* cloneFont)<br/>                                                                                 | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipCreateFont( GDIPCONST GpFontFamily \*fontFamily, REAL emSize, INT style, Unit unit, GpFont \*\*font )<br/>                          | [**Font::Font( IN const FontFamily \* family, IN REAL emSize, IN INT style, IN Unit unit )**](/windows/win32/Gdiplusheaders/?branch=master) | Creates a [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object based on a font family, a size, a font style, a unit of measurement, and a [**FontCollection**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-fontcollection?branch=master) object.                                                                                                                                     |
| GpStatus WINGDIPAPI GdipCloneFont(GpFont\* font, GpFont\*\* cloneFont)<br/>                                                                                 | [**Font::Font\* Clone() const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-clone?branch=master)                                                                                                         | Creates a new [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object based on this Font object.                                                                                                                                                                                                                                                       |
| GpStatus WINGDIPAPI GdipDeleteFont(GpFont\* font)<br/>                                                                                                      | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipGetFamily(GpFont \*font, GpFontFamily \*\*family)<br/>                                                                              | [**Status Font::GetFamily(OUT FontFamily \*family) const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getfamily?branch=master)                                                                   | Gets the font family on which this font is based.                                                                                                                                                                                                                                                                                               |
| GpStatus WINGDIPAPI GdipGetFontStyle(GpFont \*font, INT \*style)<br/>                                                                                       | [**INT Font::GetStyle() const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getstyle?branch=master)                                                                                                      | Gets the style of this font's typeface                                                                                                                                                                                                                                                                                                          |
| GpStatus WINGDIPAPI GdipGetFontSize(GpFont \*font, REAL \*size)<br/>                                                                                        | [**REAL Font::GetSize() const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getsize?branch=master)                                                                                                       | Returns the font size (commonly called the em size) of this Font object. The size is in the units of this [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object.                                                                                                                                                                                     |
| GpStatus WINGDIPAPI GdipGetFontUnit(GpFont \*font, Unit \*unit)<br/>                                                                                        | [**Unit Font::GetUnit() const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getunit?branch=master)                                                                                                       | Returns the unit of measure of this [**Font**](/windows/win32/gdiplusheaders/nl-gdiplusheaders-font?branch=master) object.                                                                                                                                                                                                                                                           |
| GpStatus WINGDIPAPI GdipGetFontHeight(GDIPCONST GpFont \*font, GDIPCONST GpGraphics \*graphics, REAL \*height)<br/>                                         | [**REAL Font::GetHeight(IN const Graphics \*graphics) const**](/windows/win32/Gdiplusheaders/?branch=master)                                                              | Gets the line spacing of this font in the current unit of a specified [**Graphics**](/windows/win32/gdiplusgraphics/nl-gdiplusgraphics-graphics?branch=master) object. The line spacing is the vertical distance between the base lines of two consecutive lines of text. Thus, the line spacing includes the blank space between lines along with the height of the character itself. |
| GpStatus WINGDIPAPI GdipGetFontHeightGivenDPI(GDIPCONST GpFont \*font, REAL dpi, REAL \*height)<br/>                                                        | [**REAL Font::GetHeight(IN REAL dpi) const**](/windows/win32/Gdiplusheaders/?branch=master)                                                                                    | Gets the line spacing, in pixels, of this font. The line spacing is the vertical distance between the base lines of two consecutive lines of text. Thus, the line spacing includes the blank space between lines along with the height of the character itself.                                                                                 |
| GpStatus WINGDIPAPI GdipGetLogFontA(GpFont \* font, GpGraphics \*graphics, LOGFONTA \* logfontA)<br/>                                                       | [**Status Font::GetLogFontA(IN const Graphics \*g, OUT LOGFONTA \*logfontA) const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getlogfonta?branch=master)                                    | Uses a **LOGFONTA** structure to get the attributes of this Font object.                                                                                                                                                                                                                                                                        |
| GpStatus WINGDIPAPI GdipGetLogFontW(GpFont \* font, GpGraphics \*graphics, LOGFONTW \* logfontW)<br/>                                                       | [**Status Font::GetLogFontW(IN const Graphics \*g, OUT LOGFONTW \*logfontW) const**](/windows/win32/Gdiplusheaders/nf-gdiplusheaders-font-getlogfontw?branch=master)                                    | Uses a **LOGFONTW** structure to get the attributes of this Font object.                                                                                                                                                                                                                                                                        |
| GpStatus WINGDIPAPI GdipNewInstalledFontCollection(GpFontCollection\*\* fontCollection)<br/>                                                                | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipNewPrivateFontCollection(GpFontCollection\*\* fontCollection)<br/>                                                                  | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipDeletePrivateFontCollection(GpFontCollection\*\* fontCollection)<br/>                                                               | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipGetFontCollectionFamilyCount( GpFontCollection\* fontCollection, INT \* numFound )<br/>                                             | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipGetFontCollectionFamilyList( GpFontCollection\* fontCollection, INT numSought, GpFontFamily\* gpfamilies\[\], INT\* numFound )<br/> | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipPrivateAddFontFile( GpFontCollection\* fontCollection, GDIPCONST WCHAR\* filename )<br/>                                            | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |
| GpStatus WINGDIPAPI GdipPrivateAddMemoryFont( GpFontCollection\* fontCollection, GDIPCONST void\* memory, INT length )<br/>                                 | Not called by wrapper methods.<br/>                                                                                                                                | Not implemented.                                                                                                                                                                                                                                                                                                                                |



 

 

 



