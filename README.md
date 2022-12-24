# pividbell - the Raspberry Pi Video Doorbell

This is a work-in-progress smart doorbell, powered by a Pi 0W.

## Progress

Progress is tracked through #1. So far, no hardware prototypes have been built. 

## Planned Features

These features have not yet been implemented, and as such implementation details may change later on.

* Video streaming with night vision (using Pi Camera) - RTSP feed for integration with NVRs such as Frigate.
* Intercom functionality - likely as a SIP phone that rings a predetermined extension when doorbell pressed.
* Optional NFC - intended for monitoring people coming and going for home automation platforms. [^1]
* Optional door release & status - the ability to drive a solenoid to open a door and a reed switch to determine if a door is open or not. [^2]
* Addressable RGB ~~for gamers~~ to indicate button position and provide feedback.

## Hardware Design

### General background

The doorbell is powered by a Pi Zero W, with power and all connections being provided over its 40-pin GPIO header. A Pi NoIR camera, combined with several IR LEDs, provides the video feed and night vision capabilities. Audio input and output is handled by a I<sup>2</sup>S ADC and DAC respectively.


### Button

This doorbell uses a capactive button, rather than a physical one. This has a few benefits, including:

* Capacitive button tends to be cheaper than a water resistant pushbutton
* Fewer points of ingress
* Theoretically, better longevity - though most water resistant pushbuttons are also rated for very high number of cycles, so this is not as important

Once the doorbell prototype has been fabricated and assembled, the possibility of a contactless doorbell (ie, configuring the capacitive controller to be more sensitive to trigger if approached to within a centimetre or two) will also be investigated. This could reduce fingerprints and reduce cleaning requirements.

## Case Design

This will be a recessed doorbell, re-using the recess box of an existing (and in my case, already installed) doorbell. This section of the README will be expanded further once the housing has been designed.

[^1]: This should not be considered secure; whilst it *could* conceivably be used as authentication for the door release functionality, it is strongly recommended against.
[^2]: Again, this may not be secure - similar to many commercially available doorbells, it would be possible to open the doorbell (with the correct tools) and simply short the wires to trigger the door release.