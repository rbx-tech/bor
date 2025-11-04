# Bor Overview
Bor is the official Golang implementation of the Polygon PoS blockchain. It is a fork of [geth](https://github.com/ethereum/go-ethereum) and is EVM compatible (upto London fork).

## Hướng dẫn build 
Cách 1: Đã có sẵn file bin ở máy hoặc muốn chạy hướng build ra bin rồi mới build docker image

1. chạy lệnh (nếu chưa có file bin ở máy)
```make
make bor-static
```

2. Build docker image
```bash
 docker build -f Dockerfile.binary -t bor-node:v2.3.4.0 .
```

Lưu ý version v2.3.4.0 chỉ là ví dụ 

3. Đăng nhập vào docker hub (làm đúng 1 lần nếu chưa login)
```bash
 docker login
```

4. Đẩy image lên docker hub
```bash
 docker tag bor-node:v2.3.4.0 [your_dockerhub_username]/bor-node:v2.3.4.0
 docker push [your_dockerhub_username]/bor-node:v2.3.4.0
```

Lưu ý: [your_dockerhub_username] đổi thành tài khoản docker hub của bạn.

Cách 2: Build trực tiếp docker image từ source code
1. Build docker image
```make
 docker build -t bor-node:v2.3.4.0 .
```
Lưu ý version v2.3.4.0 chỉ là ví dụ

2. Làm theo bước 3 ở trên để đăng nhập vào docker hub (làm đúng 1 lần nếu chưa login)
3. Làm theo bước 4 ở trên để đẩy image lên docker hub