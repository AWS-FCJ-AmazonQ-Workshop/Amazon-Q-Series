---
title: "Amazon Q: Conversational Coding Flow"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.10.3. </b> "
---

#### Amazon Q: Conversational Coding Flow

Amazon Q Developer supports multi-step coding conversations. Start a chat in your IDE, send prompts, and Amazon Q will maintain context and provide relevant instructions.

##### Example: Multi-step Coding
**Prompt:**
1. Create a list of TV shows in Python.
2. Create a list of ratings for these TV shows.
3. Merge them into a JSON object of 10 shows and their ratings in descending order.

**Amazon Q Answer:**
```python
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
```

#### Continue the Conversation

**Prompt:**
Which programming languages do you support today?

**Amazon Q Answer:**
I can assist with many common programming languages like Python, JavaScript, Java, C++, and C#. My goal is to help software developers be more productive by answering their coding questions accurately. While I have some language capabilities, developers will still need to test any code solutions themselves to ensure it meets their specific needs and works as intended.

**Prompt:**
Convert the above Python code to C++.

**Amazon Q Answer:**
```cpp
#include <iostream>
#include <vector>
#include <string>
#include <algorithm>
#include <fstream>
#include <nlohmann/json.hpp>

using json = nlohmann::json;

struct TVShow { std::string name; float rating; };

std::vector<TVShow> generateShowsList() {
    std::vector<TVShow> shows;
    
    shows.push_back({"Friends", 9.0});
    shows.push_back({"The Office", 8.9});
    shows.push_back({"Parks and Recreation", 8.7});
    shows.push_back({"Brooklyn Nine-Nine", 8.5});
    shows.push_back({"The Good Place", 8.3});
    
    return shows;
}

int main() {
    auto shows = generateShowsList();
    
    std::sort(shows.begin(), shows.end(), [](TVShow a, TVShow b) {
        return a.rating > b.rating;
    });
    
    json output;
    output = shows;
    
    std::ofstream file("shows.json");
    file << std::setw(4) << output << std::endl;
    
    return 0;
}
```

> **Note:** Amazon Q maintains conversation flow, allowing you to build complex tasks based on previous prompts.