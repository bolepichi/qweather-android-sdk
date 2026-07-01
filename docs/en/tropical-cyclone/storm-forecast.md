[English](storm-forecast.md) | [中文](../../zh/tropical-cyclone/storm-forecast.md) · [← Back](../../../README.md)

# Storm Forecast

Storm Forecast provides tropical cyclones information for a specific tropical cyclone, the data including forecast tropical cyclones location, level, pressure, wind and etc.

> **Note:** For inactive storms, the returned data is **NULL**, please get the storms status by [Storm List](https://dev.qweather.com/en/docs/android-sdk/tropical-cyclone/android-storm-list/) first.

| Interface code              | Interface     | Class                 |
| --------------------------- | ------------- | ---------------------- |
| tropicalStormForecast      | Storm forecast data | [StormForecastResponse](https://dev.qweather.com/en/docs/android-sdk/tropical-cyclone/android-storm-forecast/#response) |

## Parameters

**StormParameter**

- `stormid` ***(required)*** `String` The storm ID that needs to be queried, StormID can be obtained by [Storm List](#storm-list), e.g., `stormid=NP2018`

## Sample code


```java
StormParameter parameter = new StormParameter("NP_2426");
instance.tropicalStormForecast(parameter, new Callback<StormForecastResponse>() {
    @Override
    public void onSuccess(StormForecastResponse response) {
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

[StormForecastResponse](https://dev.qweather.com/en/docs/android-sdk/tropical-cyclone/android-storm-forecast/#response)

### Typhoon level

GBT 19201-2006

| Tropical cyclone level | Maximum average wind speed near the bottom center (m/s) | Maximum wind near the bottom center (level) |
| ------------------- | ----------------------------- | ------------------------ |
| Tropical pressure (TD) | 10.8-17.1 | 6-7 |
| Tropical Storm (TS) | 17.2-24.4 | 8-9 |
| Severe Tropical Storm (STS) | 24.5-32.6 | 10-11 |
| Typhoon (TY) | 32.7-41.4 | 12-13 |
| Severe Typhoon (STY) | 41.5-50.9 | 14-15 |
| Super Typhoon (SuperTY) | ≥51.0 | 16 or above |
