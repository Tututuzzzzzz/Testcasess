***Test Case cho màn hình đăng nhập***


**Mã testcase**: ID_1

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


**Mã testcase**:ID_2

**Mục đích kiểm thử**: Kiểm tra khi để trống email hoặc mật khẩu

**Dữ liệu đầu vào**:
- Email: ' "" ' hoặc 'test@gmail.com'
- Password: ' "" ' hoặc '123456'
  
**Các bước thực hiện**:
1. Bỏ trống một trong hai ô input
2. Nhấn nút "LOG IN"
   
**Kết quả mong muốn**:
- Hiển thị thông báo lỗi: "Invalid email or password. Please try again."
  
**Trạng thái**: Pass/ Fail


**Mã testcase**:ID_3

**Mục đích kiểm thử**: Kiểm tra khi nhập mật khẩu sai

**Dữ liệu đầu vào**:
- Email: 'test@gmail.com'
- Password: 'wrongpass'
  
**Các bước thực hiện**:
1. Nhập thông tin ở dữ liệu đầu vào
2. Nhấn nút "LOG IN"

**Kết quả mong muốn**:
- Hiển thị thông báo lỗi: "Login Failed"
  
**Trạng thái**: Pass/ Fail


**Mã testcase**:ID_4

**Mục đích kiểm thử**: Kiểm tra nút icon ẩn, hiện mật khẩu

**Dữ liệu đầu vào**:
- Password: '123456'
  
**Các bước thực hiện**:
1. Nhập mật khẩu với dữ liệu đầu vào 
2. Nhấn icon 'eye-outline'

**Kết quả mong muốn**:
- Mật khẩu hiển thị rõ
- Icon chuyển thành 'eye-off-outline'

**Trạng thái**: Pass/ Fail


**Mã testcase**:ID_5

**Mục đích kiểm thử**: Kiểm tra checkbox "Remember me" thay đổi trạng thái đúng khi được nhấn

**Dữ liệu đầu vào**:
- Không nhập dữ liệu

**Các bước thực hiện**:
1. Nhấn vào checkbox "Remember me"
2. Kiểm tra trạng thái checkbox
3. Nhấn lại để checkbox bỏ chọn
4. Kiểm tra trạng thái checkbox

**Kết quả mong muốn**:
- Checkbox chuyển sang trạng thái được chọn ở bước 2: isRemember = true
- Checkbox chuyển sang trạng thái không được chọn ở bước 4: isRemember = fail

**Trạng thái**: Pass/ Fail


**Mã testcase**:ID_6

**Mục đích kiểm thử**: Kiểm tra điều hướng khi người dùng ấn vào "Create an Account"

**Dữ liệu đầu vào**: Không có

**Các bước thực hiện**:
1. Mở ứng dụng và truy cập màn hình Login
2. Nhấn và dòng chữ "Create an Account"

**Kết quả mong muốn**:
- Màn hình sẽ được điều hướng sang màn hình Register
- Màn hình Register hiển thị đầy đủ các trường thông tin đăng ký

**Trạng thái**: Pass/ Fail


**Mã testcase**:ID_7

**Mục đích kiểm thử**: Kiểm tra điều hướng khi người dùng nhấn vào liên kết "Forgot Password"

**Dữ liệu đầu vào**: Không có 

**Các bước thực hiện**:
1. Mở ứng dụng và truy cập vào màn hình Login
2. Nhấp vào dòng chữ "Forgot Password"

**Kết quả mong muốn**:
- Ứng dụng điều hướng sang màn hình Forgot Password
- Màn hình Forgot Password hiện thị trường nhập email và giúp bạn lấy mật khẩu mới

**Trạng thái**: Pass/ Fail

  
