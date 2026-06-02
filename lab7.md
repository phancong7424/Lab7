# BÁO CÁO THỰC HÀNH KIỂM THỬ API BẰNG POSTMAN

Họ và tên Phan Văn Công  
Mã sinh viên [Điền mã sinh viên]  
Môn học [Điền tên môn học]

---

# 1. Mục tiêu bài thực hành

Trong bài thực hành này, em tiến hành tìm hiểu và sử dụng công cụ Postman để kiểm thử API. Các mục tiêu chính bao gồm

- Làm quen với giao diện và các chức năng cơ bản của Postman.
- Thực hành gửi các yêu cầu HTTP phổ biến gồm
  - GET
  - POST
  - PUT
  - PATCH
  - DELETE
- Làm việc với dữ liệu định dạng JSON.
- Kiểm tra và phân tích kết quả trả về từ API thông qua Status Code và Response Body.
- Hiểu rõ sự khác biệt giữa các phương thức HTTP trong quá trình trao đổi dữ liệu giữa Client và Server.

---

# 2. Thông tin API sử dụng

Để thực hiện kiểm thử, em sử dụng dịch vụ REST API giả lập miễn phí dành cho việc học tập và phát triển ứng dụng.

- Tên API JSONPlaceholder
- Website httpsjsonplaceholder.typicode.com
- Base URL

```text
httpsjsonplaceholder.typicode.com
```

JSONPlaceholder cung cấp các tài nguyên mẫu như

- Posts
- Comments
- Albums
- Photos
- Todos
- Users

Trong bài thực hành này, em sử dụng tài nguyên Posts để kiểm tra các phương thức HTTP.

---

# 3. Nội dung thực hành và kết quả

## 3.1. Thực hiện phương thức GET

### Mục đích

Lấy danh sách bài viết từ máy chủ.

### Endpoint

```http
GET posts
```

### URL đầy đủ

```text
httpsjsonplaceholder.typicode.composts
```

### Các bước thực hiện

1. Mở Postman.
2. Chọn phương thức GET.
3. Nhập URL API.
4. Nhấn nút Send.

### Kết quả nhận được

- Request được thực hiện thành công.
- Status Code trả về

```text
200 OK
```

- Response Body chứa danh sách các bài viết dưới dạng JSON.

### Nhận xét

Phương thức GET được sử dụng để truy xuất dữ liệu từ server mà không làm thay đổi dữ liệu hiện có.

### Hình ảnh minh họa

![GET Request](anhCreate First API Request.png)

---

## 3.2. Thực hiện phương thức POST

### Mục đích

Tạo mới một bài viết trên hệ thống.

### Endpoint

```http
POST posts
```

### URL đầy đủ

```text
httpsjsonplaceholder.typicode.composts
```

### Dữ liệu gửi lên

```json
{
    userId 1,
    title test Postman,
    body Understand HTTP METHODS
}
```

### Các bước thực hiện

1. Chọn phương thức POST.
2. Chuyển sang tab Body.
3. Chọn raw.
4. Chọn định dạng JSON.
5. Nhập dữ liệu JSON.
6. Nhấn Send.

### Kết quả nhận được

- Dữ liệu được tạo thành công.
- Status Code

```text
201 Created
```

- Server trả về dữ liệu vừa tạo kèm theo ID mới.

### Response mẫu

```json
{
    userId 1,
    title test Postman,
    body Understand HTTP METHODS,
    id 101
}
```

### Nhận xét

POST được sử dụng khi cần thêm mới dữ liệu vào hệ thống.

### Hình ảnh minh họa

![POST Request](anhPOST Method Explained.png)

---

## 3.3. Thực hiện phương thức PUT

### Mục đích

Cập nhật toàn bộ nội dung của bài viết có ID = 10.

### Endpoint

```http
PUT posts10
```

### URL đầy đủ

```text
httpsjsonplaceholder.typicode.composts10
```

### Dữ liệu gửi lên

```json
{
    userId 1,
    title test Postman,
    body Understand HTTP METHODS updated
}
```

### Các bước thực hiện

1. Chọn phương thức PUT.
2. Nhập URL cần cập nhật.
3. Chọn tab Body → raw → JSON.
4. Nhập dữ liệu mới.
5. Nhấn Send.

### Kết quả nhận được

- Cập nhật thành công.
- Status Code

```text
200 OK
```

### Response mẫu

```json
{
    userId 1,
    title test Postman,
    body Understand HTTP METHODS updated,
    id 10
}
```

### Nhận xét

PUT sẽ thay thế toàn bộ dữ liệu của tài nguyên bằng dữ liệu mới được gửi lên.

### Hình ảnh minh họa

![PUT Request](anhPUT Method Explained.png)

---

## 3.4. Thực hiện phương thức PATCH

### Mục đích

Cập nhật một phần dữ liệu của bài viết có ID = 10.

### Endpoint

```http
PATCH posts10
```

### URL đầy đủ

```text
httpsjsonplaceholder.typicode.composts10
```

### Dữ liệu gửi lên

```json
{
    title test Postman NEW
}
```

### Các bước thực hiện

1. Chọn phương thức PATCH.
2. Nhập URL API.
3. Chọn tab Body → raw → JSON.
4. Nhập trường cần cập nhật.
5. Nhấn Send.

### Kết quả nhận được

- Cập nhật thành công.
- Status Code

```text
200 OK
```

### Response mẫu

```json
{
    userId 1,
    id 10,
    title test Postman NEW,
    body ...
}
```

### Nhận xét

PATCH chỉ cập nhật những trường được chỉ định, giúp tiết kiệm dữ liệu truyền tải hơn so với PUT.

### Hình ảnh minh họa

![PATCH Request](anhPATCH Method Explained.png)

---

## 3.5. Thực hiện phương thức DELETE

### Mục đích

Xóa bài viết có ID = 10.

### Endpoint

```http
DELETE posts10
```

### URL đầy đủ

```text
httpsjsonplaceholder.typicode.composts10
```

### Các bước thực hiện

1. Chọn phương thức DELETE.
2. Nhập URL cần xóa.
3. Nhấn Send.

### Kết quả nhận được

- Xóa thành công.
- Status Code

```text
200 OK
```

### Response trả về

```json
{}
```

### Nhận xét

DELETE được sử dụng để xóa dữ liệu khỏi hệ thống.

### Hình ảnh minh họa

![DELETE Request](anhDELETE Method.png)

---

# 4. So sánh các phương thức HTTP đã thực hành

 Phương thức  Chức năng  Status Code thường gặp 
-----------------------------------------------
 GET  Lấy dữ liệu  200 OK 
 POST  Tạo mới dữ liệu  201 Created 
 PUT  Cập nhật toàn bộ dữ liệu  200 OK 
 PATCH  Cập nhật một phần dữ liệu  200 OK 
 DELETE  Xóa dữ liệu  200 OK 

---

# 5. Kết luận

Sau khi hoàn thành bài thực hành, em đã

- Biết cách tạo Collection và Request trong Postman.
- Thực hiện thành công các phương thức HTTP cơ bản.
- Hiểu cách gửi dữ liệu JSON thông qua tab Body.
- Biết cách đọc và phân tích Status Code từ server.
- Phân biệt được sự khác nhau giữa PUT và PATCH.
- Hiểu được quy trình giao tiếp cơ bản giữa Client và REST API.

Bài thực hành giúp em nắm được những kiến thức nền tảng về kiểm thử API, là bước quan trọng để phát triển và kiểm thử các ứng dụng Web, Mobile và hệ thống Backend trong thực tế.

---

# 6. Tài liệu tham khảo

## JSONPlaceholder

httpsjsonplaceholder.typicode.com

## Video tham khảo

httpswww.youtube.comwatchv=T_PV6KDzq_Y

httpswww.youtube.comwatchv=geGsavlMVDQ

## Tài liệu Postman

httpslearning.postman.com

httpswww.postman.com
