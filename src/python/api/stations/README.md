---
title: meteostat.Stations | API | Python Library
---

# meteostat.Stations

Select weather stations from the full list of stations.

## Parameters

This class does not take any parameters.

## Attributes

Attributes allow the configuration of general settings and behaviour.

| **Parameter** | **Description**                                    | **Type** | **Default**        |
|:--------------|:---------------------------------------------------|:---------|:-------------------|
| cache_dir     | The path of the cache directory                    | String   | ~/.meteostat/cache |
| cache_subdir  | The subdirectory of the cache                      | String   | stations           |
| max_age       | Maximum age of a cached file in seconds            | Integer  | 86400              |
| max_threads   | Maximum number of threads used for data processing | Integer  | 1                  |

When changing attributes, make sure to do so before creating a class instance:

```python{3}
from meteostat import Stations

Stations.cache_dir = '/my/path/goes/here'

stations = Stations()
```

## Methods

* [meteostat.Stations.nearby](nearby)
* [meteostat.Stations.bounds](bounds)
* [meteostat.Stations.region](region)
* [meteostat.Stations.id](id)
* [meteostat.Stations.inventory](inventory)
* [meteostat.Stations.convert](convert)
* [meteostat.Stations.fetch](fetch)
* [meteostat.Stations.count](count)
