# Bulk Data

The Meteostat bulk data interface provides access to full data dumps of individual weather stations. The data is provided in CSV (weather data) and JSON (weather stations) format. Users are **not required to sign up** for this service.

::: tip Donation
Help Meteostat provide free weather and climate data by donating via [PayPal](https://paypal.me/meteostat).
:::

## Quick Start

The download of full data dumps is dead simple and doesn’t even require an API key:

```sh
curl "https://bulk.meteostat.net/v2/hourly/10637.csv.gz" --output "10637.csv.gz"
```

With our [Python library](/python/) we're providing a simple, yet powerful, wrapper for bulk data dumps. If you're into more complex analysis you should definitely have a look at it.

## Endpoint

```
https://bulk.meteostat.net/v2
```

In contrast to our JSON API the Bulk Data interface does not require an API key. However, when using this service you must comply with our [terms of service](/terms.html). Please make sure to cache data if possible and forbear from sending malicious calls to this service.

## Update Cycle

To keep the load on our infrastructure as low as possible, Meteostat updates bulk data dumps individually for each weather station. The dumps are updated regularly, depending on the frequency of records. Recent hourly data should be available after a maximum of 24 hours.
