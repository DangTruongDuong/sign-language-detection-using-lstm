<div align="center">

# 🎓 ỨNG DỤNG NHẬN DIỆN CỬ CHỈ TAY HỖ TRỢ GIAO <br> TIẾP CHO NGƯỜI KHUYẾT TẬT

</div>


<div align="center">

<p align="center">
  <img src="images/logo.png" alt="Logo Đại học Đại Nam" width="200"/>
  <img src="images/AIoTLab_logo.png" alt="Logo AIoTLab" width="170"/>
</p>

</div>

<h3 align="center">🔬 Tăng Cường Giao Tiếp Bằng Công Nghệ Nhận Diện Ký Hiệu Dựa Trên AI</h3>

<p align="center">
  <strong>Hệ thống nhận diện ngôn ngữ ký hiệu tiếng Việt thời gian thực sử dụng Mediapipe và SignLSTM</strong>
</p>

## 🏗️ Kiến trúc hệ thống

<p align="center">
  
  ![image](https://github.com/user-attachments/assets/1144a93e-ac5b-4e27-9446-c1072cb4b44a)
</p>

Hệ thống được thiết kế với kiến trúc đa tầng:

1. **📹 Tầng xử lý đầu vào**: Quay video từ webcam, trích xuất 1662 điểm đặc trưng bằng Mediapipe Holistic.
2. **🧠 Tầng mô hình**: Xử lý chuỗi 30 khung hình bằng mô hình SignLSTM hai tầng.
3. **🔊 Tầng đầu ra**: Hiển thị dự đoán trên màn hình và phát âm thanh nếu độ tin cậy vượt quá 0.8 trong ít nhất 1 giây.

## ✨ Tính năng nổi bật

- **Mô hình SignLSTM** với độ chính xác 90%.
- **Nhận diện thời gian thực**, xử lý chuỗi 30 khung hình với thời gian suy luận ~30ms.
- **Phát hiện hành động ổn định**, tránh trùng lặp âm thanh.
- **Phản hồi âm thanh**, hỗ trợ giao tiếp hiệu quả.
- **Nhận diện 10 hành động**: "null", "xin chao", "cam on", "xin loi", "hanh phuc", "tuyet voi", "yeu thuong", "ghet", "biet on", "tam biet".

## 🔧 Công nghệ sử dụng

[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=yellow)](https://www.python.org/)
[![Mediapipe](https://img.shields.io/badge/Mediapipe-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://mediapipe.dev/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=for-the-badge&logo=tensorflow&logoColor=white)](https://www.tensorflow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)](https://opencv.org/)

## 📥 Cài đặt

### 🛠️ Yêu cầu hệ thống

- **Python** `3.8+`
- **Webcam** (khuyến nghị 1280x720)
- **RAM** `4GB+`
- **CPU** `2+ nhân`
- **Dung lượng lưu trữ** `2GB+`

### ⚙️ Hướng dẫn cài đặt

1. **Tải mã nguồn**
   ```bash
   git clone https://github.com/DangTruongDuong/sign-language-detection-using-lstm
   cd sign-language-detection-using-lstm
   ```

2. **Tạo môi trường ảo**
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts ctivate
   ```

3. **Cài đặt các thư viện**
   ```bash
   pip install opencv-python numpy mediapipe tensorflow scikit-learn pygame Pillow
   ```

4. **Chuẩn bị thư mục dữ liệu và âm thanh**
   ```bash
   mkdir MP_Data sounds
   # Sao chép các file .mp3 đã ghi sẵn vào thư mục sounds/
   ```

5. **Chuẩn bị font chữ tiếng Việt**
   ```bash
   # Sử dụng font mặc định (ví dụ: C:/Windows/Fonts/arial.ttf)
   # Nếu không có, tải font hỗ trợ tiếng Việt và cập nhật font_path trong predict.py
   ```

## 🚀 Bắt đầu sử dụng

### 📥 Thu thập dữ liệu
   ```bash
   Thu_Thap_Data.py
   ```
**Thu thập dữ liệu**: Tôi đã viết hướng dẫn rõ ràng, nhấn mạnh vai trò của dòng chữ "Collecting Data" như một tín hiệu để người dùng chuẩn bị và thực hiện hành động đúng thời điểm.


Nếu bạn muốn bổ sung chi tiết hơn (ví dụ: cách cài đặt môi trường, xử lý lỗi thường gặp), hãy cho tôi biết nhé!

### 🧠 Huấn luyện mô hình
   ```bash
   huan_luyen_mo_hinh.py
   ```
**Huấn luyện mô hình**: Vì bạn nói chỉ cần chạy file, tôi giữ hướng dẫn đơn giản, không thêm bước phức tạp.
### ⚡ Khởi động 
   ```bash
   Run_With_Sound.py or Run_No_Sound
   ```

### 📊 Đánh giá mô hình
   ```bash
   Ve_mo_So_do_mo_hinh_va_so_sanh.ipynb
   ```
6. **Kết quả và độ chính xác**
## 📊 Kết quả

<p align="center">
  <img src="https://github.com/user-attachments/assets/1bfaf6b2-ffc3-4b9a-a2da-1d050caa8122" alt="Kết quả tổng quan" width="600"/>
</p>

### 📈 Hiệu suất mô hình
- **Độ chính xác**: Mô hình SignLSTM đạt **90%** trên tập kiểm tra, với 10% dữ liệu được chia để đánh giá (90% train, 10% test).  
- **Thời gian suy luận**: Trung bình **~30ms** mỗi khung hình, cho phép xử lý thời gian thực với tốc độ **20-33 FPS** trên webcam 1280x720.  
- **Nhầm lẫn hành động**: Nhầm lẫn chủ yếu xảy ra giữa các hành động tương tự như **"xin chao"** và **"cam on"** (dựa trên quan sát từ dữ liệu thử nghiệm).

### ⏱️ Nhận diện thời gian thực
- Hệ thống hoạt động ổn định trên webcam tiêu chuẩn, hiển thị nhãn hành động và phát âm thanh chính xác khi độ tin cậy **≥ 0.8** trong **≥ 1 giây**.  
- Tốc độ xử lý trung bình **20-33 FPS**, phụ thuộc vào hiệu suất phần cứng.

### ⚠️ Hạn chế và cải tiến
- **Hạn chế**: Yêu cầu ánh sáng tốt để Mediapipe hoạt động hiệu quả; chỉ nhận diện các hành động đã được huấn luyện.  
- **Cải tiến đề xuất**: Thu thập thêm dữ liệu cho các hành động dễ nhầm lẫn (như **"xin chao"**, **"hanh phuc"**); tối ưu hóa mô hình bằng pruning hoặc quantization để tăng tốc độ trên thiết bị yếu.

### 📉 Phân phối thời gian suy luận so với các mô hình khác
<p align="center">
  <img src="https://github.com/user-attachments/assets/745494bf-9afa-49f3-9b6b-55849eee3d6d" alt="Phân phối thời gian suy luận" width="600"/>
</p>
SignLSTM có thời gian suy luận trung bình **~30ms**, nhanh hơn đáng kể so với các mô hình khác (ví dụ: Transformer ~50ms), phù hợp cho ứng dụng thời gian thực.

### 📊 So sánh hiệu suất với các mô hình khác
<p align="center">
  <img src="https://github.com/user-attachments/assets/dd017db6-ee3d-47d2-909e-2e81dcdb52e5" alt="So sánh hiệu suất" width="600"/>
</p>
SignLSTM vượt trội với độ chính xác **90%**, trong khi các mô hình khác (như Transformer) chỉ đạt khoảng **13%** trên cùng tập dữ liệu.

### 🧩 Ma trận nhầm lẫn
<p align="center">
  <img src="https://github.com/user-attachments/assets/a9a6f907-c670-4380-8888-ec71a4f7e3d8" alt="Ma trận nhầm lẫn" width="600"/>
</p>
Ma trận nhầm lẫn cho thấy các hành động như **"xin chao"** và **"cam on"** có tỷ lệ nhầm lẫn cao nhất, do sự tương đồng trong cử chỉ tay.

 ## 📚 Tài liệu hướng dẫn
  

- 📖 Hướng dẫn cài đặt
- 👥 Hướng dẫn sử dụng
- 🔧 Tài liệu API
- 🤝 Hướng dẫn đóng góp

## 📝 Bản quyền

© 2025 DangTruongDuong-Nhóm 1-CNTT_16-01, Khoa Công nghệ Thông tin, Đại học Đại Nam. Mọi quyền được bảo lưu.
<div align="center">
Được thực hiện bởi 💻 Nhóm 1-CNTT_16-01 tại Đại học Đại Nam

Email cá nhân : dangtruonduong2102@gmail.com
</div>
