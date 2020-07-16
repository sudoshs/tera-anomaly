# IPMI - ipmitool 참고용

## ipmitool command
    # ipmitool -I <interface> -H <host> -U <id> -P <password> <command>

## Sensor list
    # ipmitool sensor -v

## Sensor list headers
- Sensor - Sensor ID
- VALUE - Value of the sensor, in given units.
- UNITS - Units, in which are the sensor values presented. 'discrete' means the sensor value is not measured in analog units
- STATE - Status of the sensor, i.e. whether the sensor value is in acceptable threshold. For ’discrete’ sensors, the bit mask of asserted states is shown. Use ’-v’ command line option to decode the bit mask to human readable form.
- LO NOREC - Lower non-recoverable threshold.
- LO CRIT - Lower critical threshold.
- LO NOCRIT - Lower non-critical threshold.
- UP NOCRIT - Upper non-critical threshold.
- UP CRIT - Upper critical threshold.
- UP NOREC - Upper non-recoverable threshold.