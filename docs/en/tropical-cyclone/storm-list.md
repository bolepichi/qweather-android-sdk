[English](storm-list.md) | [中文](../../zh/tropical-cyclone/storm-list.md) · [← Back](../../../README.md)

# Storm list

Get a list of tropical cyclones for the last 2 years in major ocean basins around the world.

> Only the coastal areas of China are supported now, i.e. `basin=NP`

| Interface code     | Interface          | Class             |
| ------------------ | ------------------ | ----------------- |
| tropicalStormList | Storm list | [StormListResponse](https://dev.qweather.com/en/docs/android-sdk/tropical-cyclone/android-storm-list/#response) |

## Parameters

**StormListParameter**

- `basin` ***(required)*** `Basin` The basin where the storm needs to be queried. For now, only support `NP`.
  - `AL` North Atlantic
  - `EP` Eastern Pacific
  - `NP` NorthWest Pacific
  - `SP` SouthWestern Pacific
  - `NI` North Indian North Indian Ocean
  - `SI` South Indian South Indian Ocean
- `year` ***(required)*** `String` Support to query storm of this year and last year, e.g., `year=2020`

## Sample code


```java
StormListParameter parameter = new StormListParameter(Basin.NP,2024);
instance.tropicalStormList(parameter, new Callback<StormListResponse>() {
    @Override
    public void onSuccess(StormListResponse response) {
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

[StormListResponse](https://dev.qweather.com/en/docs/android-sdk/tropical-cyclone/android-storm-list/#response)
