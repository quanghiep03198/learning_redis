![logo](./images/redis-logo.png)

# Part 4 - Redis Set

### Redis set là gì

> **Redis set** là 1 tập hợp các cặp key và value, trong đó các giá trị là duy nhất, không trùng lặp và không có thứ tự.

### Ứng dụng sử dụng

- Like/Unlike bài viết, sản phẩm, ...
- Biểu thị mối liên hệ trong các ứng dụng E-commerce, mạng xã hội (bạn bè chung, sản phẩm liên quan,...)

### Các lệnh phổ biến

1. Thêm 1 tập hợp (tạo mới nếu tập hợp không tồn tại)

```shell
SADD <set_name> <value_1> <value_2> ... <value_n>
```

2. Xóa 1 phần tử khỏi tập hợp

```shell
SREM <set_name> <value_1> <value_2> ... <value_n>
```

3. Lấy ra các phần tử có trong tập hợp

```shell
SMEMBERS <set_name>
```

4. Lấy ra số lượng các phần tử có trong tập hợp

```shell
SCARD <set_name>
```

5. Kiểm tra phần tử có tồn tại trong tập hợp

```shell
SISMEMBER <set_name> <member_to_check>
```

6. Lấy ra "n" phần tử ngẫu nhiên

```shell
SRANDMEMBER <set_name> <count>
```

7. Lấy ra các giá trị chung giữa 1 tập hợp và các tập hợp khác

```shell
SINTER <set_name_to_compare> <set_name_1> <set_name_2>
```

8. Lấy ra các giá trị khác nhau giữa 1 tập hợp và các tập hợp khác

```shell
SDIFF <set_name_to_compare> <set_name_1> <set_name_2>
```
