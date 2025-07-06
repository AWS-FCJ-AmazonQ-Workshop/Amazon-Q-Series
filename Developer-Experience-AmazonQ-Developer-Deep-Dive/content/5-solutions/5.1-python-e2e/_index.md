---
title: "Python End-to-End Solution"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 5.1 </b> "
---

#### Step 1 - Setup
**Python development environment and required libraries**
To run this workshop you will need a python IDE (Integrated Development Environment) that is enabled with Amazon Q Developer. An example would be Microsoft VS Code.

You need to have a recent python version installed (version 3.9 and above) with the following libraries:

- **streamlit**: main library to develop streamlit application
- **pandas**: library to manipulate dataframes (ingestion, preparation, transformation)
- **matplotlib and seaborn**: charting libraries to visualize data
- **jupyter**: to enable Jupyter notebook environment in case your IDE supports it (please refer to your IDE documentation for the details on support and Jupyter notebooks)

Copy and run the following command in your terminal window to have these libraries installed:

```bash
pip install streamlit pandas matplotlib seaborn jupyter
```

**Folder structure**
1. Create a base folder for this Streamlit project e.g. `~/documents/code/streamlit-project`. All the consequent paths will be relative to this folder.
2. Open a terminal window and change the current path to this new base folder created.
3. Create a folder named `data`. The dataset will be copied and cleaned up in this folder.
4. Create an empty file named `weather.py` in the base folder of your project.
5. Create an empty file named `data.ipynb` in the `/data` folder.

Your folder structure should look like this:

```
base-folder
├── data
└── weather.py
```

**'Hello World' streamlit application**
1. Open `weather.py` and add the following code:

```python
import streamlit as st

st.write('Hello worlds from Streamlit!')
```

2. Run streamlit:
   - Open a terminal window and make sure that your working directory is the base folder where `weather.py` is saved.
   - Run the following command:

```bash
streamlit run weather.py
```

If streamlit is properly installed, you should see a result like this:

- **Local URL**: `http://localhost:8501`
- **Network URL**: `http://192.168.4.89:8501`

![alt text](/images/5-solutions/5.1-python-e2e/image.png?width=90pc)


{{% notice note %}}
-You might see a different IP address or port. In some systems, streamlit opens automatically a browser tab and loads the application. If it is not the case for you, just open a browser tab with the URL.
-Keep the terminal session running. You do not need to re-run the terminal command each time the script is modified. To load the new script, just click on 'rerun' on the application page (you can find it by clicking on three dots in the upper-right corner of the page).
-To stop the streamlit application, hit `Ctrl+C` at the terminal window.
-If your application contains errors, you will see error messages both at the terminal window and as a pop-up in the application window.
{{% /notice %}}

#### Step 2 - Data prep
**Dataset download**
Download this dataset in CSV format from [here](/images/5-solutions/5.1-python-e2e/https://ws-assets-prod-iad-r-iad-ed304a55c2ca1aee.s3.us-east-1.amazonaws.com/e2226eb6-f109-47ae-b2c5-f02bf73b7d0e/weather_data_orig.csv) and save it in `/data` folder as `weather_data_orig.csv`.

```
base-folder
├── data
  └── weather_data_orig.csv
```

**Dataset cleanup**
For demonstrating how Amazon Q Developer can accompany you step by step throughout data cleanup, you will use a Jupyter notebook to perform this cleanup in an interactive manner.

Here are the steps that you will cover during the cleanup process:

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

Open `data/data.ipynb` (created in the previous step) in the IDE that supports Jupyter. Start following the below instructions step-by-step and use Amazon Q Developer either by providing the prompts mentioned or use its suggestion to auto-complete the line of code.

**Single Line Prompting**
```python
import pandas as pd
# import weather_data.csv as a dataframe
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df = pd.read_csv("weather_data.csv")
```
{{% /expand%}}

```python
# remove null value rows where TMAX or TMIN columns are null, inplace
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df.dropna(subset=['TMAX', 'TMIN'], inplace=True)
```
{{% /expand%}}


```python
# reduce the dataframe and only keep the following columns: STATION, NAME, DATE, TAVG, TMAX, TMIN
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df = df[['STATION','NAME','DATE','TAVG','TMAX','TMIN']]
```
{{% /expand%}}

```python
# create new columns named "Country" using column "NAME" in the dataframe
# the data for the column has two words separated by a "comma", so we use the split() method to split the string into two words
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df['COUNTRY'] = df['NAME'].str.split(',').str[1]
df['STATIONNAME'] = df['NAME'].str.split(', ').str[0]
```
{{% /expand%}}

```python
# for the dataframe convert TMIN, TMAX, and TAVG columns to float
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df['TMIN'] = df['TMIN'].astype(float)
df['TMAX'] = df['TMAX'].astype(float)
df['TAVG'] = df['TAVG'].astype(float)
```
{{% /expand%}}

```python
# for the dataframe TAVG, if TAVG is NaN then assign TAVG = (TMAX + TMIN)/2
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df.loc[df['TAVG'].isnull(), 'TAVG'] = (df['TMAX'] + df['TMIN']) / 2
```
{{% /expand%}}

```python
# for the dataframe convert DATE column to datetime
```

{{%expand "Amazon Q Developer suggestion" %}}
```python
df['DATE'] = pd.to_datetime(df['DATE'])
```
{{% /expand%}}

```python
# write df to a csv file using utf-8 encoding and double quotes the data

```
{{%expand "Amazon Q Developer suggestion" %}}
```python
df.to_csv('weather_data.csv', encoding='utf-8', doublequote=True,index=False)
```
{{% /expand%}}

#### Multi-line prompting
During the previous section, the approach was to provide zero shot one line prompts to generate the code step by step. This works very well if you are exploring and discovering data in an interactive manner and you are not sure about all the required steps. In case you know all the steps to cleanup data, another option is to provide a multi-line prompt with all the steps in one prompt. The output of this multi-line prompt might be different from the previous step-by-step method as Amazon Q Developer will try to provide a potentially more optimised code based on all the context. You can try this by combining all the prompts from the beginning in a single multi-line prompt here and compare it to the code generated before.

#### Prompt (Use Q-Developer Chat)

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

{{%expand "Amazon Q Developer suggestion" %}}
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

#### Step 3 - Streamlit Application

**Configuration file**
It is always a good practice to create a configuration file to avoid hardcoding input in your code. You will create a basic configuration file for this purpose to tell your application where to find the cleaned dataset.

Create a text file in the base folder of your project and name it `configuration.ini`. Copy the following lines to this file (replace the file name with the output file from the last step):

```ini
[input_data]
input_file = data/weather_data_processed.csv
```

You will use the `configparser` Python library to read and parse this file in the next step.

**Folder structure verification**
At this stage, your project folder should look like this:

```
base-folder
   ├── data
   │   └── data.ipynb        <---- Notebook for data cleanup
   │   ├──── 3413569.csv     <---- Original dataset
   │   └── weather_data.csv  <---- Cleaned dataset
   ├── configuration.ini    <---- Configuration file
   └── weather.py           <---- Main Streamlit application file
```

**Streamlit application initialization**
Open `weather.py` from the root folder of your project. This file will serve as the main placeholder for the application.
Delete its content ('Hello World').


{{% notice note %}}
-The objective is for you to see Amazon Q Developer in action. The required prompts provided below should be entered exactly in the sequence presented. Please follow the entirety of this step closely and do not skip any parts.
-The responses expected from prompts are provided after each prompt. It is recommended that you generate your own response using Amazon Q Developer and compare them with the provided answers.
-In some places, you need to add some lines of code in the sequence without using Amazon Q Developer prompts.
-By keeping hitting enter after the code generation, Amazon Q Developer might suggest you more lines of code that might be interesting and useful. Do not hesitate to explore the continuation codes.
{{% /notice %}}

{{% notice note %}}
Don't forget to click on rerun after each time you modify the script to see the results. You can find rerun on the top right corner of the application page (click on three dots).
{{% /notice %}}

{{% notice note %}}
Q Developer, like any Generative AI tool, is non-deterministic in nature. The code generated by Q Developer may not be the same as the code provided in the solution. Always check to see how many suggestions are provided by Q Developer and choose the one that best fits your requirements.
{{% /notice %}}

**Import required libraries**
```python
import streamlit as st
import configparser
import os, sys
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
```

Please note that if you do not import some of these libraries at the beginning, Amazon Q Developer will suggest the addition of the required libraries in-place if needed.

**Read configuration file and load dataset**

**Prompt**
```python
# The configuration file name is 'configuration.ini' in the same folder

# get the directory name and file name of the script
```

**Amazon Q Developer suggestion**
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

**Amazon Q Developer suggestion**
```python
config = configparser.ConfigParser()
full_file_name = os.path.join(dir_name, file_name)

config.read(full_file_name)
```

**Prompt**
```python
# get the "input_file" name, from the  "input_data" section from the configuration ini file
```

**Amazon Q Developer suggestion**
```python
input_file = config.get("input_data", "input_file")
```

You might need to adjust the name of the configuration section and the parameter name in the generated code.

**Prompt**
```python
# create function called load_data. passing into the function is the file_name

# return the dataframe and decorate it as st.cache_data
```

**Amazon Q Developer suggestion**
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

**Amazon Q Developer suggestion**
```python
df = load_data(input_file)
```

Caching is an interesting functionality in Streamlit. As Streamlit is a script that runs top to bottom each time an element changes (e.g., entering data in the widgets, or script modification), you need to be cautious not to repeat resource-intensive operations such as data-loading every time the script runs. For this purpose, you can decorate the functions that you would like to cache with `st.cache_data` and Streamlit takes care of it for you. Basically, each time Streamlit needs to call the decorated function, it verifies if the code and the inputs are the same. If that is the case, it will not run the function and preserve the values without any resource consumption.

There is a lot more to caching in Streamlit. You can refer to the documentation for more information and examples: [Caching](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/advanced-features/caching).

**Prompt**
```python
# in the dataframe, convert the "DATE" column to datetime
```

**Amazon Q Developer suggestion**
```python
df["DATE"] = pd.to_datetime(df["DATE"])
```

**Main page layout**
The application is composed of a simple layout, with a header and a tab view with two tabs: one to view the loaded dataset and the other to visualize weather data using inputs to select the weather station and date range.

**Prompt (In the Chat Window)**
```python
# use markdown to write a streamlit level 1 header

# the format of the header is

# mostly_sunny Weather Data Visualization snow_cloud
```

**Amazon Q Developer suggestion**
```python
st.header(":mostly_sunny: Weather Data Visualization :snow_cloud:")
st.markdown("---")
```

As you can see, Streamlit supports Markdown language as well as Emojis. Here, the `st.write` method is used but you can use Streamlit magic to write Markdown directly in your code without using any method. For more information: [Magic](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/api-reference/write-magic/magic).

If you update the Streamlit application, you should see the main page like this (Please note that if you are not using dark mode in your environment, the background color might be different).

![alt text](/images/5-solutions/5.1-python-e2e/image-1.png?width=40pc)

**Prompt**
```python
# add two tabs to the streamlit app

# first tab is called 'Data Set' and assign it to the variable tab_data_set

# second tab is called 'Single City Charts' and assign it to the variable tab_data_visualization
```

**Amazon Q Developer suggestion**
```python
tab_data_set, tab_data_visualization = st.tabs(["Data Set", "Single City Charts"])
```

Here you are creating the first visual user interface in Streamlit: A tab view. For more information, please refer to the documentation: [st.tabs](/images/5-solutions/5.1-python-e2e/https://docs.streamlit.io/library/api-reference/layout/st.tabs).

![alt text](/images/5-solutions/5.1-python-e2e/image-2.png?width=40pc)

**First tab: dataset view**
**Prompt**
```python
# write the dataframe to the first tab

# second tab will use the tab_data_visualization variable to write the dataframe
```

**Amazon Q Developer suggestion**
```python
with tab_data_set:
  st.write(df)
```

![alt text](/images/5-solutions/5.1-python-e2e/image-3.png?width=40pc)

That's it! Streamlit has powerful integration with Python and Pandas dataframes for visualization with little or no effort.

