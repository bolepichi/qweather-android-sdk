[English](time-machine-weather.md) | [中文](../../zh/time-machine/time-machine-weather.md) · [← Back](../../../README.md)

# Time Machine for Weather

Get the last 10 days of weather history data.

> Let's say, today is December 30, you can get historical data from Dec. 20 to Dec. 29.

> QWeather also provides historical reanalysis weather data from 2000 to present. If you need more historical weather data, please provide the following information to <sales@qweather.com>.
>
> * Company name
> * Contact information
> * City or coordinates
> * Date range

| Interface code      | Interface              | Class                      |
| ------------------- | ---------------------- | -------------------------- |
| historicalWeather      | Historical weather     | [HistoricalWeatherResponse](https://dev.qweather.com/en/docs/api/time-machine/time-machine-weather/#response)      |

## Parameters

**HistoricalWeatherParameter**

* `location` ***(required)*** `String` The location to be queried, only support [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid) and LocationID can be obtained by [GeoAPI](https://dev.qweather.com/en/docs/api/geoapi/).   For example: `location=101010100`
* `date` ***(required)*** `String` Set the date, up to the most recent 10 days. The date format is yyyyMMdd. Example: `date=20200531`
* `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.
* `unit` `Unit` Set weather data unit, the available value are `unit=m` for metric(default) and `unit=i` for imperial. See more about [Unit](https://dev.qweather.com/en/docs/resource/unit).

## Sample code

```java
Calendar calendar = Calendar.getInstance();
calendar.add(Calendar.DAY_OF_MONTH, -7);
Date sevenDaysAgo = calendar.getTime();

SimpleDateFormat formatter = new SimpleDateFormat("yyyyMMdd", Locale.getDefault());
String formattedDate = formatter.format(sevenDaysAgo);

HistoricalWeatherParameter parameter = new HistoricalWeatherParameter("101120501",formattedDate);

instance.historicalWeather(parameter, new Callback<HistoricalWeatherResponse>() {
    @Override
    public void onSuccess(HistoricalWeatherResponse response) {
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

[HistoricalWeatherResponse](https://dev.qweather.com/en/docs/api/time-machine/time-machine-weather/#response)
