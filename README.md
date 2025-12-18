# LTXLDL_Project1.5

Members:
- Trần Khánh Đạt - MSV: 24022287
- Nguyễn Minh Hoàng - MSV: 24022339
- Nguyễn Đắc Trung Hiếu - MSV: 24022329

---

## ⚙️ Thiết lập Môi trường & Reproducibility

Để đảm bảo kết quả chạy lại (Replication) giống hệt báo cáo, đặc biệt là các thuật toán ngẫu nhiên như K-Means, nhóm tuân thủ cấu hình sau:

* **Python Version:** 3.9+
* **Random Seed (Global):** `42`
    * *Lưu ý:* Biến `random_state=42` hoặc `np.random.seed(42)` đã được thiết lập trong các cell chạy mô hình Machine Learning.

---

## Hướng dẫn cài đặt (Installation)

Vui lòng thực hiện tuần tự các bước sau:

**Bước 1: Clone dự án hoặc tải mã nguồn**
git clone [https://github.com/hisudewaltz/2526-LTXLDL-Project-1.5]
cd NYC-Taxi-Analysis

**Bước 2: Cài đặt đầy đủ các thư viện trong file requirements.txt**

pip install -r requirements.txt

Hướng dẫn chạy lại mã nguồn (Execution Steps)
Dữ liệu đầu vào (file .parquet) cần được đặt trong thư mục data/raw/. Vui lòng chạy các Notebook theo thứ tự sau để đảm bảo luồng dữ liệu chính xác:

src/01_CleanData.ipynb

Chức năng: Đọc dữ liệu thô, xử lý giá trị thiếu, loại bỏ dữ liệu lỗi (âm, ngoại lai), merge với taxi_zone_lookup.

Output: Tạo ra file sạch processed/clean_data_monthly/clean_trips_2023.parquet.

src/02_Calculate_KPI.ipynb

Chức năng: Tính toán các chỉ số kinh doanh: Tổng doanh thu, Số chuyến, Index 100, Rolling Average.

Output: Xuất các file CSV tổng hợp KPI vào processed/.

src/03_Visualizatino.ipynb

Chức năng: Vẽ các biểu đồ trực quan hóa (Ngày, Tháng, Giờ, Top Zone).

Output: Lưu hình ảnh .png vào thư mục figures/.

src/04_Kmeans_clustering & ARIMA.ipynb

Chức năng:

Phân cụm K-Means (với random_state=42).

Dự báo nhu cầu (Forecasting).