[English](minutely-precipitation.md) | [中文](../../zh/minutely/minutely-precipitation.md) · [← Back](../../../README.md)

# Minutely Precipitation

Get minute-level precipitation forecast data every 5 minutes for the next 2 hours in China.

> This data is only supported for Chinese cities.

| Interface code| Interface  | Class |
| ---------- | ----------- | ------------ |
| minutely | Minutely Precipitation  | [MinutelyResponse](https://dev.qweather.com/en/docs/api/minutely/minutely-precipitation/#response) |

## Parameters

**MinutelyParameter**

- `latitude` ***(required)*** `Double` The latitude of the desired location. Decimal format, up to 2 decimal places. For example `39.92`
- `longitude` ***(required)*** `Double` The longitude of the desired location. Decimal format, up to 2 decimal places. For example `116.41`
- `lang` `Lang` Multi-language setting, please see [Language](https://dev.qweather.com/en/docs/resource/language/) to find out how our multi-language works and how to set up.

## Sample code

```java
MinutelyParameter parameter = new MinutelyParameter(116.41, 39.92);
instance.minutely(parameter, new Callback<MinutelyResponse>() {
    @Override
    public void onSuccess(MinutelyResponse response) {
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

[MinutelyResponse](https://dev.qweather.com/en/docs/api/minutely/minutely-precipitation/#response)
