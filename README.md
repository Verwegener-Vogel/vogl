# vogl
##Solar Powered Embedded Micropower Bird Youth Surveillance

###Aim 
Watch breeding birds illuminated by IR leds. Trigger camera shots or short films on movement. Whole setup is
self powered by a solar panel. Low power consumption is a big priority.

Infrared light is not visible by birds. A small array of IR leds gives the webcam the required lightening.

###Required hardware hacks
The webcam needs its IR light filter removed. The el cheapo cam I used from Aliexpress had the filter on its backside. The
extraction of the filter was easy after removal of the webcam casing.

Supposedly, a more expensive webcam may be harder to modify.

###Used hardware
|Hardware|Requirement|Price|My Source|
|--------|-----------|----:|------|
|Embedded board|Low power usage, able of running Linux, GPIO, USB host|from $40 upwards||
|USB webcam|Must be supported by Video4Linux|$3|Aliexpress|
|PIR sensor||$2|Aliexpress|
|Solar Panel|Scaled according to total power consumption||Remains from other projects|
|rechargable lithium batteries|Scaled according to total power consumption||Old RF-toys or mobile phones|
|step up converter|Should ouput a clean voltage from the solar charger with high efficiency|$5|Aliexpress|
|LiIon charger|Could be done with basic parts|$20|https://www.adafruit.com/products/390|
|IR Led||$1 for 5|Aliexpress|
|Resistor|Scaled according to your Vbus|parts box|

###Prototype
The prototype is aimed at my local birds. The nest was used by a [great tit](https://en.wikipedia.org/wiki/Great_tit) last year.

###Power consumption of various embedded boards
|Board|Consumption in mW|Source|
|-----|----------:|------|
|Arduino Yun|1200|http://playground.arduino.cc/Hardware/Yun#power_consumption|
|Raspberry Pi 3|2900|https://www.raspberrypi.org/magpi/raspberry-pi-3-specs-benchmarks/|
|Intel Edison|680|https://www.adafruit.com/datasheets/EdisonDatasheet.pdf|

Note: Power consumption varies between idling, using the integrated WiFi and booting up. I tried to get 
numbers for idling with WiFi turned on.

###Power consumption of parts
(to be measured)

###Overview
![Vogl Overview](https://github.com/barde/vogl/raw/master/overview.png)

###Schematic
![Vogl Schematic](https://github.com/barde/vogl/raw/master/schematic.png)
