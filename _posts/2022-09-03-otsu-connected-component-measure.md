# Three interesting algorithms (otsu, connected component and measure)

Here's the table of contents:

1. TOC
{:toc}

## Otsu

```
import matplotlib.pyplot as plt
from skimage import data
from skimage import filters
from skimage import exposure

camera = data.camera()
val = filters.threshold_otsu(camera)

hist, bins_center = exposure.histogram(camera)

plt.figure(figsize=(9, 4))
plt.subplot(131)
plt.imshow(camera, cmap='gray', interpolation='nearest')
plt.axis('off')
plt.subplot(132)
plt.imshow(camera < val, cmap='gray', interpolation='nearest')
plt.axis('off')
plt.subplot(133)
plt.plot(bins_center, hist, lw=2)
plt.axvline(val, color='k', ls='--')

plt.tight_layout()
plt.show()

```

[See!](https://scipy-lectures.org/packages/scikit-image/auto_examples/plot_threshold.html)


## Connected component

```
from skimage import measure
from skimage import filters
import matplotlib.pyplot as plt
import numpy as np

n = 12
l = 256
np.random.seed(1)
im = np.zeros((l, l))
points = l * np.random.random((2, n ** 2))
im[(points[0]).astype(np.int), (points[1]).astype(np.int)] = 1
im = filters.gaussian(im, sigma= l / (4. * n))
blobs = im > 0.7 * im.mean()

all_labels = measure.label(blobs)
blobs_labels = measure.label(blobs, background=0)

plt.figure(figsize=(9, 3.5))
plt.subplot(131)
plt.imshow(blobs, cmap='gray')
plt.axis('off')
plt.subplot(132)
plt.imshow(all_labels, cmap='nipy_spectral')
plt.axis('off')
plt.subplot(133)
plt.imshow(blobs_labels, cmap='nipy_spectral')
plt.axis('off')

plt.tight_layout()
plt.show()
```

[See!](https://scipy-lectures.org/packages/scikit-image/auto_examples/plot_labels.html)


## Measure (on label image)

```
for j in range(0, 10, 1):
  labels = measure.label(all_labels==cnt[np.argsort(vls)[j]])

  props = measure.regionprops(labels, img)
  properties = ['area', 'eccentricity', 'perimeter', 'orientation'] #, 'moments_central', 'moments'] #, 'intensity_mean']

  oritn = getattr(props[0], 'orientation');
  print (oritn)
```


[See!](https://vincmazet.github.io/bip/mm/measure.html)
[See!](https://jni.github.io/i2k-skimage-napari/lectures/2_segmentation_and_regionprops.html)
