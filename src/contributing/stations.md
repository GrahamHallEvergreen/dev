---
title: Weather Stations | Contributing
---

# Weather Stations

A weather station is a location where meteorological data is measured. Most countries operate public weather station networks in order to monitor weather and climate. Meteostat provides an open directory of weather stations everyone can edit, share and build upon. The list of weather stations is available on [GitHub](https://github.com/meteostat/weather-stations).

If you want to download a full dump of all weather stations, please refer to the [bulk data documentation](/bulk/stations) for more information.

## Data Structure

The `stations` directory contains one JSON file per weather station. The files are named after the station's Meteostat ID and hold one JSON object which describes the respective weather station.

### Properties

Each weather station must provide the following properties. Missing values are defined as `null`.

* `id`: The Meteostat ID of the weather station
* `name`: Object containing the name of the weather station in different languages
* `country`: ISO 3166-1 alpha-2 country code of the weather station (e.g. CA for Canada)
* `region`: The ISO 3166-2 state or region code of the weather station (e.g. TX for Texas)
* `identifiers`: Object containing different identifiers of the weather station
    * `national`: The national ID of the weather station
    * `wmo`: The WMO ID of the weather station
    * `ghcn`: The GHCN ID of the weather station
    * `wban`: The WBAN ID of the weather station
    * `usaf`: The USAF ID of the weather station
    * `mosmix`: The MOSMIX ID of the weather station
    * `icao`: The ICAO ID of the weather station
    * `iata`: The IATA ID of the weather station
* `location`: Object describing the location of the weather station
    * `latitude`: The latitude of the weather station
    * `longitude`: The longitude of the weather station
    * `elevation`: The elevation of the weather station in meters above sea level
* `timezone`: The time zone of the weather station
* `history`: An array that provides previous locations, identifiers or names of the weather station

## Formatting

* All files in the `stations` directory are named after the station's Meteostat ID.
* Names of weather stations are capitalized.
* Use short and descriptive names for a weather station.
* Many weather stations are located at aerodromes. When naming weather stations please refer to aerodromes, which involve air cargo or passengers, as *airports* and use the term *airfield* if they don't.

## Making Changes

If you want to add a new weather station, update some information or correct an error, please either correct/update the affected file(s) & create a pull request or [fill an issue](https://github.com/meteostat/weather-stations/issues/new) & describe your concern. We will review each request and update the list accordingly. Once your changes are merged into the `master` branch they will be visible in all Meteostat products within a few days.
