[English](top-city.md) | [中文](../../zh/geoapi/top-city.md) · [← Back](../../../README.md)

# Top city

Get a list of popular cities around the world.

| Interface code | Interface     | Class              |
| -------------- | ------------- | ------------------ |
| geoCityTop    | Top city      | [GeoCityTopResponse](https://dev.qweather.com/en/docs/api/geoapi/top-city/#response) |

## Parameters

**GeoCityTopParameter**

- `range` `Range` Set to search only within a certain country or region. The country and region name needs to use [country code ISO 3166](https://dev.qweather.com/en/docs/resource/glossary/#iso-3166). If this parameter is not set, the search range will be all cities. Example: `range=cn`
- `number` `Int` Number of the results in response, from 1 to 20, 10 is the default.
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
GeoCityTopParameter parameter = new GeoCityTopParameter().range(Range.CN);
instance.geoCityTop(parameter, new Callback<GeoCityTopResponse>() {
    @Override
    public void onSuccess(GeoCityTopResponse response) {
        Log.i(TAG, response.toString());
    }

    @Override
    public void onFailure(ErrorResponse errorResponse) {
        Log.i(TAG, errorResponse.toString());
    }

    @Override
    public void onException(Throwable e) {
        e.printStackTrace();
        Log.e(TAG,e.toString());
    }
});
```

## Response

[GeoCityTopResponse](https://dev.qweather.com/en/docs/api/geoapi/top-city/#response)
