[English](weather-alert.md) | [中文](../../zh/warning/weather-alert.md) · [← Back](../../../README.md)

# Weather Alert

Get officially issued real-time severe weather alert data around the world.

> **Hint:** For the implementation of weather alert, see [Resource - Alert Info](https://dev.qweather.com/en/docs/resource/warning-info/) in advance.

| Interface code     | Interface    | Class           |
| -------------------- | -------- | ---------------- |
| weatherAlertCurrent | Weather Alert | [WeatherAlertCurrentResponse](https://dev.qweather.com/en/docs/api/warning/weather-alert/#response) |

## Parameters

**WeatherAlertCurrentParameter**

- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`
- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`
- `localTime` `Bool` Whether to return the local time of the queried location. `true` for local time, `false` for UTC time (default).
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
WeatherAlertCurrentParameter parameter = new WeatherAlertCurrentParameter(39.2,  116.41, true);
instance.weatherAlertCurrent(parameter, new Callback<WeatherAlertCurrentResponse>() {
    @Override
    public void onSuccess(WeatherAlertCurrentResponse response) {
        Log.i(TAG, response.toString());
    }

    @Override
    public void onFailure(ErrorResponse errorResponse) {
        Log.i(TAG,errorResponse.toString());
    }

    @Override
    public void onException(Throwable e) {
        e.printStackTrace();
    }
});
```

## Response

[WeatherAlertCurrentResponse](https://dev.qweather.com/en/docs/api/warning/weather-alert/#response)
