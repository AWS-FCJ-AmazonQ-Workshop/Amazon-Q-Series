---
title: "Language Conversion"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 4.10.6. </b> "
---


## Amazon Q: Language Conversion

Amazon Q Developer can help you convert code between programming languages. Provide your source code and specify the target language.

### Example: Convert from COBOL
**Prompt:**
Convert the following COBOL code to Python.

**Amazon Q Answer:**
Amazon Q will generate the equivalent Python code and explain the conversion if needed.

> **Note:** Amazon Q supports many languages for code conversion.
28
29
30
31
32
33
34
35
36
37
38
identification division.
program-id. json-sum-tax.

data division.
working-storage section.
   01 totals.
      05 total-amount                  pic 9(7)v99.
      05 total-tax-amount              pic 9(7)v99.

   01 line-item occurs 100 times. 
      05 amount                        pic 9(5)v99.
      05 filler                        redefines amount.
         10 dollars                    pic 9(3).
         10 cents                      pic 99.

procedure division.
   perform initialize-totals
   perform calculate-totals
   perform calculate-tax
   display-results.

   initialize-totals.
      move 0 to total-amount
      move 0 to total-tax-amount.

   calculate-totals.
      perform varying i from 1 by 1 until i > 100
         add amount(i) to total-amount
      end-perform.

   calculate-tax.
      compute total-tax-amount = total-amount * 0.07.

   display-results.
      display "Total amount: " total-amount
      display "Tax amount: " total-tax-amount.

   stop run.


In your IDE, click the icon for the Amazon Q Developer extension to open the Amazon Q Developer panel. Select the COBOL code, Right mouse click on the screen then choose Amazon Q Developer > Send to Prompt. On the Q chat panel, type your prompt and press Enter. The Amazon Q Developer panel will display the suggested questions and answers.

General Prompt
1
 Convert the following COBOL code to <Language>.


Python

JavaScript

Java

C#
Prompt
1
Convert the following COBOL code to Python.


Amazon Q Answer #1
Convert to Python
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
37
38
39
40
41
42
43
44
45

# Define variables to store totals

total_amount = 0
total_tax_amount = 0

# Define line item list  

line_items = [{'amount': 0} for i in range(100)]

# Initialize totals

def initialize_totals():
  global total_amount
  global total_tax_amount
  total_amount = 0
  total_tax_amount = 0

# Calculate totals

def calculate_totals():
  global total_amount
  for item in line_items:
    total_amount += item['amount']

# Calculate tax amount

def calculate_tax():
  global total_amount
  global total_tax_amount
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



Example 2
Microsoft SQL Server to PostGreSQL
In this example, suppose you have an existing Microsoft SQL Server Database. You are doing move-to open-source modernization and hence have a need to convert all SQL statements to its PostgreSQL equivalent.

For this exercise: Create a new file and call it samplestoredprocedure.sql in VSCode, then paste in the following code block. Suppose this is your existing MS SQL Server stored procedure declaration which is written in T-SQL.

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
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
USE [DNNDB]
GO
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO
CREATE PROCEDURE [dbo].[AddModuleControl]
   
   @ModuleDefID                int,
   @ControlKey                 nvarchar(50),
   @ControlTitle               nvarchar(50),
   @ControlSrc                 nvarchar(256),
   @IconFile                   nvarchar(100),
   @ControlType                int,
   @ViewOrder                  int,
   @HelpUrl                    nvarchar(200),
   @SupportsPartialRendering   bit,
   @SupportsPopUps				bit,
   @CreatedByUserID			int

AS
   INSERT INTO dbo.ModuleControls (
      ModuleDefID,
      ControlKey,
      ControlTitle,
      ControlSrc,
      IconFile,
      ControlType,
      ViewOrder,
      HelpUrl,
      SupportsPartialRendering,
      SupportsPopUps,
      CreatedByUserID,
      CreatedOnDate,
      LastModifiedByUserID,
      LastModifiedOnDate
   )
   VALUES (
      @ModuleDefID,
      @ControlKey,
      @ControlTitle,
      @ControlSrc,
      @IconFile,
      @ControlType,
      @ViewOrder,
      @HelpUrl,
      @SupportsPartialRendering,
      @SupportsPopUps,
      @CreatedByUserID,
      getdate(),
      @CreatedByUserID,
      getdate()
   )

   SELECT SCOPE_IDENTITY()
GO

In your IDE, click the icon for the Amazon Q Developer extension to open the Amazon Q Developer panel. Select the T-SQL code, Right mouse click on the screen then choose Amazon Q Developer > Send to Prompt. On the Q chat panel, type your prompt and press Enter. The Amazon Q Developer panel will display the suggested questions and answers.

General Prompt
1
 Convert this T-SQL to PostGreSQL equivalent implementation

Amazon Q Developer Answer
Convert to PostGreSQL
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
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54
CREATE OR REPLACE FUNCTION public.add_module_control(
    p_module_def_id INTEGER,
    p_control_key VARCHAR(50),
    p_control_title VARCHAR(50),
    p_control_src VARCHAR(256),
    p_icon_file VARCHAR(100),
    p_control_type INTEGER,
    p_view_order INTEGER,
    p_help_url VARCHAR(200),
    p_supports_partial_rendering BOOLEAN,
    p_supports_pop_ups BOOLEAN,
    p_created_by_user_id INTEGER
)
RETURNS INTEGER AS $$
DECLARE
    v_inserted_id INTEGER;
BEGIN
    INSERT INTO public.module_controls (
        module_def_id,
        control_key,
        control_title,
        control_src,
        icon_file,
        control_type,
        view_order,
        help_url,
        supports_partial_rendering,
        supports_pop_ups,
        created_by_user_id,
        created_on_date,
        last_modified_by_user_id,
        last_modified_on_date
    )
    VALUES (
        p_module_def_id,
        p_control_key,
        p_control_title,
        p_control_src,
        p_icon_file,
        p_control_type,
        p_view_order,
        p_help_url,
        p_supports_partial_rendering,
        p_supports_pop_ups,
        p_created_by_user_id,
        CURRENT_TIMESTAMP,
        p_created_by_user_id,
        CURRENT_TIMESTAMP
    )
    RETURNING id INTO v_inserted_id;

    RETURN v_inserted_id;
END;
$$ LANGUAGE plpgsql;

Here are the key changes and explanations:

The CREATE PROCEDURE syntax is replaced with CREATE OR REPLACE FUNCTION. PostgreSQL uses functions for what would be stored procedures in T-SQL.
The schema name dbo is replaced with public, which is the default schema in PostgreSQL. You can change this if you're using a different schema.
Parameters are defined with names starting with p_ to distinguish them from column names. They're also defined with PostgreSQL data types:
nvarchar is replaced with VARCHAR
bit is replaced with BOOLEAN
The function is defined to return an INTEGER, which will be the ID of the inserted row.
The AS keyword is followed by $$, which is the start of the function body in PostgreSQL.
We declare a variable v_inserted_id to store the ID of the inserted row.
The INSERT statement is mostly the same, but we use the parameter names instead of the T-SQL style @ variables.
getdate() is replaced with CURRENT_TIMESTAMP.
Instead of SELECT SCOPE_IDENTITY(), we use the RETURNING clause in the INSERT statement to get the inserted ID.
The function ends with END; and the closing $$.
We specify the language as plpgsql, which is PostgreSQL's procedural language
To use this function, you would call it like this:

1
2
3
4
SELECT public.add_module_control(
    1, 'ControlKey', 'ControlTitle', 'ControlSrc', 'IconFile', 
    1, 1, 'HelpUrl', true, false, 1
);

This will insert the new row and return the ID of the inserted row. Remember to adjust the schema name, table name, and column names if they differ in your PostgreSQL database structure.