[English](solar-elevation-angle.md) | [中文](../../zh/astronomy/solar-elevation-angle.md) · [← Back](../../../README.md)

# Solar Elevation Angle

Get global solar elevation angle and azimuth.

| Interface code                   | Interface       | Class            |
| -------------------------------- | ---------- | ----------------- |
| astronomySolarElevationAngle | Solar elevation angle data | [AstronomySolarElevationAngleResponse](https://dev.qweather.com/en/docs/api/astronomy/solar-elevation-angle/#response) |

## Parameters

**SolarElevationAngleParameter**

- `location` ***(required)*** `String` The comma-separated [longitude and latitude](https://dev.qweather.com/en/docs/resource/glossary/#coordinate) (decimal, up to 2 decimal places) of the location to be queried.  For example: `location=116.41,39.92`
- `date` ***(required)*** `String` Set date, format is yyyyMMdd, e.g., `date=20200531`
- `time` ***(required)*** `String` Set time, format is HHmm, 24-hour, e.g., `time=1230`
- `tz` ***(required)*** `String` Location time zone, e.g., `tz=0800` or `tz=-0530`
- `alt` ***(required)*** `Int` Location altitude, in meters, e.g., `alt=43`

## Sample code

```java
Date currentDate = new Date();
SimpleDateFormat dateFormat = new SimpleDateFormat("yyyMMdd", Locale.getDefault());
String date = dateFormat.format(currentDate);

SimpleDateFormat timeFormat = new SimpleDateFormat("HHmm", Locale.getDefault());
String time = timeFormat.format(currentDate);
SolarElevationAngleParameter parameter = new SolarElevationAngleParameter("116.41,39.92",date,time,"0800","43");

instance.astronomySolarElevationAngle(parameter, new Callback<AstronomySolarElevationAngleResponse>() {
    @Override
    public void onSuccess(AstronomySolarElevationAngleResponse response) {
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

[AstronomySolarElevationAngleResponse](https://dev.qweather.com/en/docs/api/astronomy/solar-elevation-angle/#response)
