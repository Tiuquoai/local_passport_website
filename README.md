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
```

Server chạy tại: [http://localhost:3000](http://localhost:3000)

---

## Test chức năng

### a. Register  
- **URL:** `POST http://localhost:3000/register`  
- **Body (x-www-form-urlencoded):**
  ```
  username: admin12
  password: 123456
  ```  

**Ảnh test:**  
![Register Form](public/results/4_register.png)  
![User in DB](public/results/4_register_user.png)

---

### b. Login  
- **URL:** `POST http://localhost:3000/login`  
- **Body (x-www-form-urlencoded):**
  ```
  username: admin12
  password: 123456
  ```  

**Ảnh test:**  
![Login](public/results/4_login.png)  
![Cookie](public/results/4_cookie.png)

---

### c. Profile  
- **URL:** `GET http://localhost:3000/profile`  

**Kết quả hiển thị:**  
```html
<h2>Welcome admin12</h2>
<a href="/logout">Logout</a>
```  

Nếu chưa login → redirect về login.  

**Ảnh test:**  
![Profile](public/results/4_profile.png)

---

### d. Logout  
- **URL:** `GET http://localhost:3000/logout`  
- **Kết quả:** Session bị xoá, redirect về trang login  

**Ảnh test:**  
![Logout](public/results/4_logout.png)

---

## Cấu trúc thư mục

```
local_passport_website/
├── README.md
├── app.js
├── config/
│   └── passport.js
├── models/
│   └── user.js
├── routes/
│   └── auth.js
├── views/
│   ├── login.ejs
│   ├── register.ejs
│   └── profile.ejs
├── public/
│   └── results/
│       ├── 4_login.png
│       ├── 4_profile.png
│       ├── 4_logout.png
│       ├── 4_register.png
│       ├── 4_register_user.png
│       └── 4_cookie.png
└── package.json
```

---

## Author
- Name: **Tiuquoai**  
- GitHub: [Tiuquoai](https://github.com/Tiuquoai)
