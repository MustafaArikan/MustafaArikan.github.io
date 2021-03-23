# Using find and grep to get file count per folder in a directory

Here's the table of contents:

1. TOC
{:toc}

## Using bash

Save as FileCountForEveryDirectory.sh

```
for file in ./*
do
  if [ -d "$file" ]; then
  	echo "$file"
  	find "$file"//. ! -name . -print | grep -c //
  fi
done
```

And call

```
cd /tmp/
/home/user/FileCountForEveryDirectory.sh
```

[See!](https://unix.stackexchange.com/a/1126)
