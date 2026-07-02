[English](sunrise-sunset.md) | [中文](../../zh/astronomy/sunrise-sunset.md) · [← Back](../../../README.md)

# Sunrise and Sunset

Get the sunrise and sunset times for any location around the world for the next 60 days.

| Interface code            | Interface     | Class       |
| -------------------------- | -------- | ------------ |
| astronomySun | Sunrise and Sunset | [AstronomySunResponse](https://dev.qweather.com/en/docs/api/astronomy/sunrise-sunset/#response) |

## Parameters

**AstronomySunParameter**

- `location` ***(required)*** `String` The location to be queried, support [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid) or comma-separated [longitude and latitude](https://dev.qweather.com/en/docs/resource/glossary/#coordinate) (decimal, up to 2 decimal places), LocationID can be obtained by [GeoAPI](https://dev.qweather.com/en/docs/api/geoapi/). Example: `location=101010100` or `location=116.41,39.92`
- `date` ***(required)*** `String` Set the date, up to 60 days in the future (including today). The date format is yyyyMMdd. Example: `date=20200531`

## Sample code

```java
SimpleDateFormat formatter = new SimpleDateFormat("yyyyMMdd", Locale.getDefault());
String formattedDate = formatter.format(new Date());
AstronomySunParameter parameter = new AstronomySunParameter("101120501",formattedDate);
instance.astronomySun(parameter, new Callback<AstronomySunResponse>() {
    @Override
    public void onSuccess(AstronomySunResponse response) {
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

[AstronomySunResponse](https://dev.qweather.com/en/docs/api/astronomy/sunrise-sunset/#response)
