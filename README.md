# Telemetry Data Format Converter

This project contains a Python-based solution to convert telemetry data from two different formats into a unified format. The purpose of the project is to normalize telemetry data with differing timestamp formats (ISO 8601 and Unix timestamps) and different field structures, allowing for a common data format to be used for further analysis or processing.

## Features

- **Conversion from Format 1**: Data in the ISO 8601 timestamp format, with sensor readings provided in nested structures.
- **Conversion from Format 2**: Data in Unix timestamp format (in seconds) with device readings.
- **Unified Output**: All input formats are converted to a common format where timestamps are standardized to milliseconds.

## Input Formats

1. **Format 1** (ISO 8601)
    - Contains date and time separately.
    - Sensor data includes temperature and humidity.
    
2. **Format 2** (Unix Timestamp)
    - Includes device type and identifier.
    - Measurements include temperature and humidity.

## Unified Output Format

The unified format for both input types includes:
```json
{
  "id": "<identifier>",
  "type": "<sensor/device>",
  "timestamp": "<milliseconds>",
  "readings": {
    "temperature": "<temperature_value>",
    "humidity": "<humidity_value>"
  }
}
