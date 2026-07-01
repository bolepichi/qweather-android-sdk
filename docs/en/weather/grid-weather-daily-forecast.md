[English](grid-weather-daily-forecast.md) | [中文](../../zh/weather/grid-weather-daily-forecast.md) · [← Back](../../../README.md)

# Grid Weather Daily Forecast

Weather forecast data based on numerical models, to provide daily weather forecasts at specified coordinates around the world, with a spatial resolution of 3-5 kilometers.

> **Hint:** The grid weather data is based on Numerical Weather Prediction (NWP) models, and it is not suitable for comparison with observation station data. For station-based city weather data, please refer to the [City Weather API](https://dev.qweather.com/en/docs/android-sdk/weather/android-weather-daily-forecast/). Grid weather uses UTC+0 as the time zone.

| Interface code    | Interface   | Class           |
| ----------------- | ----------- | --------------- |
| grid3d | 3 Days Forecast by Grid| [GridDailyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-daily-forecast/#response) |
| grid7d | 7 Days Forecast by Grid| [GridDailyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-daily-forecast/#response) |

## Parameters

 **GridWeatherParameter**

- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`
- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.
- `unit` `Unit` Set weather data unit, the available value are `unit=m` for metric(default) and `unit=i` for imperial. See more about [Unit](https://dev.qweather.com/en/docs/resource/unit).

## Sample code

```java
GridWeatherParameter parameter = new GridWeatherParameter( 116.41, 39.2);
Callback<GridDailyResponse> responseCallback = new Callback<GridDailyResponse>() {
    @Override
    public void onSuccess(GridDailyResponse response) {
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
* 3 Days Forecast by Grid
*/
instance.grid3d(parameter, responseCallback);

/*
* 7 Days Forecast by Grid
*/
instance.grid7d(parameter, responseCallback);

```

## Response

[GridDailyResponse](https://dev.qweather.com/en/docs/android-sdk/weather/android-grid-weather-daily-forecast/#response)
