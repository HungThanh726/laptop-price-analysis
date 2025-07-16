# Phân tích giá laptop dựa trên thông số kỹ thuật
Mô tả
# Dự án phân tích giá laptop dựa trên tập dữ liệu laptop.csv từ Kaggle, sử dụng các thông số như RAM, SSD, CPU, và đồ họa. Mục tiêu là dự đoán giá bằng mô hình máy học và xác định các yếu tố chính ảnh hưởng đến giá.
Mục tiêu

Dự đoán giá laptop với độ chính xác cao.
Xác định các đặc trưng quan trọng (RAM, SSD, đồ họa).
Trực quan hóa xu hướng giá qua biểu đồ và dashboard.

Dữ liệu

Nguồn: Tập dữ liệu laptop trên Kaggle
Cột chính: Model, Price, Rating, Ram, SSD, Core, Graphics, OS, Warranty.

Công cụ

Python: Pandas, NumPy, Scikit-learn.
Trực quan hóa: Matplotlib, Seaborn.
Môi trường: Jupyter Notebook.

Tải tệp laptop.csv từ Kaggle và đặt vào thư mục data.

Quy trình

Làm sạch dữ liệu: Xử lý giá trị thiếu, chuẩn hóa cột Price, OS, Graphics.
Phân tích thăm dò (EDA): Vẽ biểu đồ phân tán (Price vs. RAM/SSD), heatmap tương quan.
Kỹ thuật đặc trưng: Tạo Performance_Score từ RAM, SSD, CPU; mã hóa biến phân loại.
Mô hình hóa: Sử dụng Random Forest Regressor (R² ~0.85).
Trực quan hóa: Biểu đồ giá theo thương hiệu, dashboard Tableau.

Kết quả

Thông tin chi tiết:
Laptop với RAM 16GB+, SSD 1TB, và card đồ họa rời có giá cao hơn 30-50%.
Apple MacBook có giá cao hơn 30% so với laptop Windows tương đương.


Hiệu suất mô hình: Dự đoán giá chính xác trong ±5,000 INR cho 80% trường hợp.


Mã nguồn mẫu
import pandas as pd
from sklearn.ensemble import RandomForestRegressor
from sklearn.model_selection import train_test_split
from sklearn.preprocessing import LabelEncoder

# Đọc và làm sạch dữ liệu
df = pd.read_csv('data/laptop.csv')
df['Price'] = df['Price'].str.replace('₹', '').str.replace(',', '').astype(float)
df = df.dropna(subset=['Price', 'Ram', 'SSD'])

# Tạo đặc trưng
df['Performance_Score'] = df['Ram'].str.extract('(\d+)').astype(float) + df['SSD'].str.extract('(\d+)').astype(float)
le = LabelEncoder()
df['Graphics_Encoded'] = le.fit_transform(df['Graphics'])

# Huấn luyện mô hình
X = df[['Performance_Score', 'Graphics_Encoded', 'Rating']]
y = df['Price']
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
model = RandomForestRegressor(n_estimators=100, random_state=42)
model.fit(X_train, y_train)

# Đánh giá
print("R² Score:", model.score(X_test, y_test))

Liên kết

GitHub: https://github.com/HungThanh726/laptop-price-analysis
Kaggle Dataset: Laptop Specifications Dataset


Tên: Nguyễn Hùng Thanh
Liên hệ: hungthsnhnguyen37@gmail.com
