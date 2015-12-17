<h1>Vilnius A/D module</h1>

<img src="http://www.grodansparadis.com/vilnius/images/vilnius2_small.png" width="600">

Vilnius A/D module is a CAN4VSCP based module that have four 10-bit A/D channels for 0-5V or 0-10V and also have two 5V I/O channels that can be set as inputs or outputs. General use is to read analog values and as all other VSCP modules you can get the readings reported automatically with a user specified period.

It is also possible to report A/D readings as a VSCP measurement linearized as a floating point value from the formula

measurement = k * A/D-value + m

where k and m are configurable 32-bit floating point constants. You have full control of which event is sent and which unit is used.

This means you can send out any A/D reading as a real unit such as voltage, temperature or in any other SI specified unit.

You can also assign alarm limits so that alarm events are sent when the level goes above a certain value or below a certain value.

Two I/O channels are available. Both can individually be set as inputs or outputs. ON/OFF or TurnOn/TurnOff events can be sent out when I/O change state.

The module can be attached to a standard DIN Rail or be mounted directly on a wall. The mounting enclosures are ordered as separate options when the module is ordered.

The module fully adopts to the VSCP CAN4VSCP specification and can be powered directly over the bus cable with a good 9-28V DC power source. This means there is no need for a separate power cable. VSCP CAN modules are designed to work on a VSCP4CAN bus which use ordinary RJ-45 connectors or use the daisy chain pinhead which can be used to connect modules that are mounted close to each other. For the bus a CAT5 or better twisted pair cable is used. Bus length can have a total length of 500 meters with drops of maximum 24 meters length (up to a total of 120 meters). As for all VSCP4CAN modules the communication speed is fixed at 125 kbps.

All VSCP modules contains information of there own setup, manual, hardware version, manufacturer etc. When VSCP modules are started up they have a default functionality that often is all that is needed to get a working setup. If the module have something to report it will send you an event and if it is setup to react on a certain type of event it will do it's work when you send event(s) to it. It does not need to be harder then that. 

<hr>

This project is licensed under the 
<a href="http://creativecommons.org/licenses/by-nc-sa/3.0/">Creative Commons open source license Attribution-NonCommercial-ShareAlike 3.0 Unported</a>. 
Other license options are available by conacting <a href="malto:info@grodansparadis.com">Paradis of the Frog AB</a>

