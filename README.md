# 🏠 Dự đoán giá bất động sản tại Hà Nội & TP.HCM

Dự án này tập trung vào việc **phân tích dữ liệu và xây dựng mô hình Machine Learning dự đoán giá bất động sản** dựa trên dữ liệu thực tế được thu thập từ các tin đăng bán nhà đất.

Toàn bộ quy trình được thực hiện theo pipeline hoàn chỉnh:

**Crawl dữ liệu → Làm sạch → EDA → Feature Engineering → Xây dựng mô hình → Giải thích mô hình → Dashboard**

---

## 📌 Mục tiêu dự án

- Thu thập dữ liệu bất động sản từ thị trường thực tế  
- Làm sạch và chuẩn hóa dữ liệu thô  
- Phân tích cấu trúc thị trường và phân phối giá  
- Xây dựng mô hình học máy dự đoán giá nhà  
- Giải thích mô hình bằng SHAP  
- Xây dựng dashboard trực quan phục vụ ứng dụng thực tế  

---

## 📊 Bộ dữ liệu

Dữ liệu được crawl tự động và bao gồm các thuộc tính:

- Giá  
- Diện tích  
- Quận / Huyện  
- Thành phố (Hà Nội / TP.HCM)  
- Loại bất động sản  
- Số phòng ngủ  
- Số tầng  
- Pháp lý  
- Nội thất  
- Mặt tiền  
- Tiện ích  

Tập dữ liệu có **hàng chục nghìn tin đăng** và tồn tại nhiều giá trị ngoại lai.

---

## ⚙️ Công nghệ sử dụng

### Thu thập dữ liệu
- Selenium  
- Undetected Chromedriver  
- BeautifulSoup  

### Xử lý dữ liệu
- Pandas  
- NumPy  

### Trực quan hóa
- Matplotlib  
- Seaborn  
- Plotly  

### Machine Learning
- Scikit-learn  
- Ridge Regression  
- Random Forest  
- XGBoost  

### Tối ưu tham số
- Optuna  

### Giải thích mô hình
- SHAP  

### Dashboard
- Plotly / Streamlit  

---

## 🔎 Phân tích khám phá dữ liệu (EDA)

Một số insight quan trọng:

- Phân phối giá gốc lệch phải mạnh → cần **log-transform giá**
- Diện tích trung vị khoảng **75 m²**
- Tương quan mức trung bình giữa diện tích và giá
- Bất động sản có pháp lý rõ ràng thường có giá cao hơn
- Nhà có mặt tiền thường đắt hơn đáng kể
- Các quận trung tâm có **đơn giá/m² cao nhất**

Các biểu đồ phân tích gồm:

- Phân phối giá  
- Giá theo loại bất động sản  
- Tương quan diện tích – giá  
- Giá theo quận  
- So sánh Hà Nội vs TP.HCM  
- Phân tích giá/m²  

---

## 🧠 Feature Engineering

Khoảng **25 đặc trưng mới** được xây dựng nhằm phản ánh logic thị trường:

- Biến nhị phân (has_frontage, verified_center)  
- Biến scoring (legal_score, furniture_score, amenity_score)  
- Biến tương tác (area × floors)  
- Encoding vị trí (target encoding / frequency encoding)  
- Phân khúc giá (price segment)  

Những đặc trưng này giúp mô hình học được mối quan hệ phi tuyến tốt hơn.

---

## 🤖 Xây dựng mô hình & đánh giá

Ba mô hình chính được huấn luyện:

- Ridge Regression (baseline)  
- Random Forest  
- XGBoost (mô hình tốt nhất)  

Tối ưu tham số được thực hiện bằng **Optuna**.

### 📈 Kết quả cuối cùng

- **R² = 0.84**  
- **MAPE = 32%**  
- **Accuracy phân khúc giá = 0.73**

XGBoost cho thấy khả năng học tương tác đặc trưng và quan hệ phi tuyến vượt trội.

---

## 🔬 Giải thích mô hình bằng SHAP

SHAP được sử dụng để:

- Xác định đặc trưng quan trọng toàn cục  
- Giải thích dự đoán từng bất động sản  
- Phân tích ảnh hưởng phi tuyến của các biến  

Các đặc trưng ảnh hưởng mạnh nhất:

- Giá/m²  
- Vị trí  
- Diện tích  
- Số tầng  
- Pháp lý  

Các biểu đồ SHAP:

- Summary plot  
- Feature importance  
- Dependence plot  
- Waterfall plot  

---

## 📊 Dashboard & ứng dụng thực tế

Dashboard giúp:

- Theo dõi xu hướng thị trường  
- So sánh giá giữa các khu vực  
- Phân tích tác động của đặc trưng  
- Dự đoán giá cho bất động sản mới  

Qua đó giúp **kết nối mô hình ML với nhu cầu thực tế**.

---

## ⚠️ Hạn chế

- Dữ liệu còn tồn tại outlier và tin đăng nhiễu  
- Một số khu vực có số lượng mẫu nhỏ  
- Chưa có yếu tố thời gian  
- Chưa tích hợp dữ liệu hạ tầng hoặc GIS  

---

## 🚀 Hướng phát triển

- Thêm dữ liệu theo thời gian để phân tích xu hướng giá  
- Kết hợp dữ liệu bản đồ và khoảng cách tiện ích  
- Triển khai API định giá bất động sản  
- Thử nghiệm Deep Learning  
- Mở rộng dashboard cho người dùng công khai  

---

## 📂 Cấu trúc dự án
