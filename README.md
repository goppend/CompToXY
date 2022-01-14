# Comp to XY
An old-and-busted (but working!) DesignSpark project I made many years ago as PCB design practice. It's intended to convert a component baseband video signal to an XYZ format in a way that it can be viewed on an analog oscilloscope.

Like many existing versions of this project, the main functional component is a LM1881 IC, which provides the CSYNC and VSYNC pulse signals to some analog circuitry in order to form a raster (the X and Y outputs). The Z output is the video input passed through an AD8032 op-amp in an inverting amplifier configuration.

Some pictures of the design:
[The project schematic](pics/schematic.png)
The project schematic.

[The PCB layout](pics/pcb_layout.png)
The PCB layout.

## Test procedure:
Connect the XY outputs to the oscilloscope using a 3.5mm audio jack to stereo RCA cable and RCA to BNC adapters. Red is X and white is Y.
The Z output requires another adapter I didn't have on hand, but ideally would use another RCA cable and RCA to BNC adapter.
Put the oscilloscope in XY mode and adjust the X scale, Y scale, and brightness to appropriate levels. 0.2 V/div is a good starting value in 1X mode, and adjust vernier scales for fine tuning once the picture is visible. AC coupling is necessary on both inputs as well.
Connect any composite video source (I used my SNES with the 240p Test Suite) to the video input.
Set the DC power supply's output to 9V, and connect it to the power inputs as shown below (red is +9V, black is ground).

[The PCB fully connected](pics/1.jpg)
The PCB fully connected.

[Video test output](pics/2.jpg)
Video test output (SMPTE color bars, albeit in grayscale).

[Another test output](pics/3.jpg)
Another test output (monoscope pattern shows distinct distortion across the field).

Bonus:
[SNES DOOM splash screen](pics/4.jpg)
[SNES DOOM E1M1](pics/5.jpg)
Some DOOM footage from my SNES.

## Problems with this design
Since I have moved on to larger-scale projects, I will not be updating this design. However, there are critical issues that are worth bringing up.
 - The schematic shows D1 and D2 facing the wrong way.
 - At the time, transistor arrays were convenient, but those parts are not kept in stock in a large quantity. A redesign using discrete components would be better.
 - Power entry can be more clear. Some input protection would be nice as well, getting the inputs backwards __will__ damage most components.
 - Use more appropriate connectors for the outputs.
 - There are issues with video output, as seen in the test screenshots.
	 - Contrast adjust doesn't do very much except on the very low end of the scale. A log scale potentiometer would be a better fit.
	 - Brightness adjust acts very strange and needs work.
	 - There's nonlinear distortion in the raster output effecting picture quality. This can probably be fixed by adjusting RC values and/or with better transistor selection.
 - Probably more.

Feel free to use this design for any purpose you find useful.
