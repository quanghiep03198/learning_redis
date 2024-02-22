![logo](./images/redis-logo.png)

## Redis - Giới thiệu

**Redis** (viết tắt của **Remote Dictionary Server**) là một hệ thống lưu trữ dữ liệu trong bộ nhớ hoạt động dưới dạng cơ sở dữ liệu **key-value**.

**Redis** không chỉ đơn thuần là một cơ sở dữ liệu **key-value**, mà còn hỗ trợ các cấu trúc dữ liệu phức tạp như **danh sách**, **tập hợp**, **tập hợp được sắp xếp** và **bảng băm**.

## Các điểm nổi bật của Redis

- Tốc độ nhanh: Redis hoạt động trong bộ nhớ, giúp truy vấn và ghi dữ liệu với tốc độ cao.
- Hỗ trợ nhiều kiểu dữ liệu: Redis không chỉ hỗ trợ lưu trữ giá trị đơn giản, mà còn cho phép bạn làm việc với các cấu trúc dữ liệu phức tạp.
- Sử dụng rộng rãi: Redis được sử dụng cho việc caching, truyền thông qua message queue, và lưu trữ dữ liệu.

## Cách cài đặt và sử dụng Redis

**1. Cài đặt**

> Xem cách cài đặt tại [trang chủ](https://redis.io/docs/install/install-redis/) của **Redis**

**2. Sử dụng**

**Connect đến Redis**

```shell
redis-cli
```

## Các lệnh phổ biến

**1. Xóa 1 key nếu nó tồn tại**

```shell
DEL <key_name>
```

**2. Kiểm tra sự tồn tại của 1 key**

```shell
EXISTS <key_name>
```

**3. Đặt exprire time cho key sau "n" giây"**

```shell
EXPIRE <key_name> n
```

**4. Xóa expire time của key**

```shell
PERSIST <key_name>
```

**5. Lấy tất cả các keys đang tồn tại**

```shell
KEYS <pattern>
```

_Example_ : `KEYS *token*`

**6. Check thời gian sống của 1 key**

```shell
TTL <key_name>
```

**7. Đổi tên key**

```shell
RENAME <curent_key> <new_key>
```

_Hoặc rename key nếu <new_key> chưa tồn tại_

```shell
RENAMENX <curent_key> <new_key>
```

**8. Lấy kiểu dữ liệu được lưu trữ bởi key**

```shell
TYPE <key_name>
```
