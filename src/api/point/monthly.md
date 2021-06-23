---
title: Monthly Data | Point Data | JSON API
---

# Monthly Data

This endpoint provides historical monthly statistics for any geographic location. The data provided through this endpoint is aggregated from multiple governmental interfaces.

Monthly data is coming in with an offset of multiple months. Additionally, Meteostat aggregates monthly data from hourly observations, daily records and model data.

## Endpoint

Monthly data is provided through this endpoint:

```
GET https://meteostat.p.rapidapi.com/point/monthly
```

## Parameters

In order to query data for any location you’ll need to specify the `lat` and `lon` parameters. You will probably also want to add the `alt` parameter to your request to make the output more precise. If you do not set the `alt` parameter, Meteostat will guess the elevation based on nearby weather stations.

| **Parameter** | **Description**                                                       | **Type** | **Required** | **Default** |
|:--------------|:----------------------------------------------------------------------|:---------|:-------------|:------------|
| lat           | The latitude of the geographic location                               | Float    | Yes          | `undefined` |
| lon           | The longitude of the geographic location                              | Float    | Yes          | `undefined` |
| alt           | The elevation of the geographic location                              | Integer  | No           | `null`      |
| start         | The start date of the query (YYYY-MM-DD)                              | String   | Yes          | `undefined` |
| end           | The end date of the query (YYYY-MM-DD)                                | String   | Yes          | `undefined` |
| model         | Substitute missing records with statistically optimized model data    | String   | No           | `true`      |
| freq          | The time frequency of the records. Can be used for custom aggregation | String   | No           | `null`      |
| units         | The unit system of the meteorological parameters                      | String   | No           | metric      |

For full specification of available frequencies, defined by the `freq` parameter, please see [here](https://pandas.pydata.org/pandas-docs/stable/user_guide/timeseries.html#offset-aliases).

The `units` parameter takes one of the following values:

* _metric_ (Celsius, Millimeters, Kilometers per hour)
* _imperial_ (Fahrenheit, Inches, Miles per hour)
* _scientific_ (Kelvin, Millimeters, Meters per second)

## Response

The response body includes the following properties. Please note that all units mentioned below refer to the default `units` setting.

| **Parameter** | **Description**                                 | **Type** |
|:--------------|:------------------------------------------------|:---------|
| date          | The first date (YYYY-MM-DD) of the month        | String   |
| tavg          | The average daily air temperature in °C         | Float    |
| tmin          | The average daily minimum air temperature in °C | Float    |
| tmax          | The average daily maximum air temperature in °C | Float    |
| prcp          | The monthly precipitation total in mm           | Float    |
| snow          | The maximum snow depth in mm                    | Integer  |
| wdir          | The average wind direction in degrees (°)       | Integer  |
| wspd          | The average wind speed in km/h                  | Float    |
| wpgt          | The peak wind gust in km/h                      | Float    |
| pres          | The average sea-level air pressure in hPa       | Float    |
| tsun          | The monthly sunshine total in minutes (m)       | Integer  |

More information about the data format is available [here](/formats.html).

## Example

The following example requires the cURL command-line interface. Alternatively, you can use an API client like Postman.

```sh
curl --request GET \
	--url 'https://meteostat.p.rapidapi.com/point/monthly?lat=52.5244&lon=13.4105&start=2020-01-01&end=2020-12-31&alt=43' \
	--header 'x-rapidapi-host: meteostat.p.rapidapi.com' \
	--header 'x-rapidapi-key: {key}'
```

Please replace `{key}` with your personal API key.

### Data Response

The data output returns one object per month. Have a look at this example:

```json
{
	"date": "2020-01-01",
	"tavg": 4.1,
	"tmin": 1,
	"tmax": 7,
	"prcp": 37,
	"snow": 0,
	"wdir": 191.3,
	"wspd": 11.2,
	"wpgt": 77,
	"pres": 1025.2,
	"tsun": 3300
}
```
