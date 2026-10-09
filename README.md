# 1. Sơ đồ luồng IPO (Input – Process – Output):
Plaintext

INPUT: Yêu cầu khởi tạo hạ tần sever cho dự án Smart Farm


PROCESS:
- Dùng New-Item -Force tạo cây thư mục lồng nhau: smart-farm\data\logs & smart-farm\code
- Dùng New-Item tạo đồng thời các file cấu hình: config.json, sensors.py, .env
- Dùng Copy-Item sao chép toàn bộ thư mục code sang backup\code_v1 kèm nội dung đệ quy.


OUTPUT: 
- Cấu trúc cây thư mục smart-farm\data\logs và smart-farm\code được thiết lập chuẩn xác. 
- Các file config.json, sensors.py, và .env ẩn được khởi tạo hoàn tất bên trong thư mục code.
- Thư mục backup\code_v1 chứa toàn bộ bản sao được đồng bộ an toàn.

# 2. Danh sách các câu lệnh PowerShell đã sử dụng:
Bạn lần lượt chạy các câu lệnh sau trên Terminal PowerShell của máy chủ:

Bước 1: Tạo cây thư mục lồng nhau (smart-farm\data\logs và smart-farm\code) bằng 1 dòng lệnh
Sử dụng tham số -Force để PowerShell tự động tạo các thư mục cha/con còn thiếu tương tự cơ chế -p của lệnh mkdir trên Linux:

PowerShell
New-Item -ItemType Directory -Force -Path "smart-farm\data\logs", "smart-farm\code"


Bước 2: Di chuyển vào thư mục code để tạo file cấu hình
PowerShell
cd smart-farm\code


Bước 3: Tạo cùng lúc 3 file cấu hình (config.json, sensors.py, .env ẩn) bằng 1 dòng lệnh
PowerShell
New-Item -ItemType File -Force -Path "config.json", "sensors.py", ".env"


Bước 4: Quay lại thư mục gốc và sao chép toàn bộ thư mục code sang backup\code_v1
PowerShell
cd ..
Copy-Item -Path "code" -Destination "..\backup
