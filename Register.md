***Test case cho màn hình Register***

**Mã testcase**: ID_1

**Mục đích kiểm thử**: Kiểm tra đăng ký với thông tin hợp lệ 

**Dữ liệu đầu vào**:
- Name: 'Hoang'
- Email: 'hoang@gmail.com'
- Password: '123456'
- Confirm Password: '123456'

**Các bước thực hiện**:
1. Nhập đầy đủ thông tin
2. Nhấn "REGISTER"
   
**Kết quả mong muốn**:
- Hiển thị Alert "Register successful"
- Điều hướng màn hình đến "CodeScreen" và truyền vào email

**Trạng thái**: Pass / Fail



**Mã testcase**: ID_2

**Mục đích kiểm thử**: Kiểm tra khi bỏ trống thông tin 

**Dữ liệu đầu vào**: Bất kì trường nào trống 

**Các bước thực hiện**: Không có 
   
**Kết quả mong muốn**:
- Hiển thị Alert "Please fill in all fields"

**Trạng thái**: Pass / Fail


**Mã testcase**: ID_3

**Mục đích kiểm thử**: Kiểm tra mật khẩu và xác nhận mật khẩu có trùng khớp với nhau 

**Dữ liệu đầu vào**:
- Password: '123456'
- Confirm Password: 'asdfgh'

**Các bước thực hiện**: Nhập thông tin tương ứng với dữ liệu đầu vào 

**Kết quả mong muốn**:
- Hiển thị Alert "Passwords do not match" 

**Trạng thái**: Pass / Fail


**Mã testcase**: ID_4

**Mục đích kiểm thử**: Kiểm tra khi email đã được đăng ký

**Dữ liệu đầu vào**:
- Email: 'hoang@gmail.com'(đã được đăng ký)
  
**Các bước thực hiện**: Nhập với dữ liệu đầu vào 
   
**Kết quả mong muốn**:
- Hiển thị Alert "Email Already Exists"
- Trường email bị xóa

**Trạng thái**: Pass / Fail


**Mã testcase**: ID_5

**Mục đích kiểm thử**: Kiểm tra đăng nhập với tài khoản hợp lệ  

**Dữ liệu đầu vào**:
- Email: `test@example.com`  
- Password: `123456`

**Các bước thực hiện**:
1. Nhập email `test@gmail.com` vào ô email
2. Nhập mật khẩu `123456` vào ô mật khẩu
3. Nhấn nút "LOG IN"
   
**Kết quả mong muốn**:
- Hiển thị Alert "Login Successful"
- Điều hướng đến màn hình Home
- Lưu accessToken và user vào AsyncStorage

**Trạng thái**: Pass / Fail
