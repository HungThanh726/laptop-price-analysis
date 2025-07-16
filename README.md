# Phân tích giá laptop dựa trên thông số kỹ thuật
Mô tả
# Dự án phân tích giá laptop dựa trên tập dữ liệu laptop.csv từ Kaggle, sử dụng các thông số như RAM, SSD, và Rating. Mục tiêu là dự đoán giá bằng mô hình máy học và phân tích xu hướng giá.
Mục tiêu

Dự đoán giá laptop dựa trên RAM, SSD, và Rating.
Trực quan hóa mối quan hệ giữa giá và thông số.

Dữ liệu

Nguồn: Tập dữ liệu laptop trên Kaggle
Cột chính: Model, Price, Rating, Ram, SSD.

Công cụ

Python: Pandas, Scikit-learn.
Trực quan hóa: Matplotlib, Seaborn.
Môi trường: Jupyter Notebook.

Quy trình

Làm sạch dữ liệu: Chuyển đổi Price, xử lý giá trị thiếu.
Phân tích thăm dò (EDA): Vẽ biểu đồ phân phối giá, giá vs RAM/SSD, giá theo thương hiệu.
Mô hình hóa: Sử dụng Random Forest Regressor với RAM, SSD (mã hóa) và Rating (R² ~0.80-0.85).
Trực quan hóa: Biểu đồ boxplot, cột, và tầm quan trọng đặc trưng.

Kết quả

Thông tin chi tiết:  
RAM và SSD ảnh hưởng mạnh đến giá.  
Laptop với RAM/SSD cao có giá cao hơn 30-50%.


Hiệu suất mô hình: R² ~0.80-0.85, dự đoán giá chính xác trong ±5,000 INR cho phần lớn trường hợp.

Hình ảnh
![Tầm quan trọng đặc trưng](visualizations/plots/feature_importance.png)
Phân phối giá:
Giá theo RAM:
Tầm quan trọng đặc trưng:

Liên kết

GitHub: https://github.com/HungThanh726/laptop-price-analysis
Kaggle Dataset: Laptop Specifications Dataset

Tên: Nguyễn Hùng Thanh
Liên hệ: hungthsnhnguyen37@gmail.com
