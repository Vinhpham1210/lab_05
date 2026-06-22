# Lab 5 V4: Dockerized Multi-Model AI Inference Service for AIoT

Dự án xây dựng một AI Inference Service cho hệ thống AIoT sử dụng **FastAPI** và **Docker**. Service cung cấp các API để xử lý dữ liệu telemetry (JSON) và phân loại ảnh, giúp triển khai các model AI đã train (từ Lab 3 & Lab 4) thành một dịch vụ thực tế, ổn định và dễ dàng chia sẻ.

## 🚀 Tính năng nổi bật

* **Xử lý Telemetry:** Cung cấp các endpoint phát hiện bất thường (`/detect-anomaly`), dự báo (`/forecast`), và đánh giá rủi ro (`/predict-risk`).
* **Computer Vision:** Phân loại ảnh sử dụng model SqueezeNet ONNX ImageNet-1K, hỗ trợ trả về JSON hoặc ảnh đã gắn nhãn.
* **Giao diện trực quan:** Tích hợp sẵn Web UI mini (`/classify-image-demo`) để test upload ảnh trực tiếp.
* **Giám sát & Logging:** Có endpoint Health check và tự động ghi log kết quả inference ra file CSV.
* **Deployment-ready:** Đóng gói hoàn chỉnh với **Docker** và **Docker Compose**, loại bỏ lỗi xung đột môi trường.

## 🛠 Công nghệ sử dụng

* **Backend:** Python, FastAPI, Uvicorn
* **AI/ML:** ONNX Runtime, NumPy, Pillow
* **Deployment:** Docker, Docker Compose

## 📂 Cấu trúc thư mục (Tóm tắt)

| Tên File / Thư mục | Loại | Chức năng chính |
| :--- | :---: | :--- |
| **`app/`** | 📁 | Mã nguồn chính của FastAPI service |
| **`models/vision/`** | 📁 | Nơi lưu trữ Model ONNX và file labels |
| **`outputs/`** | 📁 | Nơi chứa file log (CSV) và ảnh kết quả sau khi inference |
| **`sample_images/`** | 📁 | Chứa các ảnh mẫu dùng để test tính năng upload |
| **`sample_requests/`** | 📁 | Chứa các file JSON mẫu để gọi thử API |
| **`scripts/`** | 📁 | Các script tiện ích (ví dụ: tải model, smoke test) |
| **`Dockerfile`** | 📄 | File định nghĩa các bước build Docker image |
| **`docker-compose.yml`** | 📄 | Cấu hình chạy đồng bộ các service bằng Docker Compose |
| **`requirements.txt`** | 📄 | Liệt kê các thư viện Python dự án đang sử dụng |
