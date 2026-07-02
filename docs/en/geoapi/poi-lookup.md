[English](poi-lookup.md) | [中文](../../zh/geoapi/poi-lookup.md) · [← Back](../../../README.md)

# POI Lookup

POI Lookup API provides basic information of POI(scenic spot, tide stations, etc.)

| Interface code | Interface         | Class        |
| ---------- | --------------------------- | ------------ |
| geoPoiLookup | POI Lookup  | [GeoPoiResponse](https://dev.qweather.com/en/docs/api/geoapi/poi-lookup/#response) |

## Parameters

**GeoPoiLookupParameter**

- `location` ***(required)*** `String` The location to be queried, support text, [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid), comma-separated [longitude and latitude](https://dev.qweather.com/en/docs/resource/glossary/#coordinate) (decimal, up to 2 decimal places), [Adcode](https://dev.qweather.com/docs/resource/glossary/#adcode)(Chinese cities only).   For example: `location=beijing` or `location=116.41,39.92`
- `type` ***(required)*** `Poi` Choose to search for a certain type of POI.
  - `scenic` Scenic Spot
  - `TSTA` Tide Station
- `city` `String` Search for POI within a given city. The city name can be text or the city's LocationID.   > The city name is an exact match. It is recommended to use LocaitonID. If the text cannot be matched, the data returned will be empty.
- `number` `Int` Number of the results in response, from 1 to 20, 10 is the default.
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
GeoPoiLookupParameter parameter = new GeoPoiLookupParameter("116.41,39.92", Poi.SCENIC);
instance.geoPoiLookup(parameter, new Callback<GeoPoiResponse>() {
    @Override
    public void onSuccess(GeoPoiResponse response) {
        Log.i(TAG, response.toString());
    }

    @Override
    public void onFailure(ErrorResponse errorResponse) {
        Log.i(TAG, errorResponse.toString());
    }

    @Override
    public void onException(Throwable e) {
        e.printStackTrace();
    }
});
```

## Response

[GeoPoiResponse](https://dev.qweather.com/en/docs/api/geoapi/poi-lookup/#response)
