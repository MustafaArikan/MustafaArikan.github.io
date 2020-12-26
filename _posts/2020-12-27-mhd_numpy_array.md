# Read .mhd file and convert to numpy

Here's the table of contents:

1. TOC
{:toc}

## Snippet to load and convert

```
from SimpleITK as sitk
import numpy as np

image = sitk.ReadImage("image.mhd");
image = sitk.GetArrayFromImage(image);
print (image.shape);

```
