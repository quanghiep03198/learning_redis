![logo](./images/redis-logo.png)

# Part 2 - Redis List

### Redis list là gì

> **Redis list** là 1 cặp key và value là 1 list (danh sách)

### Ứng dụng sủ dụng

- Sử dụng như một messages queue
- Xử lý vấn đề tồn kho trong E-commerce
- ... etc.

### Các lệnh phổ biến

**1. Thêm phần tử vào list**
_Theo chiều từ trái qua_

```shell
LPUSH <list_name> <elm_1> <elm_2> ...
```

_Theo chiều từ phải qua_

```shell
RPUSH <list_name> <elm_1> <elm_2> ...
```

**2. Xóa phần tử trong list**

_Theo chiều từ trái qua_

```shell
LPOP <list_name> <del_count>
```

_Theo chiều từ phải qua_

```shell
RPOP <list_name> <del_count>
```

**3. Lấy độ dài của list**

```shell
LLEN <list_name>
```

**4. Lấy ra giá trị các phần tử trong list**

```shell
LRANGE <list_name> <start_index> <end_index>
```

**5. Chèn 1 phần tử mới**
_Chèn vào trước 1 phần tử có giá trị = x_

```shell
LINSERT <list_name> BEFORE x
```

_Chèn vào sau 1 phần tử có giá trị = x_

```shell
LINSERT <list_name> AFTER x
```

### Cơ chế block trong Redis List
