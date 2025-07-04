---
title: "Amazon Q: Conversational Coding Flow"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.10.3. </b> "
---


## Amazon Q: Conversational Coding Flow

Amazon Q Developer supports multi-step coding conversations. Start a chat in your IDE, send prompts, and Amazon Q will maintain context and provide relevant instructions.

### Example: Multi-step Coding
**Prompt:**
1. Tạo danh sách các chương trình TV bằng Python.
2. Tạo danh sách điểm đánh giá cho các chương trình này.
3. Gộp chúng thành một đối tượng JSON gồm 10 chương trình và điểm đánh giá theo thứ tự giảm dần.

**Amazon Q Answer:**
Amazon Q sẽ tạo mã nguồn từng bước, giữ ngữ cảnh và hướng dẫn bạn hoàn thành yêu cầu phức tạp.

> **Note:** Amazon Q maintains conversation flow, so you can build on previous prompts for complex tasks.
16
17
18
19
20
21

import json

# Create a list of TV shows
shows = ["Friends", "The Office", "Parks and Recreation", "Brooklyn Nine-Nine", "The Good Place"] 

# Create a list of ratings   
ratings = [9, 8.9, 8.7, 8.5, 8.3]

# Merge shows and ratings into a dictionary
tv_shows = [{
  "name": show,
  "rating": rating
} for show, rating in zip(shows, ratings)]

# Sort the dictionary in descending order by rating
tv_shows.sort(key=lambda d: d["rating"], reverse=True)

# Output the top 10 shows to a JSON file
with open('top_shows.json', 'w') as f:
  json.dump(tv_shows[:10], f, indent=4)

Along with the response, code explanation is additional provided for the end users.

This creates lists of shows and ratings, combines them into a dictionary, sorts by rating in descending order, and outputs the top 10 to a JSON file. Let me know if you have any other questions!

Python
Prompt
1
2
3
CREATE a list of TV shows in python.
CREATE a list of ratings for these TV shows.
MERGE them to make a json object of 10 shows and their ratings in DESCENDING order.


Amazon Q Answer #1
Python Code
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

import json

# Create a list of TV shows
shows = ["Friends", "The Office", "Parks and Recreation", "Brooklyn Nine-Nine", "The Good Place"] 

# Create a list of ratings   
ratings = [9, 8.9, 8.7, 8.5, 8.3]

# Merge shows and ratings into a dictionary
tv_shows = [{
  "name": show,
  "rating": rating
} for show, rating in zip(shows, ratings)]

# Sort the dictionary in descending order by rating
tv_shows.sort(key=lambda d: d["rating"], reverse=True)

# Output the top 10 shows to a JSON file
with open('top_shows.json', 'w') as f:
  json.dump(tv_shows[:10], f, indent=4)


Test Case
1
Test the above use case.

Based on the follow-up, the following response has been generated from Amazon Q

Amazon Q Developer   Testcase

Conversation engagement
Amazon Q Conversation continuation
The users can continue the conversation as follows:

1
Which programming languages do you support today?

Amazon Q Response
I'm able to provide assistance with many common programming languages like Python, JavaScript, Java, C++ and C#. My goal is to help software developers be more productive by answering their coding questions accurately. While I have some language capabilities, developers will still need to test any code solutions themselves to ensure it meets their specific needs and works as intended. Please feel free to ask me about any programming tasks - I'll do my best to offer helpful guidance or point you towards relevant learning resources.
1
Convert the above python code to C++ then

Amazon Q Response
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
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
Here is one way to convert the Python code sample to C++: [1]

#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <fstream>
#include <nlohmann/json.hpp>

using json = nlohmann::json;

struct TVShow { std::string name; float rating;};

std::vector<TVShow> generateShowsList() {

std::vector<TVShow> shows;

shows.push_back({"Friends", 9.0}); shows.push_back({"The Office", 8.9}); shows.push_back({"Parks and Recreation", 8.7}); shows.push_back({"Brooklyn Nine-Nine", 8.5}); shows.push_back({"The Good Place", 8.3});

return shows;

}

int main() {

auto shows = generateShowsList();

std::sort(shows.begin(), shows.end(), [](TVShow a, TVShow b) {return a.rating > b.rating;});

json output; output = shows;

std::ofstream file("shows.json"); file << std::setw(4) << output << std::endl;

return 0;

}

This converts the key aspects like defining a struct, populating a list, sorting by rating, and outputting to JSON in C++. Let me know if any part needs more explanation.

Note
Amazon Q also provides Suggested follow up questions after the response has been provided. Users are encouraged to experiment with Amazon Q for code conversation, troubleshooting the code and asking follow-up questions to get the desirable outcome and enhanced understanding of Amazon Q.