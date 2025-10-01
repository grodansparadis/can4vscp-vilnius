# Vilnius A/D module

This module is part of the [VSCP project](https://www.vscp.org).  It is free to use, modify and sell. The only thing we kindly ask is that improvements and extensions are contributed back to the project (at your will). This to make the project better for everyone. All design files is licensed under the [MIT license](https://en.wikipedia.org/wiki/MIT_License).

<img src="http://www.grodansparadis.com/vilnius/docs/images/vilnius2_small.png" width="600">

## Abstraction

Vilnius A/D module is a CAN4VSCP based module that have four 10-bit A/D channels for 0-5V or 0-10V and also have two 5V I/O channels that can be set as inputs or outputs. General use is to read analog values and as all other VSCP modules you can get the readings reported automatically with a user specified period.

It is also possible to report A/D readings as a VSCP measurement linearized as a floating point value from the formula

measurement = k * A/D-value + m

where k and m are configurable 32-bit floating point constants. You have full control of which event is sent and which unit is used.

This means you can send out any A/D reading as a real unit such as voltage, temperature or in any other SI specified unit.

You can also assign alarm limits so that alarm events are sent when the level goes above a certain value or below a certain value.

Two I/O channels are available. Both can individually be set as inputs or outputs. ON/OFF or TurnOn/TurnOff events can be sent out when I/O change state.

The module can be attached to a standard DIN Rail or be mounted directly on a wall. The mounting enclosures are ordered as separate options when the module is ordered.

The module fully adopts to the VSCP CAN4VSCP specification and can be powered directly over the bus cable with a good 9-28V DC power source. This means there is no need for a separate power cable. VSCP CAN modules are designed to work on a VSCP4CAN bus which use ordinary RJ-45 connectors or use the daisy chain pinhead which can be used to connect modules that are mounted close to each other. For the bus a CAT5 or better twisted pair cable is used. Bus length can have a total length of 500 meters with drops of maximum 24 meters length (up to a total of 120 meters). As for all VSCP4CAN modules the communication speed is fixed at 125 kbps.

All VSCP modules contains information of there own setup, manual, hardware version, manufacturer etc. When VSCP modules are started up they have a default functionality that often is all that is needed to get a working setup. If the module have something to report it will send you an event and if it is setup to react on a certain type of event it will do it's work when you send event(s) to it. It does not need to be harder than that. 

---

## Project files

### User manual
  * [User Manual](https://grodansparadis.github.io/can4vscp-vilnius/#)

### Schematic, PCB, 3D files etc
  * [Schematics reversion B part 1](https://raw.githubusercontent.com/grodansparadis/can4vscp-vilnius/refs/heads/master/eagle/vilnius_sch1_rev_B.png), [part 2](https://raw.githubusercontent.com/grodansparadis/can4vscp-vilnius/refs/heads/master/eagle/vilnius_sch2_rev_B.png)
 * Hardware design files is made in [KiCad](https://kicad.org) and can be found in the `kicad` directory. Valid from reversion B of the hardware.
   * Gerber files for PCB production can be found in the `gerber` directory (in the `kicad` folder).
 * Eagle schema and board files for reversion A and B can be found in the `eagle` directory. They are no longer actively updated.

 ### Firmware

 The firmware is developed in [MPLAB X IDE](https://www.microchip.com/mplab/mplab-x-ide) using the [XC8 compiler](https://www.microchip.com/mplab/compilers).

  * Binary release files is available [here](https://github.com/grodansparadis/can4vscp-vilnius/releases)

### MDF - Module Description File(s)
  * [MDF file version: 10 Release date: 2024-04-25](http://www.eurosource.se/vilnius_1.xml)

### Support
If you need support, please open an issue in the [GitHub repository](https://github.com/grodansparadis/can4vscp-vilnius/issues).

### Buy a ready made modules
You can buy a ready made module from [Grodans Paradis](http://www.grodansparadis.com).

### Project related links
  * [VSCP project](https://www.vscp.org)
  * [VSCP Documentation site](https://docs.vscp.org/)
  * [VSCP Wiki](https://github.com/grodansparadis/vscp/wiki)


