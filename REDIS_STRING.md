![logo](./images/redis-logo.png)

# Part 1 - Redis String 🔥

### 👉 Ứng dụng sủ dụng

- Đối tượng bộ đệm
- Số lượng thông thường
- Khóa phân tán,
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
SET <key_name> <value> NX PX|EX <expire_time>
```

_Trong đó:_

- "NX" (Not Exist) - là thiết lập khóa không tồn tại
- "PX" (milliseconds) - nếu sử dụng "PX expire time sẽ được tính theo milli giây
- "EX" (seconds) - nếu sử dụng "EX expire time sẽ được tính theo giây

**4. Check thời gian sống của 1 key**

```shell
TTL <key_name>
```

**5. Get value bằng tên key**

```shell
GET <key_name>
```

**6. Kiểm tra kiểu mã hóa**

```shell
OBJECT ENCODING <key_name>
```

_Trả về "embedstr" hoặc "raw"_

**7. Kiểm tra key có tổn tại hay không**

```shell
EXISTS <key_name>
```

_Nếu tồn tại sẽ trả về 1, ngược lại nếu không tồn tại sẽ trả về 0_

**8. Lấy tất cả các keys đang tồn tại**

```shell
KEYS <regex_pattern>
```

_Example_ : `KEYS *token*`

**9. Set đồng thời nhiều cặp key-value cùng lúc**

```shell
MSET <key_1> <value_1> <key_2> <value_2> ...
```

**10. Get đồng thời nhiều values cùng lúc**

```shell
MGET <key_1> <key_2> ...
```

**11. Lấy độ dài của giá trị**

```shell
STRLEN <key_name>
```

**12. Tăng giá trị lưu trữ của key (số nguyên) với "n" đơn vị**

```shell
INCR <key_name>
```

**13. Tăng giá trị lưu trữ của key (số nguyên) lên "n" đơn vị**

```shell
INCRBY <key_name> n
```

**14. Giảm giá trị lưu trữ của key (số nguyên) với 1 đơn vị**

```shell
DECR <key_name>
```

**15. Giảm giá trị lưu trữ của key (số nguyên) với "n" đơn vị**

```shell
DECRBY <key_name> n
```

**16. Cắt lấy giá trị của key theo index**

```shell
GETRANGE <key_name> <start_index> <end_index>
```

_Trong đó:_

- (integer) start_index: vị trí bắt đầu lấy
- (integer) end_index: vị trí kết thúc

**17. Đổi tên key**

```shell
RENAMENX <curent_key> <new_key>
```
