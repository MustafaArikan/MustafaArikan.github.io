# Find and delete many files

Here's the table of contents:

1. TOC
{:toc}

## Find files first

```
find . -iname "*log.txt*"
```

## Find and delete

```
find . -iname "*log.txt*" -exec rm -rf {} \;
```
