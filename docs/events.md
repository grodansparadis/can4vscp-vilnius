

Here the events sent by the module is described.

 | Event |Description |
 |-------|-------------|
 | [CLASS1.DATA (15) Type=2, A/D Value](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.data?id=type2) | Input/Output data steam event sent on regular intervals if activated.<br><br>**Byte 0:** *0b01100000* + sensoridx (0x60-0x63) for integer.<br>**Byte 1:** 0<br>**Byte 2:** 0<br>**Byte 3:** MSB of A/D value<br>**Byte 4:** LSB of A/D value. |
  | [CLASS1.MEASUREMENT (10) Type=x, Configurable](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.measurement) | Input/Output data steam event sent on regular intervals if activated.<br><br>**Byte 0:** *0b011uuiii* where [0101]{.underline} is floating point, [uu]{.underline} is configured unit for the selected VSCP type, [iii]{.underline} is channel 0-3.<br>**Byte 1-4:** 32-bit floating point value in big endian format. |
  | [CLASS1.ALARM (1) Type=2, Alarm occurred](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.alarm?id=type2) | If an alarm is armed this event is sent when it occurs and the corresponding alarm bit is set in the alarm register.<br><br>**Byte 0** - Channel 0x00-0x03 for low alarm or with bit 7 set to indicate high alarm (0x80-0x83)<br>**Byte 1** - Zone for module.<br>**Byte 2** - Sub zone for channel or sub zone for module if channel sub zone is zero.<br> |
| [CLASS1.INFORMATION (20) Type=3, On](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.information?id=type3) | An I/O channel has been set to its ON position. For an output this means that it has been set high. For a channel set as an input it means the channel input turned high. The channel is checked every second for a change. |
| [CLASS1.INFORMATION (20) Type=4, Off](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.information?id=type4) | An I/O channel has been set to its OFF position. For an output this means that it has been set low. For a channel set as an input it means the channel input turned low. The channel is checked every second for a change. |
| [CLASS1.CONTROL (30) Type=5, TurnOn](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.control?id=type5) | An I/O channel has been set to its ON position. The channel is checked every second for a change. This is only valid for a channel configured as input. |
| [CLASS1.CONTROL (30) Type=6, TurnOff](https://grodansparadis.github.io/vscp-doc-spec/#/./class1.control?id=type6) | An I/O channel has been set to its OFF position. The channel is checked every second for a change. This is only valid for a channel configured as input. |

[filename](./bottom-copyright.md ':include')
