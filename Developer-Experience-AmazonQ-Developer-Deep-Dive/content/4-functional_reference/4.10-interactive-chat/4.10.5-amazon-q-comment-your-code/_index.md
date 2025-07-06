---
title: "Amazon Q: Comment Your Code"
date: "`r Sys.Date()`"
weight: 5
chapter: false
pre: " <b> 4.10.5 </b> "
---

#### Amazon Q: Comment Your Code

Amazon Q Developer can automatically comment your code. Select code in your IDE, right-click, and choose to send to Q for commenting. Type your prompt if needed.

##### Example: Add Comments to Code
**Prompt:**
Add comments to the following code:
```python
sum = 0
line_items = [{'amount': 0} for i in range(100)]

for j in range(len(line_items)):
  sum += line_items[j]

tax = sum * tax_rate
total = sum + tax  

print(f"Sum: {sum}")
print(f"Tax: {tax}")
print(f"Total: {total}")
```

**Amazon Q Answer:**
```python
# Initialize the sum variable to 0 
sum = 0

# Create a list of 100 items with amount = 0
line_items = [{'amount': 0} for i in range(100)]

# Loop through each item in the line_items list
for j in range(len(line_items)):
  # Add the current item's amount to the running sum
  sum += line_items[j]

# Calculate tax by multiplying the sum by the tax rate
tax = sum * tax_rate  

# Calculate the total by adding the sum and tax
total = sum + tax

# Print the sum
print(f"Sum: {sum}")

# Print the calculated tax
print(f"Tax: {tax}") 

# Print the total
print(f"Total: {total}")
```

> **Note:** Amazon Q supports commenting for multiple programming languages.
