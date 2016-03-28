# vogl
##Solar Powered Embedded Micropower Bird Youth Surveillance

###Aim 
Watch breeding birds illuminated by IR leds. Trigger camera shots or short films on movement. Whole setup is
self powered by a solar panel. Low power consumption is a big priority.

Infrared light is not visible by animals. A small array of IR leds gives the webcam the required lightening.

###Required hacks
The webcam needs its IR light filter removed. The el cheapo cam I used from Aliexpress had the filter on its backside. The
removal was easy after removal of the webcam casing.

Supposedly, a more expensive webcam may be harder to modify.

###Used tools
 Embedded board running Debian, USB V4L webcam, PIR sensor, 5W solar panel, 4.2V lithium batteries, Step up converter

###Overview
![Vogl Overview](https://github.com/barde/vogl/raw/master/overview.png)

###Schematic
![Vogl Schematic](https://github.com/barde/vogl/raw/master/schematic.png)
