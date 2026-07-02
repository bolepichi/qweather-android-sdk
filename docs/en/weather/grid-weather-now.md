[English](grid-weather-now.md) | [中文](../../zh/weather/grid-weather-now.md) · [← Back](../../../README.md)

# Grid Weather Real-time

Weather forecast data based on numerical models, to provide current weather data at specified coordinates around the world, with a spatial resolution of 3-5 kilometers.

> **Hint:** The grid weather data is based on Numerical Weather Prediction (NWP) models, and it is not suitable for comparison with observation station data. For station-based city weather data, please refer to the [Real-time weather](./weather-now.md). Grid weather uses UTC+0 as the time zone.

| Interface code          | Interface     | Class            |
| --------------------------- | ---- | ------------------ |
| gridNow |  Grid Weather Real-time| [GridNowResponse](https://dev.qweather.com/en/docs/api/weather/grid-weather-now/#response) |

## Parameters

**GridWeatherParameter**

- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`
- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.
- `unit` `Unit` Set weather data unit, the available value are `unit=m` for metric(default) and `unit=i` for imperial. See more about [Unit](https://dev.qweather.com/en/docs/resource/unit).

## Sample code

```java
GridWeatherParameter parameter = new GridWeatherParameter( 116.41, 39.2);
instance.gridNow(parameter, new Callback<GridNowResponse>() {
    @Override
    public void onSuccess(GridNowResponse response) {
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

[GridNowResponse](https://dev.qweather.com/en/docs/api/weather/grid-weather-now/#response)
