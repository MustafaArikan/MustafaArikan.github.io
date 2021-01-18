# Read .mhd/.mha/.raw metaio image/volume with SimpleITK

Here's the table of contents:

1. TOC
{:toc}

## Use ReadImage to load and convert to a numpy array

```
    import SimpleITK as sitk
    volume = sitk.ReadImage("./image.mhd");
    volume_np = sitk.GetArrayFromImage(volume);
    print (volume_np.shape);
```

[See!](http://insightsoftwareconsortium.github.io/SimpleITK-Notebooks/Python_html/03_Image_Details.html)
