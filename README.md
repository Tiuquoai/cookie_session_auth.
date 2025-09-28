# Cookie Session Authentication

## Giới thiệu
Đây là project thực hành **Authentication với Session + Cookie** trong Node.js và MongoDB (Lab 6).  
Ứng dụng triển khai các chức năng:
- Đăng ký (Register)
- Đăng nhập (Login)
- Xem profile (Profile)
- Đăng xuất (Logout)

Session được quản lý bởi **express-session**, lưu vào MongoDB qua **connect-mongo**, đồng thời cookie `connect.sid` được gửi xuống client.

---

## Cài đặt & Chạy
1. Clone project:
   ```bash
   git clone https://github.com/Tiuquoai/cookie_session_auth.git
   cd cookie_session_auth
![Node Cookie Auth](./public/results/node%20cookie_auth.js.png)
# a. Register

Method: POST

URL: http://localhost:3000/auth/register

Body (JSON):

{
  "username": "admin1",
  "password": "123456"
}


Kết quả: { "message": "User registered successfully!" }

Ảnh test: 
![Register](./public/results/register.png)
Kiểm tra DB: 
![Check Data](./public/results/checkindata.png)
![Check Data1](./public/results/checkindata1.png)
# b. Login

Method: POST

URL: http://localhost:3000/auth/login

Body (JSON):

{
  "username": "admin1",
  "password": "123456"
}


Kết quả: { "message": "Login successful!" }

Postman sẽ lưu cookie connect.sid.

Ảnh test: 
![Login](./public/results/login.png)
Cookie trong Postman:
![Cookie](./public/results/cookie.png)
Session lưu trong DB: 
![Check Data Login](./public/results/checkindatalogin.png)

# c. Profile

Method: GET

URL: http://localhost:3000/auth/profile

Yêu cầu: Đã login, cookie connect.sid hợp lệ.

Kết quả (VD):

{
  "_id": "68d75cfb347b8062f984f8c5",
  "username": "admin1",
  "__v": 0
}
Ảnh test:
![Go To Profile](./public/results/gotoprifile.png)

# d. Logout

Method: GET

URL: http://localhost:3000/auth/logout

Kết quả: { "message": "Logout successful!" }
Ảnh test:
![Go To Logout](./public/results/gotologout.png)
