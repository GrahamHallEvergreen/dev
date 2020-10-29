# Python Library

The Meteostat Python library provides a simple programming interface for accessing open weather and climate data. The historical observations and statistics are obtained from Meteostat's [bulk data interface](/bulk/) and consist of data provided by different public interfaces, most of which are governmental. Among the [data sources](/docs/sources.html) are national weather services like the National Oceanic and Atmospheric Administration (NOAA) and Germany's national meteorological service (DWD).

## Installation

The Meteostat Python package is available through [PyPI](https://pypi.org/project/meteostat/):

```
pip install meteostat
```

## Quick Start

Let's pretend you want to plot temperature data for Vancouver, BC from 2018:

```python
# Import Meteostat library and dependencies
from meteostat import Stations, Daily
from datetime import datetime
import matplotlib.pyplot as plt

# Get closest weather station to Vancouver, BC
stations = Stations(lat = 49.2497, lon = -123.1193)
station = stations.fetch(1)

# Get daily data for 2018 at the selected weather station
data = Daily(station, start = datetime(2018, 1, 1), end = datetime(2018, 12, 31))
data = data.fetch()

# Plot line chart including average, minimum and maximum temperature
data.plot(x = 'time', y = ['tavg', 'tmin', 'tmax'], kind = 'line')
plt.show()
```

### Output

![2018 temperature data for Vancouver, BC](./py-example-chart.png)
