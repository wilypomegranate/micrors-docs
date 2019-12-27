# Simple and Safe

## Intro

Abstractions in micrors should be both simple and safe.
The general expected audience are those who want to get hardware
working with their board, but not spend a lot of time in the specific
weeds. This means these abstractions aren't meant to tweak every
knob on a board. Instead abstractions should provide a way of making
a variety of boards work the same way with the same code. These
abstractions should also allow for easy implementation of I/O devices
across boards.

Safety is important too. Lots of C/C++ libraries exist for what
this project is trying to accomplish, but few of them are safe
and generally have lots of difficult to debug undefined behavior.
The guiding principle here is that it should be hard to do the
wrong thing and zero-cost compile-time abstractions should be used
whenever possible to help the developer.

## Required abstractions

These are the kinds of abstractions that should be implemented.

* Digital analog inputs and outputs.
* Analog inputs
* PWM(pulse-width modulation)
* Serial input and output.
* I2C
* SPI

## I/O device abstractions

I/O devices should also have provided implementations. Ideally these
should be put into separate crates and could be installed as the user
wishes.

Some of the devices that would need implementations to be useful.

* Serial WiFi(e.g. AT commands for ESP8266)
* LCD Displays
* OLED Displays
* Keypads
* SD Card Reader
* Temperature and other sensors

These are only a few and the list will keep growing. The hope is to
implement a some of these to start with to make a reasonable PoC and
provide some immediate value.

## TBD

These are just a starting point. One of the main goals here is to create
abstractions that would make I/O device creation easy and portable.
This will rely heavily on HAL implementations that already exist
as well as new abstractions on top of them to simplify device
development.
