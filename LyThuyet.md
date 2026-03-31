# Toán tử trong Python

Toán tử (operator) là ký hiệu dùng để **thực hiện phép tính hoặc so sánh** trên các giá trị (gọi là toán hạng — operand).

---

## 1. Toán tử số học (Arithmetic Operators)

Dùng để tính toán với số, giống như toán học thông thường.

| Toán tử | Ý nghĩa | Ví dụ | Kết quả |
|---------|---------|-------|---------|
| `+` | Cộng | `5 + 3` | `8` |
| `-` | Trừ | `5 - 3` | `2` |
| `*` | Nhân | `5 * 3` | `15` |
| `/` | Chia (kết quả thực) | `7 / 2` | `3.5` |
| `//` | Chia lấy phần nguyên | `7 // 2` | `3` |
| `%` | Chia lấy phần dư | `7 % 2` | `1` |
| `**` | Lũy thừa | `2 ** 3` | `8` |

```python
a = 10
b = 3

print(a + b)   # 13
print(a - b)   # 7
print(a * b)   # 30
print(a / b)   # 3.3333...
print(a // b)  # 3  (bỏ phần thập phân)
print(a % b)   # 1  (10 = 3×3 + 1, dư là 1)
print(a ** b)  # 1000  (10^3)
```

> **Lưu ý:** `%` (modulo) rất hữu ích để kiểm tra số chẵn/lẻ: `n % 2 == 0` nghĩa là n chẵn.

---

## 2. Toán tử so sánh (Comparison Operators)

Dùng để **so sánh hai giá trị**, kết quả luôn là `True` (đúng) hoặc `False` (sai).

| Toán tử | Ý nghĩa | Ví dụ | Kết quả |
|---------|---------|-------|---------|
| `==` | Bằng nhau | `5 == 5` | `True` |
| `!=` | Khác nhau | `5 != 3` | `True` |
| `>` | Lớn hơn | `5 > 3` | `True` |
| `<` | Nhỏ hơn | `5 < 3` | `False` |
| `>=` | Lớn hơn hoặc bằng | `5 >= 5` | `True` |
| `<=` | Nhỏ hơn hoặc bằng | `4 <= 5` | `True` |

```python
x = 10
y = 20

print(x == y)   # False
print(x != y)   # True
print(x < y)    # True
print(x >= 10)  # True
```

> **Chú ý phân biệt:** `=` là **gán giá trị** (x = 5), còn `==` là **so sánh bằng** (x == 5).

---

## 3. Toán tử logic (Logical Operators)

Dùng để **kết hợp nhiều điều kiện** lại với nhau.

| Toán tử | Ý nghĩa | Kết quả |
|---------|---------|---------|
| `and` | VÀ — cả hai điều kiện phải đúng | `True and True` → `True` |
| `or` | HOẶC — chỉ cần một điều kiện đúng | `True or False` → `True` |
| `not` | PHỦ ĐỊNH — đảo ngược kết quả | `not True` → `False` |

### Bảng chân trị (Truth Table)

| A | B | A and B | A or B | not A |
|---|---|---------|--------|-------|
| True | True | True | True | False |
| True | False | False | True | False |
| False | True | False | True | True |
| False | False | False | False | True |

```python
tuoi = 20
co_the_cao = True

# and: cả hai phải đúng
if tuoi >= 18 and co_the_cao:
    print("Được tham gia")   # In ra vì cả hai đều True

# or: chỉ cần một đúng
diem_toan = 5
diem_van = 8
if diem_toan >= 7 or diem_van >= 7:
    print("Đạt ít nhất một môn")   # In ra vì diem_van >= 7

# not: phủ định
dang_mua = False
if not dang_mua:
    print("Trời không mưa")   # In ra
```

---

## 4. Toán tử gán (Assignment Operators)

Dùng để **gán và cập nhật giá trị** cho biến một cách ngắn gọn.

| Toán tử | Tương đương | Ý nghĩa |
|---------|-------------|---------|
| `=` | — | Gán giá trị |
| `+=` | `x = x + n` | Cộng rồi gán |
| `-=` | `x = x - n` | Trừ rồi gán |
| `*=` | `x = x * n` | Nhân rồi gán |
| `/=` | `x = x / n` | Chia rồi gán |
| `//=` | `x = x // n` | Chia nguyên rồi gán |
| `%=` | `x = x % n` | Lấy dư rồi gán |
| `**=` | `x = x ** n` | Lũy thừa rồi gán |

```python
diem = 5

diem += 2    # diem = diem + 2  →  diem = 7
diem -= 1    # diem = diem - 1  →  diem = 6
diem *= 2    # diem = diem * 2  →  diem = 12
print(diem)  # 12
```

---

## 5. Thứ tự ưu tiên toán tử

Python tính toán theo thứ tự ưu tiên (giống toán học). Từ cao xuống thấp:

1. `**` (lũy thừa)
2. `*`, `/`, `//`, `%` (nhân, chia)
3. `+`, `-` (cộng, trừ)
4. `==`, `!=`, `>`, `<`, `>=`, `<=` (so sánh)
5. `not`
6. `and`
7. `or`

```python
# Không dùng ngoặc
result = 2 + 3 * 4   # 3*4 = 12 trước, rồi 2+12 = 14

# Dùng ngoặc để rõ ràng hơn
result = (2 + 3) * 4  # 2+3 = 5 trước, rồi 5*4 = 20
```

> **Lời khuyên:** Khi không chắc thứ tự, hãy dùng **dấu ngoặc `()`** để chắc chắn và dễ đọc hơn.

---

# Câu lệnh điều kiện trong Python

Câu lệnh điều kiện cho phép chương trình **đưa ra quyết định**: thực thi đoạn code này hay đoạn code kia, tùy thuộc vào điều kiện có đúng hay không.

---

## 1. Câu lệnh `if`

Cú pháp đơn giản nhất: **nếu điều kiện đúng thì làm gì đó**.

```
if <điều kiện>:
    <khối lệnh thực thi khi điều kiện đúng>
```

```python
diem = 8

if diem >= 5:
    print("Đậu môn học")   # In ra vì 8 >= 5 là True
```

> **Quan trọng:** Python dùng **thụt lề (indent)** — thường là 4 dấu cách — để xác định khối lệnh thuộc về `if`. Không dùng `{}` như C/Java.

---

## 2. Câu lệnh `if - else`

**Nếu điều kiện đúng** thì làm việc A, **ngược lại** thì làm việc B.

```
if <điều kiện>:
    <làm A>
else:
    <làm B>
```

```python
diem = 4

if diem >= 5:
    print("Đậu môn học")
else:
    print("Rớt môn học")   # In ra vì 4 >= 5 là False
```

---

## 3. Câu lệnh `if - elif - else`

Dùng khi có **nhiều trường hợp** cần xét. `elif` là viết tắt của "else if" (nếu không thì nếu...).

```
if <điều kiện 1>:
    <làm A>
elif <điều kiện 2>:
    <làm B>
elif <điều kiện 3>:
    <làm C>
else:
    <làm D nếu không có điều kiện nào đúng>
```

```python
diem = 75

if diem >= 90:
    xep_loai = "Xuất sắc"
elif diem >= 80:
    xep_loai = "Giỏi"
elif diem >= 65:
    xep_loai = "Khá"
elif diem >= 50:
    xep_loai = "Trung bình"
else:
    xep_loai = "Yếu"

print(f"Xếp loại: {xep_loai}")   # Xếp loại: Khá
```

> **Lưu ý:** Python kiểm tra từ trên xuống, gặp điều kiện đúng đầu tiên thì thực thi và **bỏ qua các `elif`/`else` còn lại**.

---

## 4. Điều kiện lồng nhau (Nested if)

Có thể đặt `if` bên trong `if` để kiểm tra điều kiện phức tạp hơn.

```python
tuoi = 20
co_cmnd = True

if tuoi >= 18:
    if co_cmnd:
        print("Được vào")
    else:
        print("Cần xuất trình CMND")
else:
    print("Chưa đủ tuổi")
```

> Khi điều kiện lồng quá sâu, nên cân nhắc dùng `and`/`or` để gộp lại cho gọn hơn:
> ```python
> if tuoi >= 18 and co_cmnd:
>     print("Được vào")
> ```

---

## 5. Toán tử ba ngôi (Ternary / Conditional Expression)

Cách viết `if-else` **trên một dòng**, dùng cho các trường hợp đơn giản.

```
<giá trị nếu đúng>  if  <điều kiện>  else  <giá trị nếu sai>
```

```python
diem = 7

ket_qua = "Đậu" if diem >= 5 else "Rớt"
print(ket_qua)   # Đậu

# Tương đương với:
# if diem >= 5:
#     ket_qua = "Đậu"
# else:
#     ket_qua = "Rớt"
```

---

## 6. Câu lệnh `match - case` (Python 3.10+)

Tương tự `switch-case` trong C/Java, dùng khi so sánh một biến với **nhiều giá trị cụ thể**.

```python
ngay = 2

match ngay:
    case 1:
        print("Thứ Hai")
    case 2:
        print("Thứ Ba")    # In ra
    case 3:
        print("Thứ Tư")
    case 6 | 7:            # Dùng | để ghép nhiều case
        print("Cuối tuần")
    case _:                # _ là trường hợp mặc định (như else)
        print("Không hợp lệ")
```

---

## Tóm tắt nhanh

| Cú pháp | Dùng khi |
|---------|---------|
| `if` | Chỉ cần xét một điều kiện |
| `if - else` | Có hai trường hợp: đúng hoặc sai |
| `if - elif - else` | Có nhiều trường hợp cần phân loại |
| Lồng `if` | Điều kiện phụ thuộc vào điều kiện khác |
| Ternary `A if cond else B` | Gán giá trị đơn giản trong một dòng |
| `match - case` | So sánh một biến với nhiều hằng giá trị (Python 3.10+) |


# Vòng lặp trong Python

Python có các loại vòng lặp chính sau: `for`, `while` (Python không có `do-while` như C/Java nhưng có cách mô phỏng). Dưới đây là hướng dẫn chi tiết.

---

## 1. Vòng lặp `for`

Dùng để **duyệt qua một iterable** (list, string, range, tuple, dict,...).

```python
# Duyệt qua list
fruits = ["táo", "chuối", "cam"]
for fruit in fruits:
    print(fruit)

# Duyệt qua range
for i in range(5):        # 0, 1, 2, 3, 4
    print(i)

for i in range(1, 6):     # 1, 2, 3, 4, 5
    print(i)

for i in range(0, 10, 2): # 0, 2, 4, 6, 8 (bước nhảy 2)
    print(i)

# Duyệt qua string
for ch in "Python":
    print(ch)

# Duyệt qua dict
person = {"name": "An", "age": 20}
for key, value in person.items():
    print(f"{key}: {value}")
```

### `enumerate` — lấy cả index lẫn giá trị

```python
fruits = ["táo", "chuối", "cam"]
for i, fruit in enumerate(fruits):
    print(f"{i}: {fruit}")
# 0: táo
# 1: chuối
# 2: cam
```

---

## 2. Vòng lặp `while`

Lặp **khi điều kiện còn đúng**.

```python
count = 0
while count < 5:
    print(f"count = {count}")
    count += 1
```

### Vòng lặp vô hạn có kiểm soát

```python
while True:
    user_input = input("Nhập 'q' để thoát: ")
    if user_input == 'q':
        break
    print(f"Bạn nhập: {user_input}")
```

---

## 3. Mô phỏng `do-while`

Python không có `do-while`, nhưng ta dùng `while True` + `break` ở cuối:

```python
# Chạy ít nhất 1 lần, sau đó kiểm tra điều kiện
while True:
    num = int(input("Nhập số dương: "))
    if num > 0:
        break
    print("Số phải lớn hơn 0, thử lại!")
```

> Đây tương đương với `do { ... } while(điều kiện)` trong C/Java.

---

## 4. `break`, `continue`, `else`

### `break` — thoát khỏi vòng lặp

```python
for i in range(10):
    if i == 5:
        break
    print(i)  # In 0, 1, 2, 3, 4
```

### `continue` — bỏ qua iteration hiện tại

```python
for i in range(10):
    if i % 2 == 0:
        continue
    print(i)  # In 1, 3, 5, 7, 9
```

### `else` trong vòng lặp — chạy khi loop kết thúc bình thường (không bị `break`)

```python
for i in range(5):
    print(i)
else:
    print("Vòng lặp kết thúc!")  # Sẽ chạy

for i in range(5):
    if i == 3:
        break
else:
    print("Không in ra vì bị break!")  # Sẽ KHÔNG chạy
```

---

## 5. Vòng lặp lồng nhau (Nested Loop)

```python
for i in range(1, 4):
    for j in range(1, 4):
        print(f"{i} x {j} = {i*j}")
```

---

## 6. List Comprehension — vòng lặp rút gọn

```python
# Bình thường
squares = []
for i in range(10):
    squares.append(i ** 2)

# Rút gọn bằng comprehension
squares = [i ** 2 for i in range(10)]

# Có điều kiện
even_squares = [i ** 2 for i in range(10) if i % 2 == 0]
```

---

## Tóm tắt nhanh

| Loại | Dùng khi |
|---|---|
| `for` | Biết trước số lần lặp hoặc duyệt iterable |
| `while` | Điều kiện dừng chưa biết trước |
| `while True` + `break` | Mô phỏng `do-while`, chạy ít nhất 1 lần |
| List comprehension | Tạo list ngắn gọn từ vòng lặp |

