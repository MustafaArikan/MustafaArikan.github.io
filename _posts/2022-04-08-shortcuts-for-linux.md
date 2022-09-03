# Some shortcuts for Linux

Here's the table of contents:

1. TOC
{:toc}

## Show size of folders using du

```
du -chs * --exclude=/media --exclude=/mnt | sort -h
```

[See!](https://unix.stackexchange.com/questions/23692/using-exclude-with-the-du-command)

## Show installed packages when using apt

```
apt list --installed
```

[See!](https://askubuntu.com/questions/17823/how-to-list-all-installed-packages)

## Show differences between folders

```
diff -qr dir1 dir2
```

[See!](https://stackoverflow.com/questions/6217628/diff-to-output-only-the-file-names)

## Run linux command from python and get the output

```
import subprocess
result = subprocess.run(['ls', '-l'], stdout=subprocess.PIPE)
result.stdout
```

[See!](https://stackoverflow.com/questions/4760215/running-shell-command-and-capturing-the-output)



