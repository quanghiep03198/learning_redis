![logo](./images/redis-logo.png)

# Part 5 - Redis Zset

### Redis Zset là gì

> **Redis Zset** là 1 bộ sưu tập các cặp key và value, trong đó các giá trị là duy nhất, không trùng lặp và **CÓ** thứ tự.

### Ứng dụng sử dụng

- Tổng hợp sản phẩm bán chạy
- Lượt xem và theo dõi

### Các lệnh phổ biến

**1. Thêm phần tử vào trong bộ sưu tập (tạo mới nếu chưa tồn tại)**

```shell
ZADD <set_name> <score_1> <member_1> <score_2> <member_2> ... <score_n> <member_n>
```

**2. Xóa 1 hoặc nhiều phần tử vào trong bộ sưu tập (tạo mới nếu chưa tồn tại)**

```shell
ZREM <set_name> <member_1> ... <member_n>
```

**3. Lấy ra các phần tử trong bộ sưu tập**

_Theo chiều giảm dần_

```shell
ZREVRANGE <set_name> <start_index> <end_index>
```

_Theo chiều tăng dần_

```shell
ZRANGE <set_name> <start_index>
```

_Bổ sung:_

- Nếu muốn hiển thị thêm "score" của "member" trong bộ sưu tập khi thêm option `WITHSCORES` vào cuối
- Nếu muốn lấy toàn bộ members của bộ sưu tập, thì `start_index = 0` và `end_index = -1`

**4. Tăng giá trị của 1 member trong bộ sưu tập lên "n"**

```shell
ZINCRBY <set_name> <n> <member_to_increase>
```

**5. Giảm giá trị của 1 member trong bộ sưu tập "n" đơn vị**

```shell
ZDECRBY <set_name> <n> <member_to_decrease>
```
