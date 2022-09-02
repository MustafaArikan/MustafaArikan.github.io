# Snippet for normalizing numpy array

Here's the table of contents:

1. TOC
{:toc}

## Generate data

```
import numpy as np

randomValues = np.random.uniform(low=1000.0, high=10000.0, size=(300,))
```

## Using numpy

```
import numpy as np

def NormalizeData(data, maxVal = 255.0):
    return ((data - np.min(data)) / (np.max(data) - np.min(data)))*maxVal

scaled_x = NormalizeData(randomValues)

scaled_x = np.round(NormalizeData(randomValues)).astype('uint8')

print(np.max(scaled_x), np.min(scaled_x))
```



[See!](https://www.stackvidhya.com/how-to-normalize-data-between-0-and-1-range/)







