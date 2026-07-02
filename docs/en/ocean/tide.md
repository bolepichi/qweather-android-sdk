[English](tide.md) | [中文](../../zh/ocean/tide.md) · [← Back](../../../README.md)

# Tide

Global tidal data for the next 10 days, including tide table and hourly tide forecast data.

| Interface code        | Interface     | Class             |
| ----------------------- | ---- | ------------------ |
| oceanTide | Tide | [OceanTideResponse](https://dev.qweather.com/en/docs/api/ocean/tide/#response) |

## Parameters

**OceanParameter**

- `location` ***(required)*** `String` The tide station to be queried, need [LocationID](https://dev.qweather.com/en/docs/resource/glossary/#locationid) and LocationID can be obtained by [POI Lookup](https://dev.qweather.com/en/docs/api/geoapi/poi-lookup/).   For example: `location=P2951`
- `date` ***(required)*** Set the date, up to 10 days in the future (including today). The date format is yyyyMMdd. Eexample: `date=20200531`

## Sample code

```java
Calendar calendar = Calendar.getInstance();
calendar.add(Calendar.DAY_OF_MONTH, 7);
Date sevenDaysAgo = calendar.getTime();

SimpleDateFormat formatter = new SimpleDateFormat("yyyyMMdd", Locale.getDefault());
String formattedDate = formatter.format(sevenDaysAgo);

OceanParameter parameter = new OceanParameter("P2236", formattedDate);

instance.oceanTide(parameter, new Callback<OceanTideResponse>() {
    @Override
    public void onSuccess(OceanTideResponse response) {
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

[OceanTideResponse](https://dev.qweather.com/en/docs/api/ocean/tide/#response)
