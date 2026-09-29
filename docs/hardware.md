# Hardware

The hardware-side implementation is located under [Hardware/](https://github.com/pmembari/Plant-Watering/tree/main/Hardware).

## Sensor loop

The Python controller creates a TCP socket and connects to:

```text
192.168.1.3:1234
```

Every two seconds it:

1. sends `getData`;
2. receives four comma-separated sensor values;
3. parses the measurements;
4. applies the soil-humidity threshold;
5. sends a compact control message back to the device.

The received fields are:

```text
air_temp, air_hum, soil_hum_1, soil_hum_2
```

## Irrigation decision

The controller uses the following threshold logic:

```python
if soil_hum_1 > 3000:
    vol_s_1 = 1
else:
    vol_s_1 = 0
```

The same logic is used for the second plant.

The resulting command is transmitted in this form:

```text
X<valve_1><valve_2>
```

For example, `X10` means the first irrigation output is active and the second is inactive.

## Project tooling

The hardware directory includes a `platformio.ini`, together with `src`, `include`, `lib`, and `test` directories, indicating a PlatformIO-based embedded-development structure.
