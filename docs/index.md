# Plant Watering System

A smart plant-watering prototype that combines environmental sensing, soil-moisture monitoring, network communication, irrigation control, and a Flutter mobile interface.

<figure markdown="span">
  ![Plant watering prototype](https://raw.githubusercontent.com/pmembari/Plant-Watering/main/images/IMG_4556.JPG)
  <figcaption>Plant watering prototype</figcaption>
</figure>

## What the project does

The system monitors:

- air temperature;
- air humidity;
- soil humidity for two plants.

The software then uses the sensor values to control two irrigation outputs. The repository also contains a Flutter application that displays the live measurements and can notify the user when irrigation time arrives.

## Main components

| Component | Role |
| --- | --- |
| Hardware / controller code | Reads sensor data and controls irrigation outputs |
| TCP communication | Exchanges measurements and commands |
| Flutter mobile app | Displays temperature, humidity, and soil moisture |
| Notifications and calendar integration | Warns the user when irrigation is due |

## Repository

The implementation is available on GitHub under [pmembari/Plant-Watering](https://github.com/pmembari/Plant-Watering).

Use the navigation to explore the system architecture and implementation details.
