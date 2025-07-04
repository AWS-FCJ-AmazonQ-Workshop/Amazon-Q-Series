---
title: "Fake data generation"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 6. </b> "
---

Fake Data - Stock Prices
Big challenge in development is to create fake data. You can use Amazon Q Developer to create fake data for you. We will prompt Amazon Q Developer to create fake data for us.

Example #1:
Fake data data
General Prompt:
 we are going to create a JSON object (variable) and have Amazon Q Developer create the code for us.


Python

JavaScript

TypeScript

C#

Java

Go

php
In your VSCode create a file fake_stock_data.py and type the following code:

Prompt:
1
2
3
4
5
6
7
8
"""
fake_stock_prices ={
    {

    }
}

"""


Amazon Q Developer Suggestion:
Fake Data
1
2
3
4
5
6
7
8
fake_stock_prices = {
    {
        'symbol': 'AAPL',
        'price': '100.00'
        },

    
}

As long as you hit enter, Amazon Q Developer will keep adding data.

Adding data to the fake data
As long as you keep hitting enter, Amazon Q Developer will keep adding / creating classes for you.

Example #2:
Fake Data Continued
General Prompt:
   ----> We are hitting enter. No need to type anything. Just hit enter.

Python

JavaScript

TypeScript

C#

Java

Go

php
We want more data, so make the following changes to the code:

Prompt:
1
2
3
4
5
6
7
8
9


fake_data = {
    {
    "ticker": "AAPL",
    "price": "100.00",
    "date": "2020-01-01"
    },
}


By adding a comma ,at the end of the first data set, and we continue to hit the enter, Amazon Q Developer will suggest the following code:

Amazon Q Developer Suggestion:
Folder Class
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
13
14
15
16
17
18
19
fake_data = {
    {
        "ticker": "AAPL",
        "price": "100.00",
        "date": "2020-01-01"
    },
    {
        "ticker": "AMZN",
        "price": "200.00",
        "date": "2020-01-01"
    },
    {
        "ticker": "MSFT",
        "price": "300.00",
        "date": "2020-01-01"
    }
}

   

As long as you keep hitting enter Amazon Q Developer will keep adding / creating classes for you.

Example #3:
Number of data sets
General Prompt:
create a list of fake stock symbols by
generating random 4 letter stock names

Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
We want to generate X number of data sets, so make the following changes to the code:

Prompt:
1
2
3
4
5

"""
create a list of fake stock symbols by
generating random 4 letter stock names
"""


Amazon Q Developer Suggestion:
Fake stock symbols
1
2
3
4
5
6
7
8
9
import random
import string


def  generate_stock_symbols(n):
    return [random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) + random.choice(string.ascii_uppercase) for i in range(n)]    


   

Now we want to generate the data sets for each stock symbol:

Prompt:
1
2
3
4
5
6
7
8
9

"""
use the list of stock symbols to generate fake data for the stocks
the data should have the following fields:
    - symbol
    - price
    - volume
    - date
"""


Amazon Q Developer Suggestion:
Fake stock symbols
Example #4:
more explicit
What if we want to generate a lot of fake data and randomized the data? We can do that by adding a few more lines of comments.

General Prompt:
Create a function to generate a fake stock prices
    - ticker
    - price
    - date
    - return it as a dictionary object
The function should have a default value of 100 data
the function should create a list of random stock tickers, date of sale and price of sale


Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
Prompt:
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
    
"""
Create a function to generate a fake stock prices
    - ticker
    - price
    - date
    - return it as a dictionary object
The function should have a default value of 100 data
the function should create a list of random stock tickers, date of sale and price of sale

"""


Amazon Q Developer Suggestion:
Explicit
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
13
14
15
16
17
18
19
20
21
import random
import datetime


def generate_fake_stock_prices(num_data=100):
    """
    Generate fake stock prices
    :param num_data:
    :return:
    """
    stock_tickers = ["AAPL", "MSFT", "AMZN", "GOOG"]
    stock_prices = []
    for i in range(num_data):
        ticker = random.choice(stock_tickers)
        price = round(random.uniform(10, 100), 2)
        date = datetime.datetime.now()
        stock_prices.append({"ticker": ticker, "price": price, "date": date})
    return stock_prices


   

As you can see, different prompts generate different results for the same intent.

Example #5:
Fake data - random
You can modify the data to be more random but making change to the suggestion.

General Prompt:
 we are going to create a JSON object (variable) and have Amazon Q Developer create the code for us.


Python

JavaScript

TypeScript

C#

Java

Go

php
In your VSCode create a file fake_user_data.py and type the following code:

Prompt:
1
2
3
4
5
6
7
8
9

"""
fake_user_data ={
    {

    }
}

"""


Amazon Q Developer Suggestion:
Fake Data
1
2
3
4
5
6
7
8
9
fake_user_data ={
    {
        "id": 1,
        "name": "John",
        "email": "XXXXXXXXXXXXXX"

    },
   
}

As long as you hit enter, Amazon Q Developer will keep adding data. After a few sets, change the ID and see what happens.

Faker Package Fake Users
Import packages
You can prompt Amazon Q Developer to import packages. Lets use Amazon Q Developer to create fake data using a package called Faker.

Example #1:
Faker Package - Fake Users
General Prompt:

use the SOMEPACKAGE  package to create a list of fake users
    - first_name
    - last_name
    - user_id
    - full_name
    - email
    - return it as a dictionary object

The function should have a default value of 100 data
the function should create a list of random first names, last names, user_ids, full names, emails



Python

JavaScript

TypeScript

C#

Java

Scala

Go

php
In your VSCode create a file fake_users_faker.py and type the following code:

Prompt:
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
13
"""
import the Faker package
use the Faker  package to create a list of fake users
    - first_name
    - last_name
    - user_id
    - full_name
    - email
    - return it as a dictionary object

The function should have a default value of 100 data
the function should create a list of random first names, last names, user_ids, full names, emails
"""


Amazon Q Developer Suggestion:
User Faker
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
13
from Faker import Faker
def generate_fake_users(num_data=100):
    fake = Faker()
    data = []
    for i in range(num_data):
        data.append({
            "first_name": fake.first_name(),
            "last_name": fake.last_name(),
            "user_id": fake.user_id(),
            "full_name": fake.name(),
            "email": fake.email()
        })
    return data