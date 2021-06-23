---
title: Nearby | Weather Stations | JSON API
---

# Nearby Weather Stations

This endpoint enables users to find nearby weather stations by geo location. When calling this endpoint, make sure to provide valid geographic coordinates (decimal degrees) using the `lat` (latitude) and `lon` (longitude) parameters. The `limit` parameter allows us to specify the maximum number of weather stations returned by this endpoint.

By default, the endpoint only returns weather stations which are closer than 100 kilometers to the specified geo location. If you want to limit your query to a certain radius, just set the `radius` parameter to any integer value.

## Endpoint

The endpoint is available through this URL:

```
GET https://meteostat.p.rapidapi.com/stations/nearby
```

## Parameters

When calling this endpoint, please refer to the following parameters.

| **Parameter** | **Description**                   | **Types** | **Required** | **Default** |
|:--------------|:----------------------------------|:----------|:-------------|:------------|
| lat           | The latitude of the location      | Float     | Yes          | `undefined` |
| lon           | The longitude of the location     | Float     | Yes          | `undefined` |
| limit         | The maximum number of results     | Integer   | No           | 10          |
| radius        | The radius of the query in meters | Integer   | No           | 100000      |

## Response

The response body includes the following properties.

| **Parameter** | **Description**                                     | **Type** |
|:--------------|:----------------------------------------------------|:---------|
| id            | The Meteostat ID of the weather station             | String   |
| name          | Name of the weather station in different languages  | Object   |
| distance      | The distance to the provided geo location in meters | Float    |

## Example

This example requires the cURL command-line interface. Alternatively, you can use an API client like Postman.

```sh
curl --request GET \
	--url 'https://meteostat.p.rapidapi.com/stations/nearby?lat=51.5085&lon=-0.1257' \
	--header 'x-rapidapi-host: meteostat.p.rapidapi.com' \
	--header 'x-rapidapi-key: {key}'
```

Please replace `{key}` with your personal API key.

### Data Response

The response should look like that:

```json
{
    "meta": {
        "exec_time": 0.197,
        "generated": "2021-06-23 12:02:41"
    },
    "data": [
        {
            "id": "03779",
            "distance": 1104.3
        },
        {
            "id": "EGLC0",
            "distance": 16804.1
        },
        {
            "id": "03672",
            "distance": 20652.3
        },
        {
            "id": "03772",
            "distance": 22624.4
        },
        {
            "id": "03781",
            "distance": 23370
        },
        {
            "id": "EGKB0",
            "distance": 24009.3
        },
        {
            "id": "EGTI0",
            "distance": 27961.2
        },
        {
            "id": "03776",
            "distance": 40063.6
        },
        {
            "id": "03673",
            "distance": 43155.8
        },
        {
            "id": "EGUH0",
            "distance": 46423.7
        }
    ]
}
```
