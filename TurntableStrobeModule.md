# Introduction #

Retrofit your turntable with this highly accurate, long-lasting LED turntable strobe module, even if your deck already has a strobe.

Why? Many turntables use mains frequency to run their strobes. While on average frequency from your outlet is 60 Hz (or 50 Hz depending), the frequency varies from hour to hour. This module produces a stable strobe. It also uses a long-lasting LED.

Purchase [here on Tindie.com](https://www.tindie.com/products/bot_thoughts/pocket-turntable-strobe/)

# Details #

  * Bright white 5mm LED or use your own (read below)
  * LED strobes at 60.00 Hz (50.00 Hz on request)
  * frequency error less than 0.005% or 0.03 Hz.
  * Input voltage of 3.3V - 5V
  * Four #4 mounting holes
  * Pin headers included for custom wiring
  * Compact 1" long by 3/4" wide (25mm x 20mm), not counting LED

Note that 45 RPM discs for 50.00 Hz strobes cannot exist; the number of dots required is not an integer. Instead, strobe patterns are typically 45.1 rpm. I have been told that some European "45 rpm" discs are actually cut at 45.1 rpm.

# How To Use #

  * Using the included LED, power the module from 3.3VDC to 5VDC.
  * For other LEDs, see LED Power below.
  * Wiring:
    * Either solder wires directly to the module or
    * Use included pin headers and then use female pin connectors
  * Figure out where you're mounting the module
  * Determine how to install the LED based on module location
  * Solder in the LED (you can also mount it remotely with wires
  * Mount module with four screws (size #4 or 3mm) and 4 standoffs
  * Activate the turntable to begin spinning the platter
  * The strobe should be illuminating and 'freezing' the platter marks
  * If the turntable lacks marks, you'll need to get a platter that has them or figure out a way to attach some.
  * Adjust turntable speed until marks stop moving (as applicable)
    * Read the turntable user manual for details
  * You may see the marks repeatedly move left and right a bit
    * That is called 'wow' and some tables have it worse than others

# LED Power #

So you don't like the included white LED? Ok, you can use your own but read these facts first to save some headache.

We're trying to figure out what voltage to supply the module so you don't burn up your fancy purple (or whatever) LED.

First of all, LEDs are rated with a maximum current, typically 20mA. Above this current they burn out.

Second, LEDs drop an effectively fixed amount of voltage regardless of the current running through them. To get an idea, check out [this table on Wikipedia](http://en.wikipedia.org/wiki/Light-emitting_diode#Colors_and_materials).

A third interesting fact is that increasing current has diminishing returns in brightness. While 10mA is a lot brighter than 5mA, 15mA isn't that much brighter than 10mA.

Knowing all this, and knowing about Ohm's law and Kirchoff's current law means you can figure out what the input voltage maximum. Let's target 15mA, assume that the onboard microcontroller "low" signal is 0.5V, and the LED resistor is 100 ohms.

Thus, V = VLED + 1.2, where VLED is the forward voltage drop, VF, for the LED. That gives you in the ballpark of 15mA and, hopefully, keep you well under the typical limit of 20mA if the LED Vf and onboard resistor are at the lower end of their specifications.

# Source Files #

[Schematic & PCB; firmware](http://code.google.com/p/bot-thoughts-blog/source/browse/#svn%2Ftrunk%2FTurntableStrobe)