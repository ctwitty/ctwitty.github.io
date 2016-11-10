---
layout: post
title: Putting an image on the e-ink screen
---

I wanted to try putting different pictures on an e-ink screen.  I am using u8glib, which has a function to draw bitmaps, but how to generate the array of pixels easily?

Luckily, this is easier than I expected.  ImageMagick supports XBM files, which is C source code.  It consists of an unsigned char array of monochrome pixel values and ```#define```s for the width and height of the image.

1) Get an image.

For my image I grabbed a square piece of Hokusai's "The Greate Wave off Kanagawa":

<img src="{{ site.url }}/assets/img/wave.png" style="width:500px;"/>

2) Convert it to an XBM file:

My screen is 200 by 200 pixels.

```
convert wave.png -resize 200x200 wave.xbm
```

3) Copy wave.xbm into source as a header file, inclue it and use it:

```
u8g_DrawXBM(&u8g, 0, 0, wave_width, wave_height, wave_bits);
```

4) Make the image a little nicer (Optional):

Since the e-ink screen is monochromatic and the wave have some fine details, I tried some sharpening.

The image on the left has no sharpening, while the image on the right has heavy sharpening:

<img src="{{ site.url }}/assets/img/wave_no_sharpen.png" style="width:200px;"/>
<img src="{{ site.url }}/assets/img/wave_sharpen.png" style="width:200px;"/>

Image on the left:
```shell
# XBM file for code:
convert wave.png -monochrome -resize 200x200 wave_no_sharpen.xbm
# convert to PNG to display here:
convert wave_no_sharpen.xbm wave_no_sharpen.png
```
Image on the right, using sharpen:
```shell
# XBM
convert wave.png -monochrome -resize 200x200 -sharpen 0x3 wave_sharpen.xbm
# and png
convert wave_sharpen.xbm wave_sharpen.png
```

Image viewers (such as eog on Linux and Preview on OSX) recognize XBM files and will display the picture.  It seems web browers don't, so I generated png's.

The monochrome flag affects the dithering.  It makes a difference when producing XBM's:
<img src="{{ site.url }}/assets/img/wave_sharp_no_monochrome.png" style="width:200px;"/>
<img src="{{ site.url }}/assets/img/wave_sharp_monochrome.png" style="width:200px;"/>

```shell
# left, without
convert wave.png -resize 200x200 -sharpen 0x3 wave2.xbm
convert wave2.xbm wave2.png
# right, with monochrome flag
convert wave.png -monochrome -resize 200x200 -sharpen 0x3 wave1.xbm
convert wave1.xbm wave1.png
```

