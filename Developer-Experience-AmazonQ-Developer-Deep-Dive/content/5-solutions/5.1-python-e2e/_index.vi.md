---
title: "Giải pháp Python End-to-End với Amazon Q Developer"
date: "`r Sys.Date()`"
weight: 1
chapter: false
pre: " <b> 1. </b> "
---

#### Bước 1: Cài đặt môi trường

- Sử dụng IDE Python (ví dụ: VS Code) có bật Amazon Q Developer.
- Cài Python 3.9+ và các thư viện:
  - `streamlit`, `pandas`, `matplotlib`, `seaborn`, `jupyter`
- Cài đặt bằng lệnh:

```sh
pip install streamlit pandas matplotlib seaborn jupyter
```

- Cấu trúc thư mục dự án:
  - `base-folder/`
    - `data/`
      - `data.ipynb` (notebook làm sạch dữ liệu)
      - `weather_data_orig.csv` (dữ liệu gốc)
      - `weather_data.csv` (dữ liệu đã làm sạch)
    - `configuration.ini` (file cấu hình)
    - `weather.py` (ứng dụng Streamlit chính)

#### Bước 2: Chuẩn bị dữ liệu

- Sử dụng bộ dữ liệu thời tiết (CSV) với các cột: NAME, DATE, TAVG, TMAX, TMIN.
- Làm sạch và biến đổi dữ liệu trong `data/data.ipynb` với các prompt Amazon Q Developer:
  - Nhập CSV thành DataFrame
  - Xóa dòng có TMAX/TMIN null
  - Giữ các cột: STATION, NAME, DATE, TAVG, TMAX, TMIN
  - Tạo cột mới (Country, StationName) bằng cách tách NAME
  - Chuyển TMIN, TMAX, TAVG sang float
  - Điền TAVG nếu NaN: `TAVG = (TMAX + TMIN)/2`
  - Chuyển DATE sang datetime
  - Ghi DataFrame đã xử lý ra CSV
- Thử cả prompt từng dòng và prompt nhiều dòng để sinh code.

#### Bước 3: Ứng dụng Streamlit

- Tạo `configuration.ini` để chỉ đường dẫn dữ liệu đã làm sạch.
- Trong `weather.py`, import các thư viện cần thiết:
  - `streamlit`, `configparser`, `os`, `sys`, `pandas`, `matplotlib.pyplot`, `seaborn`
- Đọc config và tải dữ liệu với cache (`st.cache_data`).
- Chuyển cột DATE sang datetime.
- Bố cục:
  - Dùng Markdown cho tiêu đề
  - Thêm hai tab: 'Data Set' và 'Single City Charts'
  - Tab đầu: hiển thị DataFrame
  - Tab hai: chọn country, station, date range; hiển thị biểu đồ đường và heatmap
- Sử dụng prompt Amazon Q Developer cho từng bước và thử nghiệm các gợi ý.
- Lưu ý Best practices:
  - Dùng file cấu hình cho đường dẫn
  - Dùng cache khi tải dữ liệu
  - Tách code thành các hàm riêng

> **Lưu ý:** Amazon Q Developer sinh mã không cố định; hãy kiểm tra và điều chỉnh mã phù hợp nhu cầu của bạn.