---
title: meteostat.Monthly.count | API | Python Library
---

# meteostat.Monthly.count

The `count()` method returns the total number of records in the query result as an integer.

## Parameters

This method does not take any parameters.

## Returns

Integer

## Example

Get the total number of records ever recorded at Atlanta International Airport.

```python{4}
from meteostat import Monthly

data = Monthly('72219')
count = data.count()

print(count)
```
