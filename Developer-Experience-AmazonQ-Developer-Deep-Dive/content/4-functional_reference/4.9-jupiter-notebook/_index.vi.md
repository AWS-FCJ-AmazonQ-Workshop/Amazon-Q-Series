---
title: "Jupyter Notebook với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 9
chapter: false
pre: " <b> 4.9 </b> "
---

#### Jupyter Notebook với Amazon Q Developer

Amazon Q Developer giúp bạn viết mã trong Jupyter Notebooks và thực hiện các phân tích dữ liệu như hồi quy tuyến tính.

#### Cài đặt

1. **Cài đặt Jupyter Notebook**
   - Mở cửa sổ terminal
   - Gõ `pip install jupyterlab` và nhấn Enter
   - Gõ `jupyter notebook` và nhấn Enter

2. **Cài đặt Amazon Q Developer Extension cho Jupyter Notebook**
   - Mở cửa sổ terminal
   - Trong tab Extensions của VSCode, tìm kiếm "jupyter" và cài đặt các extension Jupyter

3. **Cài đặt và kích hoạt môi trường ảo**
   - Mở cửa sổ terminal
   - Gõ `python -m venv venv` và nhấn Enter
   - Gõ `source venv/bin/activate` và nhấn Enter

4. **Cài đặt Pandas, Numpy, Matplotlib và Scikit-learn**
   - Mở cửa sổ terminal
   - Gõ `pip install pandas numpy matplotlib scikit-learn` và nhấn Enter

#### Jupyter Notebook - KMeans

Amazon Q Developer cung cấp gợi ý khi làm việc với Jupyter Notebooks.

**Ví dụ:**

1. Trong VSCode, tạo file jupyter notebook và đặt tên là `kmeans.ipynb`

   > **Lưu ý:** Bạn có thể sử dụng phím tắt Ctrl+Shift+P để mở command palette và gõ "Jupyter: Create New Blank Notebook" để tạo file notebook mới.

2. **Import thư viện**
   ```python
   # import pandas as pd
   # import numpy as np
   # import matplotlib.pyplot as plt
   ```

   **Kết quả:**
   ```python
   import pandas as pd
   import numpy as np
   import matplotlib.pyplot as plt
   from sklearn.cluster import KMeans
   ```

3. **Đọc dữ liệu**
   ```python
   """
   # read the data.json file into a dataframe
   """
   ```

   **Kết quả:**
   ```python
   df = pd.read_json('data.json')
   ```

4. **Xem 5 dòng đầu tiên**
   ```python
   """
   # Get the first 5 rows of the dataframe
   """
   ```

   **Kết quả:**
   ```python
   df.head()
   ```

5. **Lấy thông tin về dataframe**
   ```python
   """
   # Get information about the dataframe
   """
   ```

   **Kết quả:**
   ```python
   df.info()
   ```

6. **Lấy tọa độ x từ cột Elevation**
   ```python
   """
   # get x coordinates from the Elevation column in the data frame
   """
   ```

   **Kết quả:**
   ```python
   x = df['Elevation']
   ```

7. **Lấy tọa độ y từ cột HR**
   ```python
   """
   # get y coordinates from the HR column
   """
   ```

   **Kết quả:**
   ```python
   y = df['HR']
   ```

8. **Vẽ biểu đồ scatter plot**
   ```python
   """
   # scatter plot the x and y coordinates
   """
   ```

   **Kết quả:**
   ```python
   plt.scatter(x, y)
   plt.show()
   ```

9. **Tạo danh sách tọa độ**
   ```python
   """
   # turn the dataset into a list set of coordinates using zip
   """
   ```

   **Kết quả:**
   ```python
   coordinates = list(zip(x, y))
   ```

10. **Tạo đối tượng KMeans**
    ```python
    """
    # create a kmeans object with k=2
    """
    ```

    **Kết quả:**
    ```python
    kmeans = KMeans(n_clusters=2)
    ```

11. **Huấn luyện mô hình**
    ```python
    """
    # fit the kmeans object to the coordinates
    """
    ```

    **Kết quả:**
    ```python
    kmeans.fit(coordinates)
    ```

12. **Lấy nhãn cluster**
    ```python
    """
    # get the cluster labels
    """
    ```

    **Kết quả:**
    ```python
    labels = kmeans.labels_
    ```

13. **Lấy tâm cluster**
    ```python
    """
    # get the cluster centers
    """
    ```

    **Kết quả:**
    ```python
    centers = kmeans.cluster_centers_
    ```

14. **Vẽ tâm cluster**
    ```python
    """
    # plot the cluster centers
    """
    ```

    **Kết quả:**
    ```python
    plt.scatter(centers[:, 0], centers[:, 1], c='red', s=100, alpha=0.5)
    ```

15. **Vẽ tọa độ với nhãn**
    ```python
    """
    # plot the x and y coordinates with labels
    """
    ```

    **Kết quả:**
    ```python
    plt.scatter(x, y, c=labels, s=50, cmap='viridis')
    plt.show()
    ```

16. **Ghi tọa độ tâm ra file CSV**
    ```python
    """
    # write the centroid coordinates to a csv file
    """
    ```

    **Kết quả:**
    ```python
    import csv
    def write_centroid_csv(centroid_coords, output_file):
        with open(output_file, 'w') as csv_file:
            writer = csv.writer(csv_file)
            writer.writerow(['x', 'y'])
            for coord in centroid_coords:
                writer.writerow([coord[0], coord[1]])
        return True

    write_centroid_csv(centers, "all_centers.csv")
    ```