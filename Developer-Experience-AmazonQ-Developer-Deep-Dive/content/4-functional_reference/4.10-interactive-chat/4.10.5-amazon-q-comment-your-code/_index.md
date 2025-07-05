---
title: "Amazon Q: Comment Your Code"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.10.5. </b> "
---


#### Amazon Q: Comment Your Code

Amazon Q Developer can automatically comment your code. Select code in your IDE, right-click, and choose to send to Q for commenting. Type your prompt if needed.

#### Example: Add Comments to Code
**Prompt:**
Comment the following code:
```python
sum = 0
line_items = [{'amount': 0} for i in range(100)]
```

**Amazon Q Answer:**
Amazon Q sẽ tự động thêm chú thích cho đoạn mã theo yêu cầu.

> **Note:** Amazon Q supports commenting for multiple languages.

for j in range(len(line_items)):
  sum += line_items[i]

tax = sum * tax_rate
total = sum + tax  

print(f"Sum: {sum}")
print(f"Tax: {tax}")
print(f"Total: {total}")


Amazon Q Answer #1
Comment the code
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
# Initialize sum variable to 0 
sum = 0

# Loop through each item in the line_items list
for j in range(len(line_items)):

  # Add the current item to the running sum
  sum += line_items[j]

  # Calculate tax by multiplying sum by tax rate
  tax = sum * tax_rate  

  # Calculate total by adding sum and tax 
  total = sum + tax

# Print the running sum  
print(f"Sum: {sum}")

# Print the calculated tax
print(f"Tax: {tax}") 

# Print the total
print(f"Total: {total}")
