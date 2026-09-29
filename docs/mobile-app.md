# Mobile App

The mobile application is implemented in Flutter under [Flutter coding/](https://github.com/pmembari/Plant-Watering/tree/main/Flutter%20coding).

## Live dashboard

The interface displays four measurements:

- air temperature;
- air humidity;
- soil humidity for the first plant;
- soil humidity for the second plant.

The app constrains received values to practical display ranges:

- temperature: `0–50 °C`;
- air humidity: `0–100 %`;
- soil sensor readings: `0–4096`.

The soil-humidity percentage is calculated from the raw ADC reading using:

```text
(4096 - sensor_value) / 40.96
```

## Network communication

The app connects to:

```text
192.168.1.4:80
```

It requests fresh measurements every two seconds.

## Irrigation notifications

The app integrates `flutter_local_notifications` and `device_calendar`.

When the controller sends `Irrigation Time`, the app checks upcoming calendar events. If an event is about to begin, the irrigation notification includes that context and gives the user a way to cancel irrigation.

The cancellation action sends:

```text
cancelIrrigation
```

back through the socket.
