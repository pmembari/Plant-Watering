# Communication Flow

The project uses simple TCP socket messages rather than an HTTP API.

## Measurement request

The client sends:

```text
getData
```

The controller responds with four comma-separated values:

```text
<air_temp>,<air_humidity>,<soil_1>,<soil_2>
```

## Irrigation control

The Python controller derives two binary outputs from the soil readings and sends:

```text
X<output_1><output_2>
```

## Scheduled irrigation

The Flutter app also handles a special message:

```text
Irrigation Time
```

When this message arrives, the application:

1. checks the device calendar;
2. identifies events beginning within five minutes;
3. displays a local notification;
4. allows cancellation through the `cancelIrrigation` command.

This communication protocol is intentionally lightweight and closely tied to the prototype implementation.
