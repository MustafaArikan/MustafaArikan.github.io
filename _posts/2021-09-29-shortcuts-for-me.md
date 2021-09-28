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



