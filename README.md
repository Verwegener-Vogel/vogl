# vogl
## Solar Powered Embedded Micropower Bird Youth Surveillance

![great tit watching you!](https://upload.wikimedia.org/wikipedia/commons/thumb/3/3c/Great_Tit_%28Parus_major%29_1.jpg/800px-Great_Tit_%28Parus_major%29_1.jpg)

### Aim 
Watch breeding birds illuminated by IR leds. Trigger camera shots or short films on movement. Whole setup is
self powered by a solar panel. Low power consumption is a big priority.

Infrared light is not visible by birds. A small array of IR leds gives the webcam the required lightening.

### Required hardware hacks
The webcam needs its IR light filter removed. The el cheapo cam I used from Aliexpress had the filter on its backside. The
extraction of the filter was easy after removal of the webcam casing.

Supposedly, a more expensive webcam may be harder to modify.

### Used hardware
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

### Prototype
The prototype is aimed at my local birds. The nest was used by a [great tit](https://en.wikipedia.org/wiki/Great_tit) last year.

### Power consumption of various embedded boards
|Board|Consumption in mW|Source|
|-----|----------:|------|
|Arduino Yun|~1200|http://playground.arduino.cc/Hardware/Yun#power_consumption|
|Raspberry Pi 3|2900|https://www.raspberrypi.org/magpi/raspberry-pi-3-specs-benchmarks/|
|Intel Edison|35 in standby|https://www.adafruit.com/datasheets/EdisonDatasheet.pdf|

Note: Power consumption varies between idling, using the integrated WiFi and booting up. I tried to get 
numbers for idling with WiFi turned on.

### Power consumption of prototype setup with solar augmentation

A simpliefied setup with a rechargable lithium battery with 7.4Wh at 3,7V is able to power the Edison in its breakout
board configuration for roughly 58 hours resulting in a net total of 128mW. The battery was charged in between by 
a solar panel.

This is not in line with the power consumption from the datasheet. There is no way the additional led on the buck
regulator and charging circuit could be responsible. The efficiency of the regulator is claimed to be >90%.

According to [this source](https://scivision.co/measured-power-consumption-of-intel-edison/) the Edison without any
energy harvesting is pulling more power: up to 944mW!

A possible explanation could be the active WiFi or the used firmware (Ubilinux).

### Overview
![Vogl Overview](https://github.com/barde/vogl/raw/master/overview.png)

Note: This overview does not contain the multi LED setup and the transistor. This overview is just for.. well overview.

### Schematic
![Vogl Schematic](https://github.com/barde/vogl/raw/master/schematic.png)

### Prototype

Smells like victory! A picture of the first complete prototype working on solar power. The red LED was installed for debugging
purposes as I my eyes do not perceive the IR leds.

![Vogl Prototype](https://github.com/barde/vogl/raw/master/vogl_protoype_setup.jpg)

### Software Installalation and Setup
This installation instruction is based on an Intel Edison with [Ubilinux](http://www.emutexlabs.com/ubilinux) flashed. 
According to your used board you should adapt the following commands to suit your needs.

```
echo 'export PYTHONPATH=$PYTHONPATH:$(dirname $(find /usr/local -name mraa.py))' | sudo tee -a /etc/profile
```
for setting the correct PYTHONPATH for the libmraa module for every user on the Edison.


### Naming
Vogl is a [recursive acronym](https://en.wikipedia.org/wiki/Recursive_acronym) for
**V**ogl
**O**bservation
**G**aining
**L**aboratory
and also means *bird* in German despite missing a vowel. For completeness, the correct wording
would be *Vogel*.

### Publisher
Part of the projects which are created by: Verwegener Vogel e.V. , a society of bird-loving-people 
