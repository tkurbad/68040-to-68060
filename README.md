# 68040-to-68060

This is a 68040 to 68060 adapter. It allows you to physically connect
a 68060 CPU to any CPU socket that fits a 68040 CPU, assuming there
is enough physical clearance.

## About

This work is a derivative of the 68040 to 68060 adapter by
[reinauer](https://github.com/reinauer/68040-to-68060) which is a derivative
of the work of richx from the English Amiga Board which in turn is based on a
2013 design from the a1k.org forum.

At the time of this writing, the original kicad project
can be found at https://eab.abime.net/showthread.php?t=100942

The differences between this design and the original KiCAD
version are (My contributions in **bold**):

  - Moved the inner 4-pin connector in line with the substrate
    and the pins of the PGA socket. This allows to use sockets
    with 5 rows of pins without using a dremel.
  - Move the capacitors a bit more to the center to make space
    for 5 pin row sockets.
  - use 0603 4.7k resistor networks instead of 0805 resistors to
    clean up the space and have fewer parts to solder
  - move all three diodes in line for easier soldering
  - **widen all socket pin holes from 1.4 mm to 1.5 mm to allow inserting
    single socket pins further down to gain some length for better contact**
  - **for the upper PCB, swap the GND and 3.3V layers to have the GND layer on
    top**
  - **use 0805 sized capacitors**
  - **substitute the THT voltage regulator by its SMD variant**
  - **remove some unnecessary vias, do some rerouting, don't use insanely wide
    traces**
  - **write out all contributors on the silk screen**

## Assembly

The two PCBs need to be separated before assembly.

It is possible to build these with 0.1" pitch breakaway female
pin headers. However, is is much easier to solder full PGA sockets.
The top one has 206 pins, the bottom one 179. That is a large number
of breakaway pins if you go down that route.

'NOTE:' The bottom of the top PCBs has circles around some of the
pins. These are carrying VCC and must not make contact to the bottom
PCB or you will operate your 68060 at 5V instead of 3.3V. You might
destroy your processor this way, so be careful.

During assembly, you have the choice to either cut those pins, or you
can use an intermediate socket with those pins removed. This will increase
the height of your adapter by a few mm and increase the price because
you will need a third PGA socket, but make the assembly process a lot
cleaner and more reproducible.

Further reading on my adventures building these:
* [68040 to 68060 – Upformation](https://amiga.technology/2021/01/18/68040-to-68060-upformation/)
* [Finding common GND](https://amiga.technology/2021/02/25/finding-common-gnd/)

## Bill of Materials

Here's the [Bill of Materials (BOM)](https://htmlpreview.github.io/?https://raw.githubusercontent.com/tkurbad/68040-to-68060/main/bom.html).

## Make your own

Design by Stefan Reinauer

* [PCBWay](https://www.pcbway.com/project/shareproject/68040_to_68060_adapter.html)
* [OSHpark](https://oshpark.com/shared_projects/q8HjYPrh)

This fork's design (don't know if it'll work this way)

* [JLCPCB](https://cart.jlcpcb.com/quote?uploadNum=e3c08ddedc5e4b5f9d1ccca74e3f3c49&businessType=example&fileName=Gerber)

## Credits

Big thank you goes to richx, who did the original KiCAD version
and to Mozart, Lemmy and Matze from the a1k.org forum for the
Eagle version before that.

