![logo](./images/redis-logo.png)

# Part 2 - Redis Hash

### Redis hash là gì

> **Redis hash** là 1 tập các cặp key-value, giống như type Map trong các ngôn ngữ lập trình như Java, C#, Javascript ...

### Ứng dụng sủ dụng

- Giỏ hàng trong E-commerce
- Lưu trữ thông tin cho 1 thực thể
- ... etc.

### Các lệnh phổ biến

**1. Set 1 giá trị cho key**

```shell
HSET <field_1> <value_1> <field_2> <value_2> ...
```

**2. Get value bằng tên tên hash table**

```shell
HGET <hash_name> <field_name>
```

**3. Get đồng thời các giá trị của nhiều fields cùng lúc**

```shell
HMGET <field_1> <field_2> ...
```

**4. Lấy tổng số fields trong hash table**

```shell
HLEN <hash_name>
```

**5. Tăng giá trị lưu trữ của field trong hash table (số nguyên) lên "n" đơn vị**

```shell
HINCRBY <hash_name> <field_name> n
```

**6. Giảm giá trị lưu trữ của 1 trường trong hash table (số nguyên) với 1 đơn vị**

```shell
HDECRBY <hash_name> <field_name> n
```

**7. Lấy tất cả các giá trị trong hash table**

```shell
HVALS <hash_name>
```

**8. Lấy tất cả các fields**

```shell
HKEYS <hash_name>
```

**9. Kiểm tra 1 field có tồn tại trong 1 hash table**

```shell
HEXISTS <hash_name> <field_to_check>
```
