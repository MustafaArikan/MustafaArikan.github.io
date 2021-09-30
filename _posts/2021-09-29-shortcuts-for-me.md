# Some shortcuts

Here's the table of contents:

1. TOC
{:toc}

## Read a txt file as a list

```
with open('file.txt') as f:
    lines = f.readlines()
```

[See!](https://notyet/)


## Chunks from a list

```
def chunks(lst, n):
    """Yield successive n-sized chunks from lst."""
    for i in range(0, len(lst), n):
        yield lst[i:i + n]
```

[See!](https://stackoverflow.com/a/312464)


## Change directory

```
import os
os.chdir(path)
```

## Min max normalize np array

```
import numpy as np
normalized = (x-np.min(x))/(np.max(x)-np.min(x))
```

[See!](https://stats.stackexchange.com/a/70807)


## tar a directory, use split and send files with rclone

```
tar cf big_file.tar big_file/ &
split -b 1024M ./big_file.tar big_file.tar.part &
```

or
```
tar cf - big_file | split --bytes=1024MB - big_file_tar/big_file.tar. &
```

and
```
time rclone -vv --opendrive-chunk-size=32000k --checkers=4 --transfers=8 --buffer-size=32000M copy big_file_tar/ opendrive:root/big_file_tar &> big_file.out &
```

