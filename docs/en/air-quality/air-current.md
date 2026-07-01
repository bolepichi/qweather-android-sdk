[English](air-current.md) | [中文](../../zh/air-quality/air-current.md) · [← Back](../../../README.md)

# Current Air Quality

The current air quality (AQI) API provides real-time air quality data for specified locations, data resolution is 1x1 km.

- AQI, category, color and primary pollutant based on local standards for each country or region
- Generic QWeather AQI
- Pollutant concentration values and their sub-index.
- Health effects and advice
- Associated monitoring station information

We recommend to read [Air Quality Info](https://dev.qweather.com/en/docs/resource/air-info/) to learn about the AQIs, pollutants, supported regions and more.

| Interface code | Interface         | Class       |
| --------------- | ---------------- | ------------ |
| airCurrent | Current Air Quality  | [AirV1CurrentResponse](https://dev.qweather.com/en/docs/android-sdk/air-quality/android-air-current/#%E8%BF%94%E5%9B%9E%E6%95%B0%E6%8D%AE) |

## Parameters

**AirV1Parameter**

- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`

- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`

- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code


```java
AirV1Parameter parameter  = new AirV1Parameter(39.92, 116.41);
instance.airCurrent(parameter, new Callback<AirV1CurrentResponse>() {
    @Override
    public void onSuccess(AirV1CurrentResponse response) {
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

[AirV1CurrentResponse](https://dev.qweather.com/en/docs/android-sdk/air-quality/android-air-current/#%E8%BF%94%E5%9B%9E%E6%95%B0%E6%8D%AE)
