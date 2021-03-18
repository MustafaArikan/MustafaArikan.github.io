# Using find to find and sort files by date

Here's the table of contents:

1. TOC
{:toc}

## E.g. find html files and sort by date

Find and sort by date

`find . -iname "*.html" -printf "%T@ %Tc %p\n" | sort -n`

[See!](https://superuser.com/a/546900)
