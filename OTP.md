***Test case màn hình xác thực OTP***

**Mã testcase**: ID_1

**Mục đích kiểm thử**: Kiểm tra hệ thống khi người dùng nhập đúng mã OTP 6 chữ số 

**Dữ liệu đầu vào**: Mã OTP hợp lệ được gửi qua email

**Các bước thực hiện**:
1. Mở màn hình nhập mã OTP
2. Nhập đầy đủ 6 chữ số OTP hợp lệ được gửi về email của bạn
3. Nhấn nút Verify
   
**Kết quả mong muốn**:
- Thông báo: Xác minh OTP thành công!
- Điều hướng màn hình về màn hình Login



**Mã testcase**: ID_2

**Mục đích kiểm thử**: Kiểm tra hệ thống phản hồi khi người dùng nhập thiếu mã OTP

**Dữ liệu đầu vào**: Không có 

**Các bước thực hiện**:
1. Nhập ít hơn 6 chữ số (ví dụ: 123)
2. Nhấn nút Verify
   
**Kết quả mong muốn**:
- Hiển thị cảnh báo: Vui lòng nhập đủ 6 chữ số OTP
- Không gọi API, không chuyển trang 


**Mã testcase**: ID_3

**Mục đích kiểm thử**: Kiểm tra người dùng không thể nhập ký tự không hợp lệ (chữ cái, kí hiệu, ...)

**Dữ liệu đầu vào**: Không có

**Các bước thực hiện**:
1. Cố gắng nhập ký tự như 'a', '@', '-' vào ô OTP
   
**Kết quả mong muốn**:
- Các ký tự không hợp lệ và bị từ chối
- Chỉ nhận các chữ số (0-9)


**Mã testcase**: ID_4

**Mục đích kiểm thử**: Kiểm tra tính năng tự động chuyển sang ô tiếp theo hoặc quay lại ô trước

**Dữ liệu đầu vào**: Không có 

**Các bước thực hiện**:
1. Nhập số vào từng ô -> COn trỏ tự chuyển sang ô tiếp theo
2. Xóa một ô -> Con trỏ trở về ô trước đó
   
**Kết quả mong muốn**:
- Điều hướng con trỏ mượt mà đúng như logic đã xử lý


