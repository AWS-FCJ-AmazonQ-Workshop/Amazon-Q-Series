---
title: "Jupyter Notebook with Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 9
chapter: false
pre: " <b> 4.9 </b> "
---

#### Jupyter Notebook with Amazon Q Developer

Amazon Q Developer helps you write code in Jupyter Notebooks and perform data analysis such as linear regression.

#### Setup

1. **Install Jupyter Notebook**
   - Open a terminal window
   - Type `pip install jupyterlab` and press Enter
   - Type `jupyter notebook` and press Enter

2. **Install Amazon Q Developer Extension for Jupyter Notebook**
   - Open a terminal window
   - In the VSCode Extensions tab, search for "jupyter" and install the Jupyter extensions

3. **Install and Activate Virtual Environment**
   - Open a terminal window
   - Type `python -m venv venv` and press Enter
   - Type `source venv/bin/activate` and press Enter

4. **Install Pandas, Numpy, Matplotlib, and Scikit-learn**
   - Open a terminal window
   - Type `pip install pandas numpy matplotlib scikit-learn` and press Enter

#### Jupyter Notebook - KMeans

Amazon Q Developer provides suggestions when working with Jupyter Notebooks.

**Example:**

1. In VSCode, create a Jupyter Notebook file and name it `kmeans.ipynb`

   > **Note:** You can use the keyboard shortcut Ctrl+Shift+P to open the command palette and type "Jupyter: Create New Blank Notebook" to create a new notebook file.

2. **Import Libraries**
   ```python
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   from sklearn.cluster import KMeans
   ```

3. **Read Data**
   ```python
   df = pd.read_json('data.json')
   ```

4. **View First 5 Rows**
   ```python
   df.head()
   ```

5. **Get Dataframe Information**
   ```python
   df.info()
   ```

6. **Extract X Coordinates from Elevation Column**
   ```python
   x_coords = df['Elevation']
   ```

7. **Extract Y Coordinates from HR Column**
   ```python
   y_coords = df['HR']
   ```

8. **Plot Scatter Plot**
   ```python
   plt.scatter(x_coords, y_coords)
   ```

9. **Create List of Coordinates**
   ```python
   coordinates = list(zip(x_coords, y_coords))
   ```

10. **Create KMeans Object**
    ```python
    kmeans = KMeans(n_clusters=3)
    ```

11. **Train Model**
    ```python
    kmeans.fit(coordinates)
    ```

12. **Get Cluster Labels**
    ```python
    labels = kmeans.labels_
    ```

13. **Get Cluster Centers**
    ```python
    centers = kmeans.cluster_centers_
    ```

14. **Plot Cluster Centers**
    ```python
    plt.scatter(centers[:, 0], centers[:, 1], c='red', marker='x')
    ```

15. **Plot Coordinates with Labels**
    ```python
    plt.scatter(x_coords, y_coords, c=labels)
    ```

16. **Write Cluster Centers to CSV File**
    ```python
    pd.DataFrame(centers, columns=['X', 'Y']).to_csv('cluster_centers.csv', index=False)
    ```
