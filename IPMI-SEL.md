# IPMI Sensor Event Log

### 171 | 07/20/2020 | 03:45:09 | System Event #0x83 | OEM System boot event | Asserted

- SEL Record ID          : 0170
- Record Type           : 02
- Timestamp             : 07/20/2020 03:44:50
- Generator ID          : 0020
- EvM Revision          : 04
- Sensor Type           : Fan
- Sensor Number         : 36
- Event Type            : Threshold
- Event Direction       : Assertion Event
- Event Data            : 52000b
- Description           : Lower Critical going low

### Table 1
|Column|Description|
|------|-----------|
|SEL Record ID|SEL record nubmer|
|Record Type|02h = System event record (default) <br> C0h-DFh = OEM timestamped, bytes 8-16 OEM defined <br> E0h-FFh = OEM non-timestamped, bytes 4-16 OEM defined|
|Timestamp|Time when the event was logged. UTC|
|Generator ID|RqSA and LUN if event was generated from IPMB<br>Software ID if event was generated from system software.<br><br>Byte 1<br>[7:1] - 7-bit I2C slave address, or 7-bit system software ID<Br>[0] - 0b = ID is IPMB slave address, 1b = System software ID<br>Software ID values:<br>0001h - BIOS POST for POST errors, RAS configuration/state, timestamp synch, OS boot events<br>0033h - BIOS SMI handler<br>0020h - BMC firmware (default)<br>002Ch - Intel ME firmware<br>0041h - Server management software<br>00C0h - HSC firmware - HSBP A<br>00C2h - HSC firmware - HSBP B|
|EvM Revision|Event message format version<br>04h = IPMI v2.0(default)<br>03h = IPMI v1.0|
|Sensor Type|Sensor type code for sensor that generated the event|
|Sensor Number|Number of sensor that generated the event(from SDR)|
|Event Type|Event Dir<br>[7] - 0b = Assertion event, 1b = Deassertion event<br><br>Event Type<br>Type of trigger for the event.<br>Event Type Codes<br>01h = Threshold<br>02h-0ch = Discrete<br>6Fh = Sensor-specific<br>70-7fh = OEM|
