# Read and write to files

Here's the table of contents:

1. TOC
{:toc}

## Read lines from a file

```
# Using readlines()
file1 = open('myfile.txt', 'r')
Lines = file1.readlines()
```

## Write lines

```
L = ["1\n", "2\n", "3\n"]
  
# writing to file
file1 = open('myfile.txt', 'w')
file1.writelines(L)
file1.close()
```



[See!](https://www.geeksforgeeks.org/read-a-file-line-by-line-in-python/)







