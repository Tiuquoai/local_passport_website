# Local Passport Website

## Giới thiệu
Đây là project thực hành **Authentication với Passport.js (LocalStrategy)** kết hợp **Session + Cookie** và MongoDB.  
Ứng dụng có các chức năng:
- Đăng ký (Register)  
- Đăng nhập (Login)  
- Xem profile (Profile)  
- Đăng xuất (Logout)

Session được quản lý bằng **express-session**, lưu vào MongoDB qua `connect-mongo`.  
Mật khẩu người dùng được hash bằng **bcryptjs**.

---

## Cài đặt & Chạy

```bash
git clone https://github.com/Tiuquoai/local_passport_website.git
cd local_passport_website
npm install
node app.js

# a. Register

URL: http://localhost:3000/register

Method: POST

Body (x-www-form-urlencoded):

username: admin12

password: 123456
**Ảnh test:**  
- Form Register:  
![Register Form](/public/results/4_register.png)  
- User lưu vào DB:  
![Register User](/public/results/4_register_user.png)
Kết quả: User mới được lưu vào DB. Redirect về trang login.

# b. Login

URL: http://localhost:3000/login

Method: POST

Body (x-www-form-urlencoded):

username: admin12

password: 123456
**ảnh test:** 
![Login](/public/results/4_login.png)  
- Cookie lưu trong Postman:  
![Cookie](/public/results/4_cookie.png)
Kết quả: Nếu đúng → redirect sang /profile (hiện Welcome admin1).
Nếu sai → quay lại trang login.

# c. Profile

URL: http://localhost:3000/profile

Method: GET

Kết quả: Hiện thông tin user (HTML view), ví dụ:

<h2>Welcome admin1</h2>
<a href="/logout">Logout</a>

Nếu chưa login → redirect về trang login.
ảnh test:
![Profile](/public/results/4_profile.png)

# d. Logout

URL: http://localhost:3000/logout

Method: GET

Kết quả: Session bị xoá, redirect về /login.
ảnh test:
![Logout](/public/results/4_logout.png)