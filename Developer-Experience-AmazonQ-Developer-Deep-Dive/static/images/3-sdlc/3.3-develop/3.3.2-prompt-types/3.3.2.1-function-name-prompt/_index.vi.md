---
title: "Function Name Prompt"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 3.3.2.1 </b> "
---

Function Name Prompt
Amazon Q Developer có thể hiểu ý định của bạn và đưa ra gợi ý dựa trên tên hàm. Tên hàm càng mô tả rõ ràng, gợi ý càng chính xác và hữu ích.

#### Tại sao nên dùng Function Name Prompt?
Một tên hàm được chọn tốt sẽ là prompt mạnh mẽ cho Amazon Q Developer. Chỉ cần gõ một tên hàm rõ ràng, bạn có thể:
- Tự động sinh ra logic mã phù hợp
- Giảm nhu cầu phải viết comment dài dòng hoặc bổ sung ngữ cảnh
- Tăng tốc quá trình prototyping và triển khai

**Khuyến nghị:** Hãy đặt tên hàm thể hiện rõ mục đích và hành vi mong đợi. Tránh các tên chung chung, không rõ nghĩa.

---

##### Ví dụ #1: Tháp Hà Nội
**Prompt:**
Ở đây, chỉ cần tên hàm là đủ:

```python
def towers_of_hanoi(
```

Khi bạn bắt đầu gõ `def towers_of_hanoi(` trong file VSCode (ví dụ: `basic.py`), Amazon Q Developer sẽ gợi ý một cài đặt hoàn chỉnh:

```python
def towers_of_hanoi(n, source, destination, auxiliary):
    if n == 1:
        print(source, destination)
        return
    towers_of_hanoi(n - 1, source, auxiliary, destination)
    print(source, destination)
    towers_of_hanoi(n - 1, auxiliary, destination, source)
```

---

##### Ví dụ #2: Tính trung bình
**Prompt:**
Một lần nữa, chỉ cần tên hàm:

```python
def get_average(numbers):
```

Amazon Q Developer sẽ gợi ý:

```python
def get_average(numbers):
    mean = sum(numbers) / len(numbers)
    return mean
```

---

#### Nhiều gợi ý
Đôi khi Amazon Q Developer sẽ đưa ra nhiều gợi ý mã. Bạn có thể dùng phím mũi tên để duyệt và nhấn Tab để chọn gợi ý phù hợp nhất.

![alt text](image.png?width=40pc)

---

##### Ví dụ #3: Độ lệch chuẩn
**Prompt:**

```python
def standard_deviation(numbers):
```

Amazon Q Developer có thể gợi ý:

```python
def standard_deviation(numbers):
    mean = sum(numbers) / len(numbers)
    return (sum((x - mean) ** 2 for x in numbers) / len(numbers)) ** 0.5
```

Hoặc một cách tiếp cận module hóa hơn:

```python
import math
def standard_deviation(numbers):
    return math.sqrt(variance(numbers))

def variance(numbers):
    mean = sum(numbers) / len(numbers)
    return sum([(x - mean) ** 2 for x in numbers]) / len(numbers)
```

---

#### Tổng kết
- Tên hàm mô tả rõ ràng thường đủ để Amazon Q Developer sinh ra mã chất lượng cao.
- Với logic phức tạp, hãy bắt đầu bằng tên hàm rõ ràng rồi bổ sung comment/ngữ cảnh nếu cần.
- Hãy thử nghiệm với cách đặt tên và xem nhiều gợi ý để chọn giải pháp phù hợp nhất cho bài toán của bạn.
