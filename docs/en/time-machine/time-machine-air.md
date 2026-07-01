[English](time-machine-air.md) | [中文](../../zh/time-machine/time-machine-air.md) · [← Back](../../../README.md)

# Historical air quality

Get the last 10 days of air quality history data.

> Let's say, today is December 30, you can get data from Dec. 20 to Dec. 29.

| Interface code     | Interface              | Class                      |
| ------------------ | ---------------------- | -------------------------- |
| historicalAir     | Historical air quality | [HistoricalAirResponse](https://dev.qweather.com/en/docs/android-sdk/time-machine/android-time-machine-weather/#response)      |

## Parameters

**HistoricalAirParameter**

- `location` ***(required)*** `String` The location to be queried, only support [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid) and LocationID can be obtained by [GeoAPI](https://dev.qweather.com/en/docs/api/geoapi/).   For example: `location=101010100`
- `date` ***(required)*** `String` Set the date, up to the most recent 10 days. The date format is yyyyMMdd. Example: `date=20200531`
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
Calendar calendar = Calendar.getInstance();
calendar.add(Calendar.DAY_OF_MONTH, -3);
Date sevenDaysAgo = calendar.getTime();

SimpleDateFormat formatter = new SimpleDateFormat("yyyyMMdd", Locale.getDefault());
String formattedDate = formatter.format(sevenDaysAgo);

HistoricalAirParameter parameter = new HistoricalAirParameter("101120501",formattedDate);

instance.historicalAir(parameter, new Callback<HistoricalAirResponse>() {
    @Override
    public void onSuccess(HistoricalAirResponse response) {
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

[HistoricalAirResponse](https://dev.qweather.com/en/docs/android-sdk/time-machine/android-time-machine-weather/#response)
