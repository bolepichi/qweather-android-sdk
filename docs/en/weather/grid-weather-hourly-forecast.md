[English](grid-weather-hourly-forecast.md) | [中文](../../zh/weather/grid-weather-hourly-forecast.md) · [← Back](../../../README.md)

# Grid Weather Hourly Forecast

Weather forecast data based on numerical models, to provide hourly weather forecasts at specified coordinates around the world, with a spatial resolution of 3-5 kilometers.

> **Hint:** The grid weather data is based on Numerical Weather Prediction (NWP) models, and it is not suitable for comparison with observation station data. For station-based city weather data, please refer to the [City Weather API](https://dev.qweather.com/en/docs/android-sdk/weather/android-weather-hourly-forecast/). Grid weather uses UTC+0 as the time zone.

| Interface code       | Interface     | Class             |
| --------------------------- | ---- | ------------------ |
| grid24h | Hourly Forecast by Grid (24hrs)| [GridHourlyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-hourly-forecast/#response) |
| grid72h | Hourly Forecast by Grid (72hrs)）| [GridHourlyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-hourly-forecast/#response) |

## Parameters

**GridWeatherParameter**

- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`
- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.
- `unit` `Unit` Set weather data unit, the available value are `unit=m` for metric(default) and `unit=i` for imperial. See more about [Unit](https://dev.qweather.com/en/docs/resource/unit).

## Sample code

```java
GridWeatherParameter parameter = new GridWeatherParameter( 116.41, 39.2);
Callback<GridHourlyResponse> responseCallback = new Callback<GridHourlyResponse>() {
    @Override
    public void onSuccess(GridHourlyResponse response) {
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
};

/*
* Hourly Forecast by Grid (24hrs)
*/
instance.grid24h(parameter, responseCallback);

/*
* Hourly Forecast by Grid (72hrs)
*/
instance.grid72h(parameter, responseCallback);
```

## Response

[GridHourlyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-hourly-forecast/#response)
