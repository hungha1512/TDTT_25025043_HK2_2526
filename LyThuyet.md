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


# Hàm (Function) trong Python

Hàm là một **khối lệnh được đặt tên**, dùng để thực hiện một nhiệm vụ cụ thể. Thay vì viết lại code nhiều lần, ta định nghĩa hàm một lần và gọi lại bất kỳ lúc nào.

---

## 1. Định nghĩa và gọi hàm

```
def tên_hàm(tham_số_1, tham_số_2, ...):
    <khối lệnh>
    return <giá trị>   # tuỳ chọn
```

```python
def chao(ten):
    print(f"Xin chào, {ten}!")

chao("An")   # Xin chào, An!
```

> **Lưu ý:** Hàm không có `return` sẽ tự động trả về `None`.

---

## 2. Tham số và đối số

| Khái niệm | Ý nghĩa |
|-----------|---------|
| **Tham số (parameter)** | Biến được khai báo trong `def` |
| **Đối số (argument)** | Giá trị thực tế truyền vào khi gọi hàm |

```python
def cong(a, b):       # a, b là tham số
    return a + b

ket_qua = cong(3, 5)  # 3, 5 là đối số  →  ket_qua = 8
```

### Tham số mặc định (Default parameter)

```python
def luy_thua(co_so, so_mu=2):   # so_mu mặc định là 2
    return co_so ** so_mu

print(luy_thua(3))     # 9   (3^2)
print(luy_thua(3, 3))  # 27  (3^3)
```

---

## 3. Câu lệnh `return`

- Trả về giá trị cho nơi gọi hàm và **kết thúc hàm ngay lập tức**.
- Có thể trả về **nhiều giá trị** cùng lúc (dưới dạng tuple).

```python
def tinh_chia(a, b):
    thuong = a // b
    du = a % b
    return thuong, du   # trả về tuple (thuong, du)

q, r = tinh_chia(10, 3)
print(q, r)   # 3  1
```

---

## 4. Type Hint (Gợi ý kiểu dữ liệu)

Python cho phép ghi chú kiểu dữ liệu của tham số và giá trị trả về — giúp code dễ đọc hơn, **không bắt buộc**.

```python
from typing import Tuple

def max_of_two(a: int, b: int) -> int:
    return a if a > b else b

def swap(a: int, b: int) -> Tuple[int, int]:
    return b, a
```

| Cú pháp | Ý nghĩa |
|---------|---------|
| `a: int` | Tham số `a` có kiểu `int` |
| `-> int` | Hàm trả về kiểu `int` |
| `-> Tuple[int, int]` | Hàm trả về tuple gồm 2 số nguyên |
| `-> bool` | Hàm trả về `True` hoặc `False` |

---

## 5. Phạm vi biến (Scope)

- Biến khai báo **bên trong hàm** (local) chỉ tồn tại trong hàm đó.
- Biến khai báo **ngoài hàm** (global) có thể đọc bên trong hàm, nhưng muốn thay đổi phải dùng từ khoá `global`.

```python
x = 10   # biến global

def ham():
    y = 5      # biến local, chỉ sống trong ham()
    print(x)   # đọc được biến global
    print(y)

ham()
# print(y)  # Lỗi! y không tồn tại ngoài ham()
```

---

## 6. Hàm và một số bài toán thường gặp

### 6.1. Tìm số lớn hơn trong hai số

```python
def max_of_two(a: int, b: int) -> int:
    return a if a > b else b
```

### 6.2. Hoán đổi hai biến

```python
def swap(a: int, b: int):
    return b, a   # trả về tuple đã đổi chỗ

a, b = swap(3, 7)
print(a, b)   # 7  3
```

### 6.3. Kiểm tra số nguyên tố

Số nguyên tố là số lớn hơn 1, **chỉ chia hết cho 1 và chính nó**.

```python
def is_prime(n: int) -> bool:
    if n < 2:
        return False
    for i in range(2, int(n ** 0.5) + 1):   # chỉ cần kiểm tra đến căn bậc hai
        if n % i == 0:
            return False
    return True

print(is_prime(7))   # True
print(is_prime(9))   # False  (9 = 3×3)
```

> **Mẹo tối ưu:** Chỉ cần kiểm tra đến `√n` vì nếu `n` có ước > `√n`, thì ước còn lại phải < `√n` và đã được kiểm tra rồi.

### 6.4. Kiểm tra số hoàn hảo

Số hoàn hảo là số bằng **tổng tất cả ước số thực sự** (ước số trừ chính nó). Ví dụ: 6 = 1 + 2 + 3.

```python
def is_perfect(n: int) -> bool:
    if n < 2:
        return False
    tong = sum(i for i in range(1, n) if n % i == 0)
    return tong == n

print(is_perfect(6))    # True   (1+2+3 = 6)
print(is_perfect(28))   # True   (1+2+4+7+14 = 28)
print(is_perfect(12))   # False
```

### 6.5. Tính giai thừa

```python
def factorial(n: int) -> int:
    result = 1
    for i in range(2, n + 1):
        result *= i
    return result

print(factorial(5))   # 120  (5! = 1×2×3×4×5)
```

### 6.6. Tìm kiếm trong list

```python
def tim_vi_tri(lst: list, k: int) -> int:
    for i in range(len(lst)):
        if lst[i] == k:
            return i   # trả về vị trí đầu tiên tìm thấy
    return -1          # không tìm thấy

print(tim_vi_tri([3, 7, 2, 7], 7))   # 1
print(tim_vi_tri([3, 7, 2, 7], 9))   # -1
```

### 6.7. Tổng các chữ số

```python
def digit_sum(n: int) -> int:
    tong = 0
    n = abs(n)          # xử lý số âm
    while n > 0:
        tong += n % 10  # lấy chữ số cuối
        n //= 10        # bỏ chữ số cuối
    return tong

print(digit_sum(1234))   # 10  (1+2+3+4)
```

### 6.8. Khoảng cách Hamming

Khoảng cách Hamming giữa hai số nguyên = **số vị trí bit khác nhau** trong biểu diễn nhị phân của chúng.

```python
def hamming_distance(x: int, y: int) -> int:
    xor = x ^ y         # XOR: bit = 1 ở những vị trí khác nhau
    dem = 0
    while xor > 0:
        dem += xor & 1  # kiểm tra bit cuối
        xor >>= 1       # dịch phải 1 bit
    return dem

# Hoặc ngắn gọn hơn:
def hamming_distance(x: int, y: int) -> int:
    return bin(x ^ y).count('1')

print(hamming_distance(1, 4))   # 2  (001 XOR 100 = 101 → có 2 bit 1)
```

> **Giải thích phép tính bit:**
> - `^` (XOR): kết quả là `1` tại những vị trí hai bit **khác nhau**.
> - `bin(n)` chuyển số nguyên sang chuỗi nhị phân, ví dụ `bin(5)` → `'0b101'`.
> - `.count('1')` đếm số bit `1` trong chuỗi.

### 6.9. Kiểm tra hai từ đẳng cấu (Isomorphic)

Hai từ đẳng cấu nếu có thể ánh xạ 1-1 các ký tự tương ứng.

```python
def is_isomorphic(a: str, b: str) -> bool:
    if len(a) != len(b):
        return False
    map_ab = {}   # ánh xạ từ a sang b
    map_ba = {}   # ánh xạ từ b sang a (để đảm bảo 1-1)
    for ca, cb in zip(a, b):
        if ca in map_ab and map_ab[ca] != cb:
            return False
        if cb in map_ba and map_ba[cb] != ca:
            return False
        map_ab[ca] = cb
        map_ba[cb] = ca
    return True

print(is_isomorphic("abca", "zbxz"))   # True
print(is_isomorphic("ab", "aa"))       # False
```

### 6.10. Kiểm tra tam giác vuông

Ba cạnh a, b, c tạo thành tam giác vuông nếu bình phương cạnh lớn nhất bằng tổng bình phương hai cạnh còn lại (định lý Pythagore).

```python
def is_right_triangle(a: float, b: float, c: float) -> bool:
    canh = sorted([a, b, c])   # sắp xếp tăng dần
    return canh[2] ** 2 == canh[0] ** 2 + canh[1] ** 2

print(is_right_triangle(3, 4, 5))    # True   (9 + 16 = 25)
print(is_right_triangle(1, 2, 3))   # False
```

---

## 7. Một số hàm và kỹ thuật hữu ích

### `abs()` — giá trị tuyệt đối
```python
print(abs(-5))   # 5
```

### `round()` — làm tròn số
```python
print(round(3.14159, 2))   # 3.14
```

### `sorted()` — sắp xếp iterable, trả về list mới
```python
print(sorted([3, 1, 2]))      # [1, 2, 3]
print(sorted([3, 1, 2], reverse=True))  # [3, 2, 1]
```

### `zip()` — ghép các iterable lại từng cặp
```python
a = [1, 2, 3]
b = ['a', 'b', 'c']
for x, y in zip(a, b):
    print(x, y)   # 1 a / 2 b / 3 c
```

### Phép toán bit (Bitwise Operators)

| Toán tử | Ý nghĩa | Ví dụ |
|---------|---------|-------|
| `&` | AND bit | `5 & 3` → `1` |
| `\|` | OR bit | `5 \| 3` → `7` |
| `^` | XOR bit | `5 ^ 3` → `6` |
| `~` | NOT bit | `~5` → `-6` |
| `<<` | Dịch trái | `1 << 2` → `4` |
| `>>` | Dịch phải | `8 >> 1` → `4` |

```python
# XOR hữu ích để tìm bit khác nhau
print(bin(5))      # '0b101'
print(bin(3))      # '0b011'
print(bin(5 ^ 3))  # '0b110'  → vị trí bit khác nhau
```

---

## Tóm tắt nhanh

| Khái niệm | Cú pháp |
|-----------|---------|
| Định nghĩa hàm | `def tên(tham_số):` |
| Trả về giá trị | `return giá_trị` |
| Trả về nhiều giá trị | `return a, b` → nhận bằng `x, y = hàm()` |
| Type hint | `def f(a: int) -> bool:` |
| Tham số mặc định | `def f(a, b=10):` |
| Import kiểu | `from typing import Tuple, List` |


# List, Tuple, Dict trong Python

Ba cấu trúc dữ liệu cơ bản nhất là `list`, `tuple`, `dict`. Chúng đều là kiểu dữ liệu *iterable* và thường xuyên xuất hiện trong bài tập.

---

## 1. List (Danh sách)

**List** là dãy phần tử *có thứ tự* và *có thể thay đổi* (mutable).

### Cách tạo list

```python
nums = [1, 2, 3, 4]
words = ["python", "java", "c++"]
mix = [1, "a", 3.5, True]
empty = []
```

### Truy cập phần tử và cắt (slicing)

```python
nums = [10, 20, 30, 40, 50]
print(nums[0])    # 10
print(nums[-1])   # 50 (phần tử cuối)

print(nums[1:4])  # [20, 30, 40]
print(nums[:3])   # [10, 20, 30]
print(nums[::2])  # [10, 30, 50]
```

### Thao tác thường dùng

```python
nums = [1, 2, 3]
nums.append(4)       # [1, 2, 3, 4]
nums.insert(1, 99)   # [1, 99, 2, 3, 4]
nums.remove(99)      # xoá phần tử đầu tiên có giá trị 99
nums.pop()           # xoá phần tử cuối
nums.extend([5, 6])  # nối thêm list
```

### Duyệt list

```python
nums = [3, 5, 7]
for x in nums:
    print(x)

for i, x in enumerate(nums):
    print(i, x)   # in ra cả vị trí và giá trị
```

### Một số hàm hay dùng

```python
nums = [5, 1, 9]
print(len(nums))   # 3
print(sum(nums))   # 15
print(max(nums))   # 9
print(min(nums))   # 1

nums.sort()        # sắp xếp tăng dần, thay đổi list gốc
nums.reverse()     # đảo ngược list
```

> **Lưu ý:** Khi cần copy list để không ảnh hưởng list gốc, dùng `nums.copy()` hoặc `nums[:]`.

---

## 2. Tuple (Bộ)

**Tuple** là dãy phần tử *có thứ tự* nhưng **không thay đổi được** (immutable).

### Cách tạo tuple

```python
t = (1, 2, 3)
t2 = ("a", "b", "c")
t3 = ()
t4 = (5,)   # tuple 1 phần tử phải có dấu phẩy
```

### Truy cập tuple

```python
t = (10, 20, 30)
print(t[0])    # 10
print(t[-1])   # 30
print(t[1:])   # (20, 30)
```

### Dùng tuple để trả về nhiều giá trị

```python
def chia(a, b):
    return a // b, a % b

q, r = chia(10, 3)
print(q, r)   # 3 1
```

> **Khi nào dùng tuple?** Khi dữ liệu *không cần thay đổi*, giúp an toàn và tiết kiệm bộ nhớ hơn list.

---

## 3. Dict (Từ điển)

**Dict** là tập hợp các cặp `key: value`. *Không có thứ tự vị trí theo chỉ số* (nhưng từ Python 3.7+ dict giữ thứ tự thêm vào).

### Cách tạo dict

```python
student = {"name": "An", "age": 20}
scores = {1: "A", 2: "B"}
empty = {}
```

### Truy cập và cập nhật

```python
student = {"name": "An", "age": 20}
print(student["name"])    # An

student["age"] = 21       # cập nhật
student["city"] = "HCM"  # thêm mới
```

### Duyệt dict

```python
student = {"name": "An", "age": 20}

for key in student:
    print(key, student[key])

for key, value in student.items():
    print(key, value)
```

### Một số thao tác phổ biến

```python
student = {"name": "An", "age": 20}

print(student.get("name"))       # An (an toàn hơn [] nếu key không tồn tại)
print("age" in student)          # True

student.pop("age")               # xoá key age
student.update({"grade": "A"})  # thêm nhiều key
```

### Đếm số lần xuất hiện bằng dict

```python
nums = [1, 2, 1, 3, 2, 1]
count = {}
for x in nums:
    count[x] = count.get(x, 0) + 1

print(count)   # {1: 3, 2: 2, 3: 1}
```

---

## 4. Set (Tập hợp)

**Set** là tập hợp các phần tử *không trùng nhau* và *không có thứ tự*.

### Cách tạo set

```python
nums = {1, 2, 3}
chars = set(["a", "b", "c"])
empty = set()  # không dùng {} vì đó là dict rỗng
```

### Thao tác cơ bản

```python
nums = {1, 2, 3}
nums.add(4)          # thêm phần tử
nums.remove(2)       # xoá phần tử (lỗi nếu không tồn tại)
nums.discard(10)     # xoá an toàn, không lỗi
```

### Toán tử tập hợp

```python
a = {1, 2, 3}
b = {3, 4, 5}

print(a | b)  # hợp: {1, 2, 3, 4, 5}
print(a & b)  # giao: {3}
print(a - b)  # hiệu: {1, 2}
print(a ^ b)  # đối xứng: {1, 2, 4, 5}
```

> **Khi nào dùng set?** Khi cần loại bỏ trùng lặp, kiểm tra tồn tại nhanh, hoặc làm các phép toán tập hợp.

---

## 5. So sánh nhanh

| Kiểu | Có thứ tự | Thay đổi được | Truy cập | Ví dụ |
|------|-----------|---------------|----------|-------|
| List | Có | Có | theo chỉ số | `[1, 2, 3]` |
| Tuple | Có | Không | theo chỉ số | `(1, 2, 3)` |
| Dict | Theo key | Có | theo key | `{ "a": 1 }` |
| Set | Không | Có | theo phần tử | `{1, 2, 3}` |

> **Mẹo học nhanh:**
> - List: dùng khi cần thay đổi dữ liệu (thêm, xoá, sửa).
> - Tuple: dùng khi dữ liệu cố định (toạ độ, trả về nhiều giá trị).
> - Dict: dùng khi cần tra cứu theo khóa (key) nhanh.
> - Set: dùng khi cần lọc trùng và kiểm tra tồn tại nhanh.

