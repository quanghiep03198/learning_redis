![logo](./images/redis-logo.png)

# Part 1 - Redis String

### 👉 Redis string là gì

> "**Redis string** là 1 các cặp key-value trong đó value có giá trị string trong redis"

### 👉 Ứng dụng sử dụng

- Đối tượng bộ đệm
- Số lượng thông thường
- Khóa phân tán
- Thông tin phiên được chia sẻ
- ... etc.

### 👉 Các loại mã hóa

- Embed string (embstr) có dung lượng **<= 44MB**
- Raw (raw) có dung lượng **> 44MB**

### 👉 Các lệnh phổ biến

**1. Set 1 giá trị cho key**

```shell
SET <key_name> <value>
```

**2. Set 1 giá trị cho key nếu key chưa tồn tại**

```shell
SETNX <key_name> <value>
```

**3. Set 1 giá trị và thời gian tồn tại cho key**

```shell
SETEX <key_name> <value> <expire_time>
```

_Hoặc_

```shell
SET <key_name> <value> <NX|XX> <PX|EX> <expire_time>
```

_Trong đó:_

- "XX" (Exist) - là thiết lập cho khóa đã tồn tại
- "NX" (Not Exist) - là thiết lập khóa không tồn tại
- "PX" (milliseconds) - nếu sử dụng "PX", expire time sẽ được tính theo milli giây
- "EX" (seconds) - nếu sử dụng "EX", expire time sẽ được tính theo giây

_Example:_

- Set value và expire time cho 1 key chưa tồn tại với thời gian sống là 60s

```shell
SET some_key xxx NX EX 60
```

- Set value và expire time cho key đang tồn tại với thời gian sống là 60000ms (60s)

```shell
SET some_key yyy XX PX 60000
```

**4. Get value bằng tên key**

```shell
GET <key_name>
```

**5. Kiểm tra kiểu mã hóa**

```shell
OBJECT ENCODING <key_name>
```

_Trả về "embedstr" hoặc "raw"_

**6. Set đồng thời nhiều cặp key-value cùng lúc**

```shell
MSET <key_1> <value_1> <key_2> <value_2> ...
```

**7. Get đồng thời nhiều values cùng lúc**

```shell
MGET <key_1> <key_2> ...
```

**8. Lấy độ dài của giá trị**

```shell
STRLEN <key_name>
```

**9. Tăng giá trị lưu trữ của key (số nguyên) với "n" đơn vị**

```shell
INCR <key_name>
```

**10. Tăng giá trị lưu trữ của key (số nguyên) lên "n" đơn vị**

```shell
INCRBY <key_name> n
```

**11. Giảm giá trị lưu trữ của key (số nguyên) với 1 đơn vị**

```shell
DECR <key_name>
```

**12. Giảm giá trị lưu trữ của key (số nguyên) với "n" đơn vị**

```shell
DECRBY <key_name> n
```

**13. Cắt lấy giá trị của key theo index**

```shell
GETRANGE <key_name> <start_index> <end_index>
```

_Trong đó:_

- (integer) start_index: vị trí bắt đầu lấy
- (integer) end_index: vị trí kết thúc
