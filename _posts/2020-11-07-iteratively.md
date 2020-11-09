# Search files iteratively in Python

Here's the table of contents:

1. TOC
{:toc}

## Snippet for searching files with certain ending

```
import os
rootdir = '/home/username/'

for subdir, dirs, files in os.walk(rootdir):
    for file in files:
        if(".png" in file):
            print(os.path.join(subdir, file))
```

[See!](https://stackoverflow.com/a/19587581)
