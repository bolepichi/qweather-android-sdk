[English](../../en/air-quality/air-station.md) | [中文](air-station.md) · [← Back](../../../README-zh.md)

# 监测站数据

监测站数据API提供各个国家或地区监测站的污染物浓度值。

> **警告：**监测站的观测值仅供参考，可能由于故障、移除、维护或当地法律法规等各种原因导致数据延迟或缺失，我们无法确保该数据的可用性。

| 接口代码 | 接口         | 数据类        |
| --------------- | ---------------- | ------------ |
| airStation | 监测站数据  | [AirV1StationResponse](https://dev.qweather.com/docs/android-sdk/air-quality/android-air-station/#%E8%BF%94%E5%9B%9E%E6%95%B0%E6%8D%AE) |

## 参数

**AirV1StationParameter**

- `LocationID` ***（必选）*** `String` 空气质量监测站的LocationID，LocationID可通过[GeoAPI](https://dev.qweather.com/docs/api/geoapi/)获取。例如 `P58911`
- `lang` `Lang` 多语言设置，请阅读[多语言](https://dev.qweather.com/docs/resource/language/)文档，了解我们的多语言是如何工作、如何设置以及数据是否支持多语言。

## 示例代码

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

## 返回数据

[AirV1StationResponse](https://dev.qweather.com/docs/android-sdk/air-quality/android-air-station/#%E8%BF%94%E5%9B%9E%E6%95%B0%E6%8D%AE)
