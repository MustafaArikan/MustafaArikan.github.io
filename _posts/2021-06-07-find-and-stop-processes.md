# Find and stop linux processes

Here's the table of contents:

1. TOC
{:toc}

## Find the processes

```
ps aux | grep 'python -m joblib' | awk '{print $2}'
```

## Find the processes and kill

```
kill -9 $(ps aux | grep 'python -m joblib' | awk '{print $2}')
```

[See!](https://stackoverflow.com/a/3510850)
