---
title: "Chuyển đổi ngôn ngữ lập trình"
date: "`r Sys.Date()`"
weight: 6
chapter: false
pre: " <b> 4.10.6 </b> "
---

#### Amazon Q: Chuyển đổi ngôn ngữ lập trình

Amazon Q Developer giúp bạn chuyển đổi mã nguồn giữa các ngôn ngữ lập trình. Cung cấp mã nguồn và chỉ định ngôn ngữ đích.

#### Ví dụ 1: Chuyển từ COBOL sang Python
**Prompt:**
Chuyển đoạn mã COBOL sau sang Python:

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
```

**Amazon Q Trả lời:**
```python
# Định nghĩa biến để lưu tổng

total_amount = 0
total_tax_amount = 0

# Định nghĩa danh sách các mục  

line_items = [{'amount': 0} for i in range(100)]

# Khởi tạo tổng

def initialize_totals():
  global total_amount
  global total_tax_amount
  total_amount = 0
  total_tax_amount = 0

# Tính tổng

def calculate_totals():
  global total_amount
  for item in line_items:
    total_amount += item['amount']

# Tính thuế

def calculate_tax():
  global total_amount
  global total_tax_amount
  total_tax_amount = total_amount * 0.07

# Hiển thị kết quả  

def display_results():
  print(f"Total amount: {total_amount}")
  print(f"Tax amount: {total_tax_amount}")

# Chạy các hàm

initialize_totals()
calculate_totals()
calculate_tax()
display_results()
```

#### Ví dụ 2: Chuyển từ Microsoft SQL Server sang PostgreSQL
**Prompt:**
Chuyển đoạn mã T-SQL sau sang PostgreSQL:

```sql
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
   @SupportsPopUps             bit,
   @CreatedByUserID            int

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
```

**Amazon Q Trả lời:**
```sql
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
```

> **Lưu ý:** Amazon Q hỗ trợ nhiều ngôn ngữ cho chuyển đổi mã nguồn.