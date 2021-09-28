# Sort list by nth element of sublist

Here's the table of contents:

1. TOC
{:toc}

## Sort list

```
whichEl = 2; # third Element
def Sort(sub_li):
    l = len(sub_li)
    for i in range(0, l):
        for j in range(0, l-i-1):
            if (sub_li[j][whichEl] > sub_li[j + 1][whichEl]):
                tempo = sub_li[j]
                sub_li[j]= sub_li[j + 1]
                sub_li[j + 1]= tempo
    return sub_li
sorted_by_whichEl = (Sort(sub_li));
```

[See!](https://www.geeksforgeeks.org/python-sort-list-according-second-element-sublist/)

