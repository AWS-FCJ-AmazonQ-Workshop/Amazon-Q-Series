---
title: "Language Conversion"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 4.10.6 </b> "
---

#### Amazon Q: Language Conversion

Amazon Q Developer can help you convert code between programming languages. Provide your source code and specify the target language.

##### Example 1: Convert from COBOL to Python
**Prompt:**
Convert the following COBOL code to Python:

```cobol
identification division.
program-id. json-sum-tax.

data division.
working-storage section.
   01 totals.
      05 total-amount                  pic 9(7)v99.
      05 total-tax-amount              pic 9(7)v99.

   01 line-item occurs 100 times. 
      05 amount                        pic 9(5)v99.

procedure division.
   perform initialize-totals
   perform calculate-totals
   perform calculate-tax
   display-results.

   initialize-totals.
   stop run.
```

**Amazon Q Answer:**
```python
# Define variables to store totals
total_amount = 0
total_tax_amount = 0

# Define a list of line items
line_items = [{'amount': 0} for i in range(100)]

# Initialize totals
def initialize_totals():
  global total_amount
  total_tax_amount = 0

# Calculate totals
def calculate_totals():
  global total_amount

# Calculate tax amount
def calculate_tax():
  global total_amount
  total_tax_amount = total_amount * 0.07

# Display results
def display_results():
  print(f"Total amount: {total_amount}")
  print(f"Tax amount: {total_tax_amount}")

# Run functions
initialize_totals()
calculate_totals()
calculate_tax()
display_results()
```

##### Example 2: Convert from Microsoft SQL Server to PostgreSQL
**Prompt:**
Convert the following T-SQL code to PostgreSQL:

```sql
USE [DNNDB]
GO
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[AddModuleControl]
   
   @CreatedByUserID            int

AS
   INSERT INTO dbo.ModuleControls (
   SELECT SCOPE_IDENTITY()
GO
```

**Amazon Q Answer:**
```sql
CREATE OR REPLACE FUNCTION public.add_module_control(
    p_module_def_id INTEGER,
    p_created_by_user_id INTEGER
)
RETURNS INTEGER AS $$
DECLARE
    v_inserted_id INTEGER;
BEGIN
    INSERT INTO public.module_controls (
    RETURN v_inserted_id;
END;
$$ LANGUAGE plpgsql;
```

> **Note:** Amazon Q supports many languages for code conversion.