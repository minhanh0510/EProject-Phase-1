Hệ thống hoạt động trên Docker 
![alt text](public/img/11.png)

Test Case 1: Đăng ký user mới thành công
Method: POST
URL: http://localhost:3003/auth/register
Body: 
{
    "username": "minhanh1",
    "password": "123456"
}
Kết quả: {
    "username": "minhanh1",
    "password": "$2a$10$2odRWRqgqcZ9QjAVMqq1eOPTGzOAVa8hxwvrpON.Bb0CjoRWnMpXK",
    "_id": "68fd179c03c20188ada5bcc5",
    "__v": 0
}
![alt text](public/img/1.png)


Test Case 2: Đăng ký user mới không thành công
Method: POST
URL: http://localhost:3003/auth/register
Body: 
{
    "username": "minhanh",
    "password": "123456"
}
Kết quả: {"message":"Username already taken"}
![alt text](public/img/7.png)


Test Case 3: Đăng nhập thành công
Method: POST
URL: http://localhost:3003/auth/login
Body: 
{
    "username": "minhanh",
    "password": "123456"
}
Kết quả: {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6IjY4ZmQxODEzMDNjMjAxODhhZGE1YmNjOSIsImlhdCI6MTc2MTQxNzI5OX0.s3GdE1kvWFGsDQtgBuKjFS1KgTgXL6-WWdvFPgmKUJc"
}
![alt text](public/img/2.png)

Test Case 4: Đăng nhập không thành công
Method: POST
URL: http://localhost:3003/auth/login
Body: 
{
    "username": "minhanh",
    "password": "1234567"
}
Kết quả: {
    "message": "Invalid username or password"
}
![alt text](public/img/8.png)


Test Case 5: Truy cập dashboard (cần xác thực)
Method: GET
URL: http://localhost:3003/auth/dashboard
Kết quả: {"message":"Welcome to dashboard"}
![alt text](public/img/9.png)


Test Case 6: Truy cập dashboard không được (sai token)
Method: GET
URL: http://localhost:3003/auth/dashboard
Kết quả: {
    "message": "Token is not valid"
}
![alt text](public/img/10.png)


Test Case 7: Tạo 1 sản phẩm mới
Method: POST
URL: http://localhost:3003/products/api/products
Kết quả: {
    "name": "Laptop Dell",
    "price": 1500,
    "description": "High performance laptop",
    "_id": "68fd1aa9e00f08db0a0e0616",
    "__v": 0
}
![alt text](public/img/3.png)

Test Case 8: Xem danh sách sản phẩm
Method: GET
URL: http://localhost:3003/products/api/products
Kết quả: [
    {
        "_id": "68fd03bf5304f4f3aa22f27a",
        "name": "Ip",
        "price": 200,
        "description": "co 2 khe sim",
        "__v": 0
    },
    {
        "_id": "68fd05dfe00f08db0a0e060d",
        "name": "Ip16",
        "price": 200,
        "description": "co 2 khe sim",
        "__v": 0
    },
    {
        "_id": "68fd1aa9e00f08db0a0e0616",
        "name": "Laptop Dell",
        "price": 1500,
        "description": "High performance laptop",
        "__v": 0
    }
]
![alt text](public/img/6.png)

Test Case 9: Thao tác đặt hàng
Method: POST
URL: http://localhost:3003/products/api/products/buy
Kết quả: {
    "status": "completed",
    "products": [
        "68fd1aa9e00f08db0a0e0616"
    ],
    "orderId": "68d5a61c-8767-47ac-ad15-985a071de31f",
    "totalPrice": 1500
}
![alt text](public/img/4.png)

Test Case 10: Xem sản phẩm theo id
Method: GET
URL: http://localhost:3003/products/api/products/68fd1aa9e00f08db0a0e0616
Kết quả: {
    "_id": "68fd1aa9e00f08db0a0e0616",
    "name": "Laptop Dell",
    "price": 1500,
    "description": "High performance laptop",
    "__v": 0
}
![alt text](public/img/5.png)


Thao tác với github Action: Thực hiện CI/CD với dự án
![alt text](public/img/12.png)