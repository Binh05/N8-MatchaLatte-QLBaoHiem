3.3. Cài đặt ứng dụng 

3.3.1 Cài đặt cơ sở dữ lieu 

Bước 1: Mở file QuanLyBaoHiem trong SQL Server Management Studio. 

Bước 2: Login với Authentication là Window Authentication. 

Bước 3: Nhấn F5 hoặc execute để khởi tạo cơ sở dữ liệu. 

3.3.2 Cài đặt backend 

Bước 1: Cài đặt Python Ứng dụng yêu cầu Python phiên bản 3.7 trở lên. Để kiểm tra phiên bản Python trên máy tính, bạn mở Command Prompt (Windows) hoặc Terminal (Mac, Linux) và gõ:  

python --version  

Nếu chưa cài đặt Python, bạn tải tại: https://www.python.org/downloads/  

Lưu ý: Trong quá trình cài đặt, nhớ tick chọn Add Python to PATH trước khi nhấn Install. 

Bước 2: Cài đặt các thư viện cần thiết: 

Bước 2.1: Mở Command Prompt hoặc Terminal.  

Bước 2.2: Điều hướng đến thư mục chứa file app.py và requirements.txt bằng lệnh: cd đường_dẫn_đến_thư_mục_của_bạn Ví dụ: cd D:\project\flask_app  

Bước 2.3: Cài đặt các thư viện được liệt kê trong file requirements.txt bằng lệnh:  

pip install -r requirements.txt  

Lưu ý: Nếu chưa có pip, bạn có thể kiểm tra bằng: pip --version Nếu chưa có, cài pip theo hướng dẫn tại: https://pip.pypa.io/en/stable/installation/ 

 

Bước 3: Cấu hình kết nối cơ sở dữ liệu SQL Server  

Tìm đến hàm get_db_connection() trong file app.py, ví dụ: def get_db_connection():  

conn = pyodbc.connect(  

'DRIVER={ODBC Driver 17 for SQL Server};'  

'SERVER=localhost;' 'DATABASE=TenCSDL;'  

'UID=sa;'  

'PWD=123456' )  

return conn  

Chỉnh sửa các thông số:  

SERVER: tên server SQL của bạn (ví dụ: localhost, DESKTOP-XXXX\SQLEXPRESS)  

DATABASE: tên cơ sở dữ liệu mà ứng dụng sử dụng  

Ví dụ chỉnh sửa: 'SERVER=DESKTOP-ABCD\SQLEXPRESS;' 'DATABASE=QLSinhVien;' 'Trusted_Connection=yes;’ 

Bước 4: Chạy ứng dụng Flask  

Bước 4.1: Trong terminal, đảm bảo bạn đang ở thư mục chứa file app.py.  

Bước 4.2: Chạy ứng dụng bằng lệnh: flask run 

Bước 4.3: Nếu ứng dụng chạy thành công, bạn sẽ thấy thông báo đại loại như: 

Running on http://127.0.0.1:5000/  

Restarting with stat 

3.3.3 Cài đặt front - end 

Bước 1: Mở file index.html 
Bước 2: Nhập chuột phải và chọn Open With Live Server. 