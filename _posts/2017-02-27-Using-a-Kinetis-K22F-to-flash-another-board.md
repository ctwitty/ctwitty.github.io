---
layout: post
title: Using a Kinetis K22F as a programmer for an external MCU.
---

You can use the [FRDM-K22F](http://www.nxp.com/products/software-and-tools/hardware-development-tools/freedom-development-boards/nxp-freedom-development-platform-for-kinetis-k22-mcus:FRDM-K22F) development board to flash another MCU.  At ~$30, the K22F is a relatively cheap flashing tool.  If [OpenOCD](http://openocd.org/) supports your target board, then you can use that the program your target board.  My target board doesn't have a microUSB interface as it's not a dev board.

The development board contains board a K22 and also a K20DX128VFM5.  The K20 is used to flash the K22 via the OpenSDA microUSB interface, as shown in this diagram which I took from the K22 Reference manual.

<img src="{{ site.url }}/assets/img/k22f-block-diagram.jpg"/>

You can disconnect the K22 from the K20 and then program another board via an SWD debug connector.

1) Cut the J7 trace with an X-acto blade or similar.  You can find it on the back of the board.

See the green box:

<img src="{{ site.url }}/assets/img/IMAG0235-box.jpg" style="width:800px;"/>

2) Remove the jumper on J7.  (Replace it when you want to program the K22 on board.)

<img src="{{ site.url }}/assets/img/IMAG0236.jpg" style="width:800px;"/>

3) Connect from the JTAG interface to the SWD interface on your other board.  Be mindful of where pin 1 is on the cable.

<img src="{{ site.url }}/assets/img/IMAG0239.jpg" style="width:800px;"/>

4) Connect your microusb from your host computer to the OpenSDA port on the K22 dev board.

5) Start up OpenOCD and flash.

So there you have it, a $30 programmer!  And if you feel like programming the K22f onboard, just reconnect J7 and reset power.

Right now I'm using OpenOCD to flash a K17 on a custom board.  More on that soon!

References:
[FRDM K22F Reference manual (pdf)](http://www.nxp.com/assets/documents/data/en/user-guides/FRDMK22FUG.pdf)
