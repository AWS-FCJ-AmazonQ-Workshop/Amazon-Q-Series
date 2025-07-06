---
title: "Giải pháp Python End-to-End"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

#### Bước 1 - Thiết lập
**Môi trường phát triển Python và các thư viện cần thiết**
Để chạy workshop này, bạn sẽ cần một IDE Python (Integrated Development Environment) được kích hoạt với Amazon Q Developer. Một ví dụ là Microsoft VS Code.

Bạn cần cài đặt phiên bản Python mới (phiên bản 3.9 trở lên) với các thư viện sau:

- **streamlit**: thư viện chính để phát triển ứng dụng streamlit
- **pandas**: thư viện để thao tác với dataframes (nhập, chuẩn bị, chuyển đổi dữ liệu)
- **matplotlib và seaborn**: các thư viện biểu đồ để trực quan hóa dữ liệu
- **jupyter**: để kích hoạt môi trường Jupyter notebook trong trường hợp IDE của bạn hỗ trợ (vui lòng tham khảo tài liệu IDE của bạn để biết chi tiết về hỗ trợ và Jupyter notebooks)

Sao chép và chạy lệnh sau trong cửa sổ terminal để cài đặt các thư viện này:

```bash
pip install streamlit pandas matplotlib seaborn jupyter
```

**Cấu trúc thư mục**
1. Tạo một thư mục cơ sở cho dự án Streamlit này, ví dụ: `~/documents/code/streamlit-project`. Tất cả các đường dẫn tiếp theo sẽ tương đối với thư mục này.
2. Mở cửa sổ terminal và thay đổi đường dẫn hiện tại đến thư mục cơ sở mới được tạo.
3. Tạo một thư mục có tên `data`. Tập dữ liệu sẽ được sao chép và làm sạch trong thư mục này.
4. Tạo một tệp trống có tên `weather.py` trong thư mục cơ sở của dự án.
5. Tạo một tệp trống có tên `data.ipynb` trong thư mục `/data`.

Cấu trúc thư mục của bạn sẽ trông như thế này:

```
base-folder
├── data
└── weather.py
```

**Ứng dụng streamlit 'Hello World'**
1. Mở `weather.py` và thêm mã sau:

```python
import streamlit as st

st.write('Hello worlds from Streamlit!')
```

2. Chạy streamlit:
   - Mở cửa sổ terminal và đảm bảo rằng thư mục làm việc của bạn là thư mục cơ sở nơi `weather.py` được lưu.
   - Chạy lệnh sau:

```bash
streamlit run weather.py
```

Nếu streamlit được cài đặt đúng cách, bạn sẽ thấy kết quả như sau:

- **Local URL**: `http://localhost:8501`
- **Network URL**: `http://192.168.4.89:8501`

![alt text](/images/5-solutions/5.1-python-e2e/image.png?width=90pc)


{{% notice note %}}
-Bạn có thể thấy địa chỉ IP hoặc cổng khác. Trong một số hệ thống, streamlit tự động mở tab trình duyệt và tải ứng dụng. Nếu không phải trường hợp của bạn, chỉ cần mở tab trình duyệt với URL.
-Giữ phiên terminal đang chạy. Bạn không cần chạy lại lệnh terminal mỗi khi script được sửa đổi. Để tải script mới, chỉ cần nhấp vào 'rerun' trên trang ứng dụng (bạn có thể tìm thấy nó bằng cách nhấp vào ba dấu chấm ở góc trên bên phải của trang).
-Để dừng ứng dụng streamlit, nhấn `Ctrl+C` tại cửa sổ terminal.
-Nếu ứng dụng của bạn chứa lỗi, bạn sẽ thấy thông báo lỗi cả ở cửa sổ terminal và dưới dạng pop-up trong cửa sổ ứng dụng.
{{% /notice %}}

#### Bước 2 - Chuẩn bị dữ liệu
**Tải xuống tập dữ liệu**
Tải xuống tập dữ liệu này ở định dạng CSV từ [đây](/images/5-solutions/5.1-python-e2e/https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/e2226eb6-f109-47ae-b2c5-f02bf73b7d0e/weather_data_orig.csv) và lưu nó trong thư mục `/data` dưới tên `weather_data_orig.csv`.

```
base-folder
├── data
  └── weather_data_orig.csv
```

**Làm sạch tập dữ liệu**
Để minh họa cách Amazon Q Developer có thể đồng hành với bạn từng bước trong quá trình làm sạch dữ liệu, bạn sẽ sử dụng Jupyter notebook để thực hiện việc làm sạch này một cách tương tác.

Đây là các bước mà bạn sẽ thực hiện trong quá trình làm sạch:

```text
+------------------------+
|      Import CSV        |
+------------------------+
           |
           v
+------------------------+
| Remove Null Value Rows |
+------------------------+
           |
           v
+----------------------------+
| Keep Only Used Columns     |
+----------------------------+
           |
           v
+----------------------------+
|   Create New Columns       |
+----------------------------+
           |
           v
+----------------------------+
|     Type Conversion        |
+----------------------------+
           |
           v
+----------------------------+
| Replace Nulls with Values  |
+----------------------------+
           |
           v
+----------------------------+
|   Write to Output File     |
+----------------------------+
  ```

Mở `data/data.ipynb` (đã tạo ở bước trước) trong IDE hỗ trợ Jupyter. Bắt đầu làm theo các hướng dẫn dưới đây từng bước một và sử dụng Amazon Q Developer bằng cách cung cấp các prompt được đề cập hoặc sử dụng gợi ý của nó để tự động hoàn thành dòng mã.

**Prompt đơn dòng**
```python
import pandas as pd
# import weather_data.csv as a dataframe
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df = pd.read_csv("weather_data.csv")
```
{{% /expand%}}

```python
# remove null value rows where TMAX or TMIN columns are null, inplace
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df.dropna(subset=['TMAX', 'TMIN'], inplace=True)
```
{{% /expand%}}


```python
# reduce the dataframe and only keep the following columns: STATION, NAME, DATE, TAVG, TMAX, TMIN
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df = df[['STATION','NAME','DATE','TAVG','TMAX','TMIN']]
```
{{% /expand%}}

```python
# create new columns named "Country" using column "NAME" in the dataframe
# the data for the column has two words separated by a "comma", so we use the split() method to split the string into two words
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df['COUNTRY'] = df['NAME'].str.split(',').str[1]
df['STATIONNAME'] = df['NAME'].str.split(', ').str[0]
```
{{% /expand%}}

```python
# for the dataframe convert TMIN, TMAX, and TAVG columns to float
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df['TMIN'] = df['TMIN'].astype(float)
df['TMAX'] = df['TMAX'].astype(float)
df['TAVG'] = df['TAVG'].astype(float)
```
{{% /expand%}}

```python
# for the dataframe TAVG, if TAVG is NaN then assign TAVG = (TMAX + TMIN)/2
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df.loc[df['TAVG'].isnull(), 'TAVG'] = (df['TMAX'] + df['TMIN']) / 2
```
{{% /expand%}}

```python
# for the dataframe convert DATE column to datetime
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df['DATE'] = pd.to_datetime(df['DATE'])
```
{{% /expand%}}

```python
# write df to a csv file using utf-8 encoding and double quotes the data

```
{{%expand "Gợi ý của Amazon Q Developer" %}}
```python
df.to_csv('weather_data.csv', encoding='utf-8', doublequote=True,index=False)
```
{{% /expand%}}

#### Prompt nhiều dòng
Trong phần trước, cách tiếp cận là cung cấp các prompt một dòng zero shot để tạo mã từng bước một. Điều này hoạt động rất tốt nếu bạn đang khám phá và tìm hiểu dữ liệu một cách tương tác và bạn không chắc chắn về tất cả các bước cần thiết. Trong trường hợp bạn biết tất cả các bước để làm sạch dữ liệu, một tùy chọn khác là cung cấp một prompt nhiều dòng với tất cả các bước trong một prompt. Đầu ra của prompt nhiều dòng này có thể khác với phương pháp từng bước trước đó vì Amazon Q Developer sẽ cố gắng cung cấp mã có thể được tối ưu hóa hơn dựa trên tất cả ngữ cảnh. Bạn có thể thử điều này bằng cách kết hợp tất cả các prompt từ đầu trong một prompt nhiều dòng ở đây và so sánh với mã được tạo trước đó.

#### Prompt (Sử dụng Q-Developer Chat)

```text
For every step of the following generate the code in one code block.
Take your time, iterate through your answer multiple time.
Do not rush through any of steps. Do not skip any  of the step.
Every step should have code.
Do not forget to add comments to your code.
Do not forget to add docstrings to your code.

"""
read an input csv file and load it into a dataframe
remove null value rows where TMAX or TMIN columns are null
keep only following columns: STATION,NAME,DATE,TAVG,TMAX,TMIN
create new columns named Country using column NAME by splitting it on comma and take the last segment and delete trailing spaces
create new columns named StationName using column Name by splitting it on comma and take the first segment
convert TMIN,TMAX and TAVG columns to float
if TAVG is NaN then assign TAVG = (TMAX + TMIN)/2
convert DATE column to datetime
write df to a csv file using utf-8 encoding and double quotes
"""
```

{{%expand "Gợi ý của Amazon Q Developer" %}}
```python

"""

1. Read an input csv file weather_data.csv and load it into a dataframe
"""
import pandas as pd

df = pd.read_csv('weather_data.csv')

"""
2. Remove null value rows from the dataframe where TMAX or TMIN columns are null
"""
df = df.dropna(subset=['TMAX', 'TMIN'])

"""
3. Then, drop all columns of the dataframe except STATION,NAME,DATE,TAVG,TMAX,TMIN
"""
df = df[['STATION', 'NAME', 'DATE', 'TAVG', 'TMAX', 'TMIN']]

"""
4. Then the column named "NAME", Split the value into two parts and split using a  "comma"
"""
df[['STATIONNAME', 'COUNTRY']] = df['NAME'].str.split(',', expand=True)

"""
5. Then, Create a column named "Country" from the last part of the split delete trailing spaces
"""
df['COUNTRY'] = df['COUNTRY'].str.strip()

"""
6. Then, Create a column named "STATIONNAME" from the first part of the split
"""
df['STATIONNAME'] = df['STATIONNAME'].str.strip()

"""
7. Then, for columns TMIN, TMAX, and TAVG convert the values to float
"""
df[['TMIN', 'TMAX', 'TAVG']] = df[['TMIN', 'TMAX', 'TAVG']].astype(float)

"""
8. Then, from the datafraem, if TAVG is NaN then assign TAVG = (TMAX + TMIN)/2
"""
df.loc[df['TAVG'].isna(), 'TAVG'] = (df['TMAX'] + df['TMIN']) / 2

"""
9. Then, for the dataframe, convert the "DATE" column to a datetime
"""
df['DATE'] = pd.to_datetime(df['DATE'])

"""
10. Then, Write the dataframe to a CSV file double-quote the values, use utf-8 encoding, and no indexing
"""
df.to_csv('weather_data_processed.csv', index=False, quoting=1, encoding='utf-8')
```
{{% /expand%}}

#### Bước 3 - Ứng dụng Streamlit

**Tệp cấu hình**
Luôn là một thực hành tốt để tạo một tệp cấu hình để tránh hardcoding đầu vào trong mã của bạn. Bạn sẽ tạo một tệp cấu hình cơ bản cho mục đích này để cho ứng dụng của bạn biết nơi tìm tập dữ liệu đã làm sạch.

Tạo một tệp văn bản trong thư mục cơ sở của dự án và đặt tên là `configuration.ini`. Sao chép các dòng sau vào tệp này (thay thế tên tệp bằng tệp đầu ra từ bước cuối cùng):

```ini
[input_data]
input_file = data/weather_data_processed.csv
```

Bạn sẽ sử dụng thư viện Python `configparser` để đọc và phân tích tệp này trong bước tiếp theo.

**Xác minh cấu trúc thư mục**
Ở giai đoạn này, thư mục dự án của bạn sẽ trông như thế này:

```
base-folder
   ├── data
   │   └── data.ipynb        <---- Notebook cho việc làm sạch dữ liệu
   │   ├──── 3413569.csv     <---- Tập dữ liệu gốc
   │   └── weather_data.csv  <---- Tập dữ liệu đã làm sạch
   ├── configuration.ini    <---- Tệp cấu hình
   └── weather.py           <---- Tệp ứng dụng Streamlit chính
```

**Khởi tạo ứng dụng Streamlit**
Mở `weather.py` từ thư mục gốc của dự án. Tệp này sẽ đóng vai trò là placeholder chính cho ứng dụng.
Xóa nội dung của nó ('Hello World').


{{% notice note %}}
-Mục tiêu là để bạn thấy Amazon Q Developer hoạt động. Các prompt cần thiết được cung cấp dưới đây nên được nhập chính xác theo trình tự được trình bày. Vui lòng làm theo toàn bộ bước này một cách chặt chẽ và không bỏ qua bất kỳ phần nào.
-Các phản hồi dự kiến từ prompt được cung cấp sau mỗi prompt. Khuyến nghị bạn tạo phản hồi của riêng mình bằng cách sử dụng Amazon Q Developer và so sánh chúng với các câu trả lời được cung cấp.
-Ở một số nơi, bạn cần thêm một số dòng mã theo trình tự mà không sử dụng prompt của Amazon Q Developer.
-Bằng cách tiếp tục nhấn enter sau khi tạo mã, Amazon Q Developer có thể gợi ý cho bạn thêm các dòng mã có thể thú vị và hữu ích. Đừng ngần ngại khám phá các mã tiếp tục.
{{% /notice %}}

{{% notice note %}}
Đừng quên nhấp vào rerun sau mỗi lần bạn sửa đổi script để xem kết quả. Bạn có thể tìm thấy rerun ở góc trên bên phải của trang ứng dụng (nhấp vào ba dấu chấm).
{{% /notice %}}

{{% notice note %}}
Q Developer, giống như bất kỳ công cụ AI Tạo sinh nào, về bản chất là không xác định. Mã được tạo bởi Q Developer có thể không giống với mã được cung cấp trong giải pháp. Luôn kiểm tra xem có bao nhiêu gợi ý được cung cấp bởi Q Developer và chọn cái phù hợp nhất với yêu cầu của bạn.
{{% /notice %}}

**Import các thư viện cần thiết**
```python
import streamlit as st
import configparser
import os, sys
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

Xin lưu ý rằng nếu bạn không import một số thư viện này từ đầu, Amazon Q Developer sẽ gợi ý thêm các thư viện cần thiết tại chỗ nếu cần.

**Đọc tệp cấu hình và tải tập dữ liệu**

**Prompt**
```python
# The configuration file name is 'configuration.ini' in the same folder

# get the directory name and file name of the script
```

**Gợi ý của Amazon Q Developer**
```python
dir_name = os.path.dirname(os.path.abspath(ini_file_name))
file_name = os.path.basename(ini_file_name)

# get the directory name of the parent directory
parent_dir_name = os.path.dirname(dir_name)
```

**Prompt**
```python
# read the ini configuration file named "configuration.ini"
```

**Gợi ý của Amazon Q Developer**
```python
config = configparser.ConfigParser()
full_file_name = os.path.join(dir_name, file_name)

config.read(full_file_name)
```

**Prompt**
```python
# get the "input_file" name, from the  "input_data" section from the configuration ini file
```

**Gợi ý của Amazon Q Developer**
```python
input_file = config.get("input_data", "input_file")
```

Bạn có thể cần điều chỉnh tên của phần cấu hình và tên tham số trong mã được tạo.

**Prompt**
```python
# create function called load_data. passing into the function is the file_name

# return the dataframe and decorate it as st.cache_data
```

**Gợi ý của Amazon Q Developer**
```python
@st.cache_data
def load_data(data_file_name):
  df = pd.read_csv(data_file_name)
  return df
```

**Prompt**
```python
# load the data into a dataframe
```

**Gợi ý của Amazon Q Developer**
```python
df = load_data(input_file)
```

Caching là một chức năng thú vị trong Streamlit. Vì Streamlit là một script chạy từ trên xuống dưới mỗi khi một phần tử thay đổi (ví dụ: nhập dữ liệu vào các widget, hoặc sửa đổi script), bạn cần thận trọng để không lặp lại các hoạt động tiêu tốn nhiều tài nguyên như tải dữ liệu mỗi khi script chạy. Vì mục đích này, bạn có thể trang trí các hàm mà bạn muốn cache với `st.cache_data` và Streamlit sẽ lo liệu cho bạn. Về cơ bản, mỗi khi Streamlit cần gọi hàm được trang trí, nó sẽ xác minh xem mã và đầu vào có giống nhau không. Nếu đúng như vậy, nó sẽ không chạy hàm và giữ lại các giá trị mà không tiêu thụ bất kỳ tài nguyên nào.

Còn nhiều điều về caching trong Streamlit. Bạn có thể tham khảo tài liệu để biết thêm thông tin và ví dụ: [Caching](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/advanced-features/caching).

**Prompt**
```python
# in the dataframe, convert the "DATE" column to datetime
```

**Gợi ý của Amazon Q Developer**
```python
df["DATE"] = pd.to_datetime(df["DATE"])
```

**Bố cục trang chính**
Ứng dụng được cấu thành từ một bố cục đơn giản, với một tiêu đề và một chế độ xem tab với hai tab: một để xem tập dữ liệu đã tải và tab kia để trực quan hóa dữ liệu thời tiết bằng cách sử dụng đầu vào để chọn trạm thời tiết và phạm vi ngày.

**Prompt (Trong Cửa sổ Chat)**
```python
# use markdown to write a streamlit level 1 header

# the format of the header is

# mostly_sunny Weather Data Visualization snow_cloud
```

**Gợi ý của Amazon Q Developer**
```python
st.header(":mostly_sunny: Weather Data Visualization :snow_cloud:")
st.markdown("---")
```

Như bạn có thể thấy, Streamlit hỗ trợ ngôn ngữ Markdown cũng như Emojis. Ở đây, phương thức `st.write` được sử dụng nhưng bạn có thể sử dụng Streamlit magic để viết Markdown trực tiếp trong mã của bạn mà không cần sử dụng bất kỳ phương thức nào. Để biết thêm thông tin: [Magic](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/api-reference/write-magic/magic).

Nếu bạn cập nhật ứng dụng Streamlit, bạn sẽ thấy trang chính như thế này (Xin lưu ý rằng nếu bạn không sử dụng chế độ tối trong môi trường của mình, màu nền có thể khác).

![alt text](/images/5-solutions/5.1-python-e2e/image-1.png?width=40pc)

**Prompt**
```python
# add two tabs to the streamlit app

# first tab is called 'Data Set' and assign it to the variable tab_data_set

# second tab is called 'Single City Charts' and assign it to the variable tab_data_visualization
```

**Gợi ý của Amazon Q Developer**
```python
tab_data_set, tab_data_visualization = st.tabs(["Data Set", "Single City Charts"])
```

Ở đây bạn đang tạo giao diện người dùng trực quan đầu tiên trong Streamlit: Một chế độ xem tab. Để biết thêm thông tin, vui lòng tham khảo tài liệu: [st.tabs](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/api-reference/layout/st.tabs).

![alt text](/images/5-solutions/5.1-python-e2e/image-2.png?width=40pc)

**Tab đầu tiên: chế độ xem tập dữ liệu**
**Prompt**
```python
# write the dataframe to the first tab

# second tab will use the tab_data_visualization variable to write the dataframe
```

**Gợi ý của Amazon Q Developer**
```python
with tab_data_set:
  st.write(df)
```

![alt text](/images/5-solutions/5.1-python-e2e/image-3.png?width=40pc)

Vậy là xong! Streamlit có tích hợp mạnh mẽ với Python và Pandas dataframes để trực quan hóa với ít hoặc không cần nỗ lực.