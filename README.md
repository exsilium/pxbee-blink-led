# pxbee-blink-led
Programmable XBee Blink Led project that can be built under Linux or Mac OS X. Meant to be used as a boilerplate for new projects without running CodeWarrior.

# Getting Started

## Linux 32bit

`make`

## Linux 64bit

You need to install 32bit compatibility. For example in Ubuntu:

`sudo apt-get install lib32stdc++6`

Verify that the compiler is able to execute:

`./hc08c/bin/chc08 -Lic`

You should be able to compile the project:

`make`

## Mac OS X

As the project depends on the Linux 32bit compiler/linker, the OS X compatibility is achieved through [Docker](https://www.docker.com). You need to have a working Docker installation prior to building this project. To get started, download [Docker](http://docker.io). After you have a working Docker environment (you can successfully run: `docker version`). You can build the compiler image included in this project:

`make builddocker`

After this you can compile the project by executing:

`make dall`

# Outcome

The expected outcome of the compiler and linker will be an .abs file that is input to the burner that will generate the final application binary `obj/blink_led.bin` and in Motorola format application coupled with the bootloader `obj/blink_led.s19`. Use these files to test the application on hardware.

The application will blink a LED connected to pin 7 with 125ms interval.

# Cleaning

`make clean`

# Taking it forward

- `include/xbee_config.h` - This is the Programmable XBEE Project settings
- `src/main.c` - The main() loop

# License

Source files include a header of copyright and license.

Includes the full [Digi](http://www.digi.com) XBee SDK version 1.6.0 sources (latest at the time of commit).

Includes the necessary build binaries:
```
HI-CROSS+ ANSI-C Compiler for HC08 V-5.0.39, Dec 13 2011
HI-CROSS+ SmartLinker V-5.0.48, Dec 13 2011
HI-CROSS+ Burner V-5.0.16, Dec 13 2011
(c) Copyright Freescale 1987-2010
```
