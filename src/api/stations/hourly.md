---
title: Hourly Data | Weather Stations | JSON API
---

# Hourly Data

This endpoint provides historical hourly observations for a particular weather station. Furthermore, gaps in the time series can be filled in with statistically optimized model data. The data provided through this endpoint is aggregated from multiple governmental interfaces.

Hourly observations are coming in with an offset of about two to three hours. However, some data might be added multiple days or even months later, depending on how the different weather services are updating their datasets.

Hourly data can be queried for a **maximum of 30 days** per request.

## Endpoint

Hourly data is provided through this endpoint:

```
GET https://meteostat.p.rapidapi.com/stations/hourly
```

## Parameters

When calling this endpoint please refer to the following parameters.

| **Parameter** | **Description**                                                       | **Type** | **Required** | **Default** |
|:--------------|:----------------------------------------------------------------------|:---------|:-------------|:------------|
| station       | The weather station ID                                                | String   | Yes          | `undefined` |
| start         | The start date of the period (YYYY-MM-DD)                             | String   | Yes          | `undefined` |
| end           | The end date of the period (YYYY-MM-DD)                               | String   | Yes          | `undefined` |
| tz            | The time zone according to the tz database                            | String   | No           | UTC         |
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

| **Parameter** | **Description**                            | **Type** |
|:--------------|:-------------------------------------------|:---------|
| time          | Time of observation (YYYY-MM-DD hh:mm:ss)  | String   |
| temp          | The air temperature in °C                  | Float    |
| dwpt          | The dew point in °C                        | Float    |
| rhum          | The relative humidity in percent (%)       | Integer  |
| prcp          | The one hour precipitation total in mm     | Float    |
| snow          | The snow depth in mm                       | Integer  |
| wdir          | The wind direction in degrees (°)          | Integer  |
| wspd          | The average wind speed in km/h             | Float    |
| wpgt          | The peak wind gust in km/h                 | Float    |
| pres          | The sea-level air pressure in hPa          | Float    |
| tsun          | The one hour sunshine total in minutes (m) | Integer  |
| coco          | The weather condition code                 | Integer  |

More information on the data formats and weather condition codes is available [here](/formats.html).

## Example

The following example requires the cURL command-line interface. Alternatively, you can use an API client like Postman.

```sh
curl --request GET \
	--url 'https://meteostat.p.rapidapi.com/stations/hourly?station=10637&start=2020-01-01&end=2020-01-01&tz=Europe%2FBerlin' \
	--header 'x-rapidapi-host: meteostat.p.rapidapi.com' \
	--header 'x-rapidapi-key: {key}'
```

Please replace `{key}` with your personal API key.

### Data Response

The data output returns one object per hour. Have a look at this example:

```json
{
	"time": "2019-12-31 23:00:00",
	"temp": 1.6,
	"dwpt": 0.1,
	"rhum": 90,
	"prcp": 0,
	"snow": 0,
	"wdir": 300,
	"wspd": 5,
	"wpgt": 10,
	"pres": 1036.4,
	"tsun": 0,
	"coco": 4
}
```
