[English](air-station.md) | [中文](../../zh/air-quality/air-station.md) · [← Back](../../../README.md)

# Monitoring Station Data

Monitoring Station Data API provides pollutant concentration values from air quality monitoring stations in each country or region.

> **Warning:** Monitoring station data is for reference only, it may be delayed, incorrect or unavailable due to various reasons such as failure, removal, maintenance or local laws and regulations.

| Interface code | Interface         | Class       |
| --------------- | ---------------- | ------------ |
| airStation | Monitoring Station Data  | [AirV1StationResponse](https://dev.qweather.com/en/docs/api/air-quality/air-station/#response) |

## Parameters

**AirV1StationParameter**

- `LocationID` ***(required)*** `String` LocationID of air quality monitoring station, LocationID can be obtained by [GeoAPI](https://dev.qweather.com/en/docs/api/geoapi/). For example `P58911`

- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
AirV1StationParameter parameter = new AirV1StationParameter("P58911");
instance.airStation(parameter, new Callback<AirV1StationResponse>() {
    @Override
    public void onSuccess(AirV1StationResponse response) {
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

[AirV1StationResponse](https://dev.qweather.com/en/docs/api/air-quality/air-station/#response)
