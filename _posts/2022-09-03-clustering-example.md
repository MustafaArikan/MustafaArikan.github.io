# Snippet for clustering example

Here's the table of contents:

1. TOC
{:toc}

## Introduction (cities with coordinates)

```
#Cities_Cluster.ipynb
from geopy.geocoders import Nominatim
import time
import numpy as np
from pprint import pprint
app = Nominatim(user_agent="tutorial")

# Define 6 groups of cities, which are roughly connected

cities = ["Nairobi, Kenya", "Mombasa, Kenya", "Nakuru, Kenya", "Ruiru, Kenya", "Eldoret, Kenya", "Kisumu, Kenya",
          "New York, United States", "Los Angeles, United States","Chicago, United States","Chicago, United States","Houston, United States","Phoenix, United States","San Antonio, United States",
          "Kiel, Germany", "Hamburg, Germany", "Berlin, Germany", "Cologne, Germany", "Mainz, Germany", "Freiburg, Germany", "Konstanz, Germany",
          "Yokohama, Japan","Kobe, Japan","Incheon, South Korea","Shanghai, China",
          "Buenos Aires, Argentina","Rosario, Argentina","La Plata, Argentina","Salta, Argentina",
         "Sydney, Australia","Melbourne, Australia","Brisbane, Australia","Perth, Australia","Adelaide, Australia","Hobart, Australia","Darwin, Australia"]
         #"Cambridge, UK","London, UK","Watford, UK","Edinburgh, UK","Oxford, UK","Leicester, UK","Southampton, UK","Manchester, UK","Liverpool, UK","Aberdeen, UK"]
         #"Linz, Austria","Inzersdorf im Kremstal, Austria","Vienna, Austria","Salzburg, Austria","Graz, Austria","Wels, Austria"]
         #"Vancouver, Canada","Edmonton, Canada","Montreal, Canada","Toronto, Canada","London, Canada",]
         
#for 
x_ = [];
y_ = [];
citiesKM = [];
for i in range(0, len(cities)):
    location = app.geocode(cities[i]).raw
    #print (location['lat']);
    x_.append(location['lat'])
    y_.append(location['lon'])
    citiesKM.append((location['lat'], location['lon']))
```

## Calculate distance or affinity matrix

```
# Import the geodesic module from geopy library 
from geopy.distance import geodesic as GD
 # For the specified locations, load their latitude and longitude data.
#Finally, print the distance between the two sites in kilometers.

matrix = np.zeros((len(cities), len(cities)), 'float32')

for i in range(0, len(cities)):
    for j in range(0, len(cities)):
        if(i == j):
            matrix[i,j] = 1.0;
        else:
            matrix[i,j] = -1.0*GD(citiesKM[i],citiesKM[j]).km
            
def NormalizeData(data):
    return (data - np.min(data)) / (np.max(data) - np.min(data))
    
matrix = NormalizeData(matrix)


```

## Visualize matrix and show distance between two cities as example

```
from matplotlib import pylab as plt
plt.imshow(matrix,cmap="gray")



# Import the geodesic module from geopy library 
from geopy.distance import geodesic as GD
 # For the specified locations, load their latitude and longitude data.
#Finally, print the distance between the two sites in kilometers.
print("The distance between Abuja and Dakar is: ", GD(citiesKM[0],citiesKM[-1]).km)

#The distance between Abuja and Dakar is:  10423.219350045409

```

![Cities](/images/Cities_Matrix.png)

## Spectral Clustering

```
import scipy
from sklearn.cluster import SpectralClustering
import pandas as pd

#%%time

best_k = None
stds = {} # a map of std for each k
max_clusters = 16 # max number of clusters or target classes we are okay with 

#with warnings.catch_warnings():
#    warnings.simplefilter("ignore")
    
for clusters in range(2, max_clusters):
    #print (clusters)
    sc = SpectralClustering(clusters, assign_labels='cluster_qr', random_state=1, affinity='precomputed')
    sc.fit_predict(matrix)

    std = pd.DataFrame(sc.labels_, columns=["cluster_id"]).cluster_id.value_counts().describe().loc["std"]
    stds[clusters] = std

```

## Find ideal number of clusters

```
import matplotlib.pyplot as plt
import seaborn as sns
sns.set_style('darkgrid', {'axes.facecolor': '.9'})
sns.set_palette(palette='deep')
sns_c = sns.color_palette(palette='deep')
%matplotlib inline

plt.figure(figsize=(20,20))
ax = sns.barplot(x="k", y="std", data=pd.DataFrame( stds.items(), columns=["k", "std"] ))
plt.xlabel("number of clusters")
plt.ylabel("class imbalance metric (std)")
ax.grid()



```


![Cities](/images/Clusters_Imbalance.png)






