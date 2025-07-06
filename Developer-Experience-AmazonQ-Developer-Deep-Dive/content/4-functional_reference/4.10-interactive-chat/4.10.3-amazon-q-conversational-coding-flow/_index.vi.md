---
title: "Amazon Q: Quy trình lập trình hội thoại"
date: "`r Sys.Date()`"
weight: 3
chapter: false
pre: " <b> 4.10.3 </b> "
---

#### Amazon Q: Quy trình lập trình hội thoại

Amazon Q Developer hỗ trợ hội thoại nhiều bước khi lập trình. Bắt đầu chat trong IDE, gửi các prompt, Amazon Q sẽ giữ ngữ cảnh và cung cấp hướng dẫn phù hợp.

##### Ví dụ: Lập trình nhiều bước
**Prompt:**
1. Tạo danh sách các chương trình TV bằng Python.
2. Tạo danh sách điểm đánh giá cho các chương trình này.
3. Gộp chúng thành một đối tượng JSON gồm 10 chương trình và điểm đánh giá theo thứ tự giảm dần.

**Amazon Q Trả lời:**
```python
import json

# Tạo danh sách các chương trình TV
shows = ["Friends", "The Office", "Parks and Recreation", "Brooklyn Nine-Nine", "The Good Place"] 

# Tạo danh sách điểm đánh giá   
ratings = [9, 8.9, 8.7, 8.5, 8.3]

# Gộp chương trình và điểm đánh giá thành từ điển
tv_shows = [{
  "name": show,
  "rating": rating
} for show, rating in zip(shows, ratings)]

# Sắp xếp từ điển theo điểm đánh giá giảm dần
tv_shows.sort(key=lambda d: d["rating"], reverse=True)

# Xuất 10 chương trình hàng đầu ra file JSON
with open('top_shows.json', 'w') as f:
  json.dump(tv_shows[:10], f, indent=4)
```

#### Tiếp tục cuộc hội thoại

**Prompt:**
Bạn hỗ trợ những ngôn ngữ lập trình nào?

**Amazon Q Trả lời:**
Tôi có thể hỗ trợ nhiều ngôn ngữ lập trình phổ biến như Python, JavaScript, Java, C++ và C#. Mục tiêu của tôi là giúp các nhà phát triển phần mềm làm việc hiệu quả hơn bằng cách trả lời chính xác các câu hỏi về lập trình. Mặc dù tôi có khả năng hỗ trợ nhiều ngôn ngữ, nhà phát triển vẫn cần tự kiểm tra các giải pháp mã để đảm bảo đáp ứng nhu cầu cụ thể và hoạt động như dự định.

**Prompt:**
Chuyển đổi mã Python trên sang C++

**Amazon Q Trả lời:**
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

> **Lưu ý:** Amazon Q duy trì luồng hội thoại, cho phép bạn xây dựng các tác vụ phức tạp dựa trên các prompt trước đó.