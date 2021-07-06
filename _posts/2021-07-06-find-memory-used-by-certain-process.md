# Find memory usage of a certain process

Here's the table of contents:

1. TOC
{:toc}

## Find the processes

```
ps -eo size,pid,user,command --sort -size | awk '{ hr=$1/1024 ; printf("%13.2f Mb ",hr) } { for ( x=4 ; x<=NF ; x++ ) { printf("%s ",$x) } print "" }' | grep "python "
```

[See!](https://unix.stackexchange.com/a/383639)
