---
title: meteostat.Daily | API | Python Library
---

# meteostat.Daily

Query daily weather data for one or multiple weather stations or a single geographical point.

## Parameters

The `stations` parameter is required. You can pass a [meteostat.Point](/python/api/point) or a DataFrame returned by the [meteostat.Stations.fetch](/python/api/stations/fetch) method or provide one (String) or multiple Meteostat weather station identifiers (Tuple or List).

| **Parameter** | **Description**                  | **Type**                                              | **Default** |
|:--------------|:---------------------------------|:------------------------------------------------------|:------------|
| loc           | Weather station(s) or Point      | DataFrame, [Point](/python/api/point), String or List | undefined   |
| start         | Start date of the desired period | Datetime                                              | None        |
| end           | End date of the desired period   | Datetime                                              | None        |
| model         | Include model data               | Boolean                                               | True        |

## Attributes

Attributes allow the configuration of general settings and behaviour.

| **Parameter** | **Description**                                      | **Type** | **Default**        |
|:--------------|:-----------------------------------------------------|:---------|:-------------------|
| cache_dir     | The path of the cache directory                      | String   | ~/.meteostat/cache |
| cache_subdir  | The subdirectory of the cache                        | String   | daily              |
| max_age       | Maximum age of a cached file in seconds              | Integer  | 86400              |
| processes     | Maximum number of processes used for data processing | Integer  | 1                  |
| threads       | Maximum number of threads used for data processing   | Integer  | 1                  |

You can disable caching completely by setting `max_age` to `0`.

When changing attributes, make sure to do so before creating a class instance:

```python{3}
from meteostat import Daily

Daily.cache_dir = '/my/path/goes/here'

data = Daily('10637')
```

## Methods

* [meteostat.Daily.normalize](normalize)
* [meteostat.Daily.aggregate](aggregate)
* [meteostat.Daily.interpolate](interpolate)
* [meteostat.Daily.convert](convert)
* [meteostat.Daily.coverage](coverage)
* [meteostat.Daily.fetch](fetch)
* [meteostat.Daily.count](count)
