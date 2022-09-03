# Matplotlib snippets

Here's the table of contents:

1. TOC
{:toc}

## Add patches (e.g. circles into a plot)

```
fig = plt.figure()
ax = fig.add_subplot(1, 1, 1)
rect = plt.Rectangle((0.2, 0.75), 0.4, 0.15, color='k', alpha=0.3)
circ = plt.Circle((0.7, 0.2), 0.15, color='b', alpha=0.3)
pgon = plt.Polygon([[0.15, 0.15], [0.35, 0.4], [0.2, 0.6]],
color='g', alpha=0.5)

ax.add_patch(rect)
ax.add_patch(circ)
ax.add_patch(pgon)
```



[See!](https://discuss.analyticsvidhya.com/t/how-to-add-a-patch-in-a-plot-in-python/5518)







