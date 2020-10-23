# Formats and Units

Meteostat uses the metric system. Both the JSON API and the Bulk Data interface use the formats and units listed below.

## Time Format

Date and time statements follow the ISO 8601 standard (e.g. 2016-12-31 for December 31st 2016 and 23:59:58 for 23 hours, 59 minutes, and 58 seconds). The time zone used by Meteostat is Coordinated Universal Time (UTC).

### Time Ranges

Many JSON API endpoints require the specification of a time range using the <code>start</code> and <code>end</code> parameters. For these parameters please always provide dates in this format: _YYYY-MM-DD_.

## Meteorological Parameters

The Meteostat API uses abbreviations to describe meteorological parameters:

| **Code** | **Meaning**             |
|----------|-------------------------|
| TEMP     | Air Temperature         |
| TAVG     | Average Temperature     |
| TMIN     | Minimum Temperature     |
| TMAX     | Maximum Temperature     |
| DWPT     | Dew Point               |
| PRCP     | Total Precipitation     |
| WDIR     | Wind Direction          |
| WSPD     | Average Wind Speed      |
| WPGT     | Wind Peak Gust          |
| RHUM     | Relative Humidity       |
| PRES     | Sea-Level Air Pressure  |
| SNOW     | Snow Depth              |
| TSUN     | Total Sunshine Duration |
| COCO     | Weather Condition Code  |

## Meteorological Data Units

| **Parameter(s)**           | **Unit**       |
|----------------------------|----------------|
| Temperature                | °C             |
| Precipitation              | mm             |
| Sunshine Duration          | Minutes, Hours |
| Air Pressure               | hPa            |
| Wind Speed, Peak Wind Gust | km/h           |
| Wind Direction             | Degrees        |
| Visibility, Cloud Height   | m              |
| Relative Humidity          | %              |

## Weather Condition Codes

Hourly weather data may include information on the observed weather condition. Please note that the weather condition is not a key parameter for the Meteostat project. METAR reports issued by weather stations located at airports only report significant weather events. Also, some weather stations do not provide weather condition data at all.

Weather conditions are indicated by an integer value between 1 and 27 according to this list:

| **Code** | **Weather Condition** |
|----------|-----------------------|
| 1        | Clear                 |
| 2        | Fair                  |
| 3        | Cloudy                |
| 4        | Overcast              |
| 5        | Fog                   |
| 6        | Freezing Fog          |
| 7        | Light Rain            |
| 8        | Rain                  |
| 9        | Heavy Rain            |
| 10       | Freezing Rain         |
| 11       | Heavy Freezing Rain   |
| 12       | Sleet                 |
| 13       | Heavy Sleet           |
| 14       | Light Snowfall        |
| 15       | Snowfall              |
| 16       | Heavy Snowfall        |
| 17       | Rain Shower           |
| 18       | Heavy Rain Shower     |
| 19       | Sleet Shower          |
| 20       | Heavy Sleet Shower    |
| 21       | Snow Shower           |
| 22       | Heavy Snow Shower     |
| 23       | Lightning             |
| 24       | Hail                  |
| 25       | Thunderstorm          |
| 26       | Heavy Thunderstorm    |
| 27       | Storm                 |
