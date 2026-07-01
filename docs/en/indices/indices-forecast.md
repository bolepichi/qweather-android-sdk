[English](indices-forecast.md) | [中文](../../zh/indices/indices-forecast.md) · [← Back](../../../README.md)

# Weather Indices Forecast

Get weather indices forecast data for cities in China and around the world.

- Weather Indices in China: Comfort Indices, Car Wash Indices, Dressing Indices, Cold Indices, Sports Indices, Travel Indices, UV Indices, Air Pollution Indices, Air Conditioning Indices, Allergy Indices, Sunglasses Indices, Makeup Indices, Sunshine Indices, Traffic Indices, Fishing Indices, Sun Protection Indices
- Weather Indices worldwide: Sports Indices, Car Wash Indices, UV Indices, Fishing Indices

| Interface code   | Interface             | Class            |
| ---------------- | ------------------ | ---------------- |
| indices1d | Today Weather Indices           | [IndicesDailyResponse](https://dev.qweather.com/en/docs/android-sdk/indices/android-indices-forecast/#response) |
| indices3d | Weather Indices 3-days forecast | [IndicesDailyResponse](https://dev.qweather.com/en/docs/android-sdk/indices/android-indices-forecast/#response) |

## Parameters

**IndicesParameter**

- `location` ***(required)*** `String` The location to be queried, support [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid) or comma-separated [longitude and latitude](https://dev.qweather.com/en/docs/resource/glossary/#coordinate) (decimal, up to 2 decimal places), LocationID can be obtained by [GeoAPI](https://dev.qweather.com/en/docs/api/geoapi/). Example: `location=101010100` or `location=116.41,39.92`
- `indices` ***(required)*** `Indices` Weather indices type ID, including car wash index, clothing index, fishing index, etc. You can get multiple types of weather indices at one time. All indices type see [Indices Info](https://dev.qweather.com/en/docs/resource/indices-info/).
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
IndicesParameter parameter = new IndicesParameter("101120501", Indices.CW, Indices.DRSG);

Callback<IndicesDailyResponse> responseCallback = new Callback<IndicesDailyResponse>() {
    @Override
    public void onSuccess(IndicesDailyResponse response) {
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

// Get 1-day weather indices data
instance.indices1d(parameter, responseCallback);

// Get 3-days weather indices data
instance.indices3d(parameter, responseCallback);
```

## Response

[IndicesDailyResponse](https://dev.qweather.com/en/docs/android-sdk/indices/android-indices-forecast/#response)

### Index type and level

See [Indices Info](https://dev.qweather.com/en/docs/resource/indices-info/).
