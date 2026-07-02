[English](../../en/tropical-cyclone/storm-forecast.md) | [中文](storm-forecast.md) · [← Back](../../../README-zh.md)

# 台风预报

台风预报提供全球主要海洋流域的热带低气压（台风）的预报信息，包括台风预测位置、等级、气压、风力、速度。

> 如果查询的台风已经结束，则返回的数据为空，建议先通过[台风列表](./storm-list.md)获取台风的状态

| 接口代码                | 接口      | 数据类                 |
| ---------------------- | -------- | --------------------- |
| tropicalStormForecast | 台风预报   | [StormForecastResponse](https://dev.qweather.com/docs/api/tropical-cyclone/storm-forecast/#%E5%8F%B0%E9%A3%8E%E7%AD%89%E7%BA%A7) |

## 参数

**StormParameter**

- `stormid` ***（必选）*** `String` 需要查询的台风ID，StormID可通过[台风列表](#storm-list)获取。例如 `stormid=NP2018`

## 示例代码

```java
StormParameter parameter = new StormParameter("NP_2426");
instance.tropicalStormForecast(parameter, new Callback<StormForecastResponse>() {
    @Override
    public void onSuccess(StormForecastResponse response) {
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

[StormForecastResponse](https://dev.qweather.com/docs/api/tropical-cyclone/storm-forecast/#%E5%8F%B0%E9%A3%8E%E7%AD%89%E7%BA%A7)

### 台风等级

GBT 19201-2006

| 热带气旋等级        | 底层中心附近最大平均风速(m/s) | 底层中心附近最大风力(级) |
| ------------------- | ----------------------------- | ------------------------ |
| 热带气压（TD）      | 10.8-17.1                     | 6-7                      |
| 热带风暴（TS）      | 17.2-24.4                     | 8-9                      |
| 强热带风暴（STS）   | 24.5-32.6                     | 10-11                    |
| 台风（TY）          | 32.7-41.4                     | 12-13                    |
| 强台风（STY）       | 41.5-50.9                     | 14-15                    |
| 超强台风（SuperTY） | ≥51.0                         | 16或以上                 |
