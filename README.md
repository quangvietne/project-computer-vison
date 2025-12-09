# Mô tả dự án 
- Dự án này giải quyết bài toán phát hiện đối tượng nhỏ (người, phương tiện) trên ảnh hồng ngoại nhiệt thu thập từ UAV ở độ cao lớn (60m - 130m). Ảnh nhiệt có độ tương phản thấp và chi tiết mờ, khiến các mô hình thông thường gặp khó khăn.
- Giải pháp của là xây dựng Mô hình Lai (Hybrid Model): sử dụng kiến trúc YOLOv8 làm nền tảng (Head/Neck) và thay thế Backbone mặc định bằng các mạng CNN hiện đại để tối ưu hóa việc trích xuất đặc trưng.

# Phương pháp : 
- Dataset: Sử dụng bộ dữ liệu HIT-UAV gồm 2,898 ảnh nhiệt được chọn lọc kỹ, bao gồm cả điều kiện ban ngày và ban đêm.
- Kiến trúc: YOLOv8 Detect Head kết hợp với Custom Backbones:
 + Lightweight: MobileNet (v2 , v3), EfficientNet (B0, B3).
 + Modern CNN: ConvNeXt (Tiny, Small).

# Cách tải dữ liệu
## Dữ liệu đầy đủ: https://github.com/suojiashun/HIT-UAV-Infrared-Thermal-Dataset

## Dữ liệu trên kaggle: https://www.kaggle.com/datasets/pandrii000/hituav-a-highaltitude-infrared-thermal-dataset

# Cách tổ chức thư mục :
- notebook ( nơi chứa các file notebook chạy code)
- data/HIT-UAV-Infrared-Thermal-Dataset ( nơi chữa dữ liệu)
 
# Kịch bản thực nghiệm
- chọn mô hình cần thử nghiệm (backbone + phiên bản yolov8/yolov11)
- chuẩn bị dữ liệu (dataloader)
- huấn luyện mô hình trên bộ dữ liệu
- đánh giá mô hình (mAP, precision-recall)
- lưu kết quả huấn luyện và đánh giá
- so sánh kết quả giữa các mô hình