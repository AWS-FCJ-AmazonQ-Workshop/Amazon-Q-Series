---
title: "Introduction to Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

Jupyter Notebook
Use Amazon Q Developer to help you write code in Jupyter Notebooks and linear regression.

SETUP
Install Jupyter Notebook
Open a terminal window.
Type pip install jupyterlab and press enter.
Type jupyter notebook and press enter.
Install Amazon Q Developer Extension for Jupyter Notebook
Open a terminal window.
In the VSCode Extensions tab, search for jupyter and install the Jupyter extensions.
Install and Activate virtual environment
Open a terminal window.
Type python -m venv venv and press enter.
Type source venv/bin/activate and press enter.
Install Pandas, Numpy, and Matplotlib, and Scikit-learn
Open a terminal window.
Type pip install pandas numpy matplotlib scikit-learn and press enter.

Jupyter Notebook - KMeans
Amazon Q Developer can provide suggestions when working with Jupyter Notebooks.

Example #1:

Python

JavaScript

TypeScript

Go

php
In your VSCode create a jupyter notebook file and name it --> kmeans.ipynb

Note: You can use the keyboard shortcut Ctrl+Shift+P to open the command palette and type Jupyter: Create New Blank Notebook to create a new notebook file.

Note: Please follow the SETUP instructions.

Prompt:
# import pandas as pd
# import numpy as np
# import matplotlib.pyplot as plt

Amazon Q Developer Suggestion:
Imports
1
2
3
4
5
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans



Prompt:

"""
# read the data.json file into a dataframe

"""
Amazon Q Developer Suggestion:
Read
1
2

df = pd.read_json('data.json')

Prompt:
"""
# Get the first 5 rows of the dataframe


"""
Amazon Q Developer Suggestion:
First 5 rows
1
df.head()


Prompt:
"""
# Get information about the dataframe

"""
Amazon Q Developer Suggestion:
Get Info
1
df.info()


Prompt:
"""
# get x coordinates from the Elevation column in the data frame

"""
Amazon Q Developer Suggestion:
X coordinate
1
x = df['Elevation']


Prompt:
"""
# get y coordinates from the HR column


"""
Amazon Q Developer Suggestion:
Y Coordinate
1
y = df['HR']


Prompt:
"""
# scatter plot the x and y coordinates
"""
Amazon Q Developer Suggestion:
Plot X and Y
1
2
plt.scatter(x, y)
plt.show()


Prompt:
"""
# turn the dataset into a list set of coordinates using zip
"""
Amazon Q Developer Suggestion:
Create List
1
coordinates = list(zip(x, y))


Prompt:
"""
# create a kmeans object with k=2


"""
Amazon Q Developer Suggestion:
Kmeans Object
1
kmeans = KMeans(n_clusters=2)


Prompt:
"""
# fit the kmeans object to the coordinates


"""
Amazon Q Developer Suggestion:
Fit
1
kmeans.fit(coordinates)


Prompt:
"""
# get the cluster labels


"""
Amazon Q Developer Suggestion:
Labels
1
labels = kmeans.labels_


Prompt:
"""
# get the cluster centers


"""
Amazon Q Developer Suggestion:
Centers
1
centers = kmeans.cluster_centers_


Prompt:
"""
# plot the cluster centers


"""
Amazon Q Developer Suggestion:
Plot Centers
1
plt.scatter(centers[:, 0], centers[:, 1], c='red', s=100, alpha=0.5)

Prompt:
"""
# plot the x and y coordinates with labels


"""
Amazon Q Developer Suggestion:
Plot X, Y with labels
1
2
plt.scatter(x, y, c=labels, s=50, cmap='viridis')
plt.show()


Prompt:
"""
# write the centroid coordinates to a csv file

"""
Amazon Q Developer Suggestion:
Write
1
2
3
4
5
6
7
8
9
10
11
12
plt.scatter(x, y, c=labels, s=50, cmap='viridis')
import csv
def write_centroid_csv(centroid_coords, output_file):
    with open(output_file, 'w') as csv_file:
        writer = csv.writer(csv_file)
        writer.writerow(['x', 'y'])
        for coord in centroid_coords:
            writer.writerow([coord[0], coord[1]])

    return True

write_centroid_csv(centers, "all_centers.csv")
