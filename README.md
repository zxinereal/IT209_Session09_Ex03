# Bài 3 — Đóng gói trang HTML tĩnh với Nginx

## Nội dung

- `index.html`: trang web trả về dòng `<h1>Hello Docker Session 09!</h1>`.
- `Dockerfile`: dùng image `nginx:alpine` và chép trang HTML vào thư mục web mặc định của Nginx.

## Build image

Chạy lệnh tại thư mục `ex03`:

```bash
docker build -t my-html-app:v1 .
```

## Khởi chạy container

```bash
docker run -d -p 8081:80 --name html-app my-html-app:v1
```

## Kiểm tra

```bash
curl http://localhost:8081
```

Kết quả mong đợi:

```html
<h1>Hello Docker Session 09!</h1>
```

## Dừng và xóa container (khi cần)

```bash
docker rm -f html-app
```
