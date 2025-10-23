1. Kiến trúc dự án
2. 
<img width="490" height="1024" alt="image" src="https://github.com/user-attachments/assets/d7fb32ad-3ddd-4ce2-be02-2bbc175df026" />

- Mô tả tổng thể Project:

Dự án được xây dựng theo kiến trúc microservices, gồm 4 dịch vụ chính:

api-gateway: Cổng giao tiếp trung tâm, định tuyến request đến các service.

auth: Xử lý xác thực người dùng (login, register, JWT, v.v.)

product: Quản lý thông tin sản phẩm.

order: Xử lý đơn hàng, kết nối với auth và product.

utils: Chứa các hàm tiện ích dùng chung giữa các service (như middleware isAuthenticated.js).

Dự án có tệp docker-compose.yml, cho phép chạy toàn bộ hệ thống bằng Docker, dễ dàng triển khai và quản lý container cho từng service.

2.  Công nghệ sử dụng

<img width="869" height="526" alt="image" src="https://github.com/user-attachments/assets/1cf054e6-27d9-4d87-b957-614dbb796d60" />

3. Tạo các file .env

   
- auth service
  
<img width="596" height="99" alt="image" src="https://github.com/user-attachments/assets/1254d7a1-3d61-4f72-b8a9-7a0344bea878" />

- order service


<img width="635" height="142" alt="image" src="https://github.com/user-attachments/assets/90bb63c7-c5d6-4f59-921a-e03a4a012288" />


- product service

<img width="673" height="137" alt="image" src="https://github.com/user-attachments/assets/65c05418-0933-4b4b-9dd3-69971e3282c5" />

- .env cho thư mục gốc

<img width="396" height="69" alt="image" src="https://github.com/user-attachments/assets/40155d22-f786-4612-860b-06c436071c96" />

4. Kiểm tra trạng thái container

Gõ lệnh : docker compose ps

5. Test các API bằng 

Request: POST http://localhost:3003/auth/register → Đăng ký tài khoản.

Request: POST http://localhost:3003/auth/login → Đăng nhập và nhận Token.

Request: POST http://localhost:3003/products/api/products → Thêm sản phẩm vào phần body- row. Nhập Token vào Bearer Token.

Request: GET  http://localhost:3003/products/api/products  →  Xem sản phẩm. chon vào Bearer Token , nhập Token vào.

Request: POST http://localhost:3003/products/api/products/buy   → order sản phẩm nhập vào ids của id sản phẩm send 
được bỏ vô trong row.


   
