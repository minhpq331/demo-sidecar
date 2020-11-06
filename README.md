# Demo Pod

Demo pod nhiều container trên kubernetes

## Docker image:

Sử dụng 2 image sau để làm image cho container trong pod

Nginx: `minhpq331/demo-sidecar:nginx`

PHP-FPM: `minhpq331/demo-sidecar:php-fpm`

Trong đó

- Nginx chạy trên cổng `80`
- PHP-FPM chạy trên cổng `9000`

## Thực hành 3:

- Edit file `pod.yaml` và thêm 2 container sử dụng 2 image ở trên
- Apply file vừa sửa bằng lệnh:

```bash
kubectl -n <ns> apply -f pod.yaml
```

- Chạy port-forward để kiểm tra pod đã chạy thành công hay chưa

```bash
kubectl -n <ns> port-forward --address 0.0.0.0 pod/test-pod 8000:80
```

- Mở url `http://<host>:8000` và kiểm tra response

