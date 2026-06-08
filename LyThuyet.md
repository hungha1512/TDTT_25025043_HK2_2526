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

---

# Mảng 2 chiều (2D List) trong Python

Mảng 2 chiều thực chất là **một mảng chứa nhiều mảng** (hay gọi là 1 list chứa một hoặc nhiều list con). Chúng ta thường dùng nó để biểu diễn ma trận hoặc dữ liệu dạng hàng và cột.

---

## 1. Khởi tạo và truy cập mảng 2 chiều

Ta có thể khởi tạo mảng 2 chiều bằng cách viết trên nhiều dòng cho trực quan hoặc trên một dòng.

```python
# Ma trận vuông 3x3
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]   
]

matrix_2 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Truy cập phần tử: matrix[chỉ_số_hàng][chỉ_số_cột]
# Lấy phần tử có giá trị 2 trong list matrix
print(matrix[0][1])      # Kết quả: 2 (hàng 0, cột 1)

# Lấy phần tử có giá trị 7 trong list matrix_2
print(matrix_2[2][0])    # Kết quả: 7 (hàng 2, cột 0)

matrix_3 = [[1, 2, 3, [4, 5, 6, [7, 8, 9]]]]
# Lấy phần tử có giá trị 8 trong list matrix_3
print(matrix_3[0][3][3][1])  # Kết quả: 8
```

---

## 2. Duyệt mảng 2 chiều

Dùng **vòng lặp lồng nhau** để duyệt mảng 2 (hay nhiều) chiều.

### 2.1. Duyệt theo hàng
Duyệt trực tiếp qua từng phần tử hàng, sau đó duyệt từng item trong hàng đó.
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]   
]

# Duyệt theo hàng
for row in matrix:
    for item in row:
        print(item, end=" ")
    print()
# Kết quả in ra:
# 1 2 3 
# 4 5 6 
# 7 8 9 
```

### 2.2. Duyệt theo chỉ số (đối với mảng đồng nhất độ dài)
Duyệt qua số lượng hàng và cột của ma trận.
```python
# Duyệt theo chỉ số
rows = len(matrix)
cols = len(matrix[0])
for i in range(rows):
    for j in range(cols):
        print(f"Phần tử tại [{i}][{j}] của matrix là {matrix[i][j]}")
```

### 2.3. Duyệt theo chỉ số với mảng con không đồng nhất độ dài
Khi các hàng có số cột khác nhau, ta phải dùng `len(matrix_2[i])` để lấy số cột riêng của từng hàng.
```python
matrix_2 = [
    [1, 2, 3, 11, 12],
    [4, 5, 6, 10],
    [7, 8, 9]   
]

for i in range(len(matrix_2)):
    for j in range(len(matrix_2[i])):
        print(f"Phần tử tại [{i}][{j}] của matrix_2 là {matrix_2[i][j]}")
```

---

## 3. Các thao tác hay gặp trên mảng 2 chiều

### 3.1. Làm phẳng mảng (Flattening)
Chuyển từ mảng 2 chiều thành mảng 1 chiều. Có 3 cách thường dùng:

```python
matrix = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

# Cách 1: Làm phẳng bằng vòng lặp và append()
result = []
for row in matrix:
    for item in row:
        result.append(item)
print(result)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Cách 2: Làm phẳng bằng vòng lặp và extend()
result_2 = []
for row in matrix:
    result_2.extend(row)
print(result_2)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]

# Cách 3: Làm phẳng bằng List Comprehension (Ngắn gọn nhất)
result_3 = [item for row in matrix for item in row]
print(result_3)  # [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

### 3.2. Tính tổng hàng
```python
matrix = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]   
]

# Cách 1: Duyệt trực tiếp qua từng hàng để tính tổng
count = 1
for row in matrix:
    sum_val = 0
    for item in row:
        sum_val += item
    print(f"Tong cua hang {count} la: {sum_val}")
    count += 1

# Cách 2: Viết hàm tính tổng của hàng thứ k (chỉ số 1-based)
def tong_hang(matrix, k):
    sum_val = 0
    for i in range(len(matrix[k-1])):
        sum_val += matrix[k-1][i]
    return sum_val

print(tong_hang(matrix, 3))  # Kết quả: 24 (Tổng hàng 3: 7 + 8 + 9)
```

### 3.3. Tính tổng cột
Duyệt qua chỉ số hàng để tính tổng tại một vị trí cột cố định `k` (chỉ số 0-based).
```python
def tong_cot(matrix, k):
    sum_column = 0
    # Kiểm tra tính hợp lệ của chỉ số cột k
    if k < 0 or k >= len(matrix):
        return None
    for i in range(len(matrix)):
        sum_column += matrix[i][k]
    return sum_column

print(tong_cot(matrix, 2))  # Kết quả: 18 (Tổng cột 2: 3 + 6 + 9)
```

### 3.4. Lưu ý trong ma trận vuông
Đối với ma trận vuông cấp n x n:
- **Đường chéo chính:** Các phần tử có chỉ số hàng = chỉ số cột (`i == j`).
- **Đường chéo phụ:** Các phần tử có chỉ số thỏa mãn `i + j == n - 1` (với n là kích thước ma trận vuông).

---

# Thuật toán Tìm kiếm (Searching)

Dùng để tìm vị trí (chỉ số) của một phần tử mục tiêu trong danh sách.

## 1. Tìm kiếm tuyến tính (Linear Search)
Duyệt lần lượt qua từng phần tử từ đầu đến cuối cho đến khi tìm thấy mục tiêu thì dừng lại. Dùng cho danh sách **chưa sắp xếp**.

```python
# Tìm kiếm tuyến tính, dùng cho danh sách chưa sắp xếp
arr = [2, 4, 5, 3, 1, 7, 9, 10]

def linear_search(arr, tar):
    for i in range(len(arr)):
        if arr[i] == tar:
            return i
    return -1

print(linear_search(arr, 7))  # Kết quả: 5
```
*Độ phức tạp thời gian:* O(n)

## 2. Tìm kiếm nhị phân (Binary Search)
Chỉ áp dụng cho danh sách **đã sắp xếp**. Nguyên lý: Luôn chia đôi phạm vi tìm kiếm ở mỗi bước.

```python
# Tìm kiếm nhị phân, chỉ dùng cho danh sách đã sắp xếp
arr = [1, 2, 3, 4, 4, 5, 6, 7, 8, 8, 9, 10]
```

### Cách 1: Tìm kiếm nhị phân bằng Đệ quy (Recursive)
```python
def binary_search(arr, tar, left, right):
    # Kiểm tra left và right có hợp lệ không
    if left > right:
        return -1
    
    mid = (left + right) // 2
    
    if arr[mid] == tar:
        return mid
    
    if arr[mid] < tar:
        left = mid + 1
    else:
        right = mid - 1
        
    return binary_search(arr, tar, left, right)

print(binary_search(arr, 8, 0, len(arr)-1))  # Kết quả: 8
```

### Cách 2: Tìm kiếm nhị phân dùng vòng lặp `while` (Iterative)
```python
def binary_search_while(arr, tar):
    left, right = 0, len(arr) - 1
    while left <= right:
        mid = (left + right) // 2
        if arr[mid] == tar:
            return mid
        if arr[mid] < tar:
            left = mid + 1
        else: 
            right = mid - 1
    return -1

print(binary_search_while(arr, 8))  # Kết quả: 8
```
*Độ phức tạp thời gian:* O(log n)

---

# Thuật toán Sắp xếp cơ bản (Sorting)

## 1. Sắp xếp nổi bọt (Bubble Sort)
So sánh 2 phần tử kề nhau, nếu sai thứ tự thì hoán đổi. Sau mỗi vòng lặp lớn, phần tử lớn nhất sẽ "nổi" dần về cuối dãy.

```python
arr = [2, 4, 5, 3, 1, 7, 9, 10]
print(f"Mảng trước khi sắp xếp là: {arr}") 

def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(0, len(arr)-i-1):
            if arr[j] > arr[j+1]:
                # Hoán đổi hai phần tử kề nhau
                arr[j], arr[j+1] = arr[j+1], arr[j]
    return arr

print(f"Mảng sau khi sắp xếp là: {bubble_sort(arr)}")            
# Kết quả: [1, 2, 3, 4, 5, 7, 9, 10]
```
*Độ phức tạp thời gian:* O(n^2)

## 2. Sắp xếp lựa chọn (Selection Sort)
Tìm phần tử nhỏ nhất (hoặc lớn nhất) trong đoạn chưa sắp xếp và đưa nó về vị trí đang xét đầu đoạn đó. Thuật toán sắp xếp trực tiếp tại chỗ (in-place).

```python
arr = [2, 4, 5, 3, 1, 7, 9, 10]
print(f"Mảng trước khi sắp xếp là: {arr}")

def selection_sort(arr):
    for i in range(len(arr)):
        min_idx = i
        for j in range(i+1, len(arr)):
            if arr[j] < arr[min_idx]:
                min_idx = j
        # Hoán đổi phần tử nhỏ nhất tìm được với phần tử tại vị trí i
        arr[i], arr[min_idx] = arr[min_idx], arr[i]

selection_sort(arr)
print(f"Mảng sau khi sắp xếp là: {arr}")
# Kết quả: [1, 2, 3, 4, 5, 7, 9, 10]
```
*Độ phức tạp thời gian:* O(n^2)

## 3. Sắp xếp chèn (Insertion Sort)
Xây dựng dãy con đã sắp xếp bằng cách lấy từng phần tử từ dãy chưa sắp xếp và "chèn" vào đúng vị trí của nó trong dãy con đã sắp xếp trước đó.

```python
arr = [2, 4, 5, 3, 1, 7, 9, 10]

def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        # Di chuyển các phần tử có giá trị lớn hơn key về sau
        while j >= 0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr     

print(insertion_sort(arr))
# Kết quả: [1, 2, 3, 4, 5, 7, 9, 10]
```
*Độ phức tạp thời gian:* O(n^2)

## 4. Sắp xếp trộn (Merge Sort)
Sử dụng chiến lược **"Chia để trị" (Divide and Conquer)**. Chia mảng thành 2 nửa, sắp xếp từng nửa rồi trộn (merge) chúng lại.

Trọng tâm trong bài học là **thuật toán trộn 2 mảng đã sắp xếp sẵn** để tạo thành mảng mới:

```python
# Trộn 2 mảng đã sắp xếp tăng dần
a = [1, 3, 6, 7, 10, 15, 20, 25]
b = [2, 4, 5, 8, 9, 1000, 1200]
res = []

i, j = 0, 0
# Trộn luân phiên hai mảng
while i < len(a) and j < len(b):
    if a[i] < b[j]:
        res.append(a[i])
        i += 1
    else:
        res.append(b[j])
        j += 1

# Kiểm tra nếu còn phần tử thừa trên mảng a 
while i < len(a):
    res.append(a[i])
    i += 1

# Kiểm tra nếu còn phần tử thừa trên mảng b
while j < len(b):
    res.append(b[j])
    j += 1  

print(res)
# Kết quả: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 15, 20, 25, 1000, 1200]
```
*Độ phức tạp thời gian:* O(n log n) khi triển khai Merge Sort đầy đủ bằng đệ quy.

### Merge Sort đầy đủ (từ 1 mảng ban đầu — dùng đệ quy)

Ý tưởng:
1. **Chia (Divide):** tách mảng thành 2 nửa ở vị trí giữa.
2. **Trị (Conquer):** đệ quy sắp xếp từng nửa.
3. **Trộn (Merge):** gộp 2 nửa đã sắp xếp lại.

```
merge_sort([5, 1, 4, 2, 8])
├── merge_sort([5, 1])
│   ├── merge_sort([5])  → [5]
│   ├── merge_sort([1])  → [1]
│   └── merge([5], [1])  → [1, 5]
├── merge_sort([4, 2, 8])
│   ├── merge_sort([4])       → [4]
│   ├── merge_sort([2, 8])
│   │   ├── merge_sort([2])   → [2]
│   │   ├── merge_sort([8])   → [8]
│   │   └── merge([2], [8])   → [2, 8]
│   └── merge([4], [2, 8])    → [2, 4, 8]
└── merge([1, 5], [2, 4, 8])  → [1, 2, 4, 5, 8]
```

```python
def merge(a, b):
    res = []
    i, j = 0, 0
    while i < len(a) and j < len(b):
        if a[i] <= b[j]:
            res.append(a[i])
            i += 1
        else:
            res.append(b[j])
            j += 1
    res.extend(a[i:])
    res.extend(b[j:])
    return res

def merge_sort(arr):
    if len(arr) <= 1:          # base case: mảng 0 hoặc 1 phần tử đã sắp xếp
        return arr
    mid = len(arr) // 2
    left = merge_sort(arr[:mid])   # đệ quy nửa trái
    right = merge_sort(arr[mid:])  # đệ quy nửa phải
    return merge(left, right)      # trộn 2 nửa đã sắp

print(merge_sort([5, 1, 4, 2, 8]))  # [1, 2, 4, 5, 8]
```

> **Base case quan trọng:** `len(arr) <= 1` — mảng 1 phần tử luôn đã sắp xếp, đệ quy dừng ở đây.

---

# Class (Lớp) trong Python

**Class** là bản thiết kế (blueprint) để tạo ra các **object** (đối tượng). Mỗi object có thuộc tính (attribute) và phương thức (method) riêng.

---

## 1. Định nghĩa Class và tạo Object

```python
class Person:
    def __init__(self, name, age):  # hàm khởi tạo
        self.name = name            # thuộc tính
        self.age = age

    def greet(self):                # phương thức
        return f"Xin chào, tôi là {self.name}, {self.age} tuổi"

p = Person("Long", 20)  # tạo object
print(p.greet())        # Xin chào, tôi là Long, 20 tuổi
```

> **`self`** đại diện cho chính object đang gọi phương thức. Mọi phương thức instance đều có `self` làm tham số đầu tiên.

---

## 2. Class variable và Instance variable

| Loại | Khai báo | Phạm vi |
|------|----------|---------|
| **Instance variable** | Trong `__init__` qua `self` | Riêng từng object |
| **Class variable** | Trực tiếp trong class | Chung tất cả object |

```python
class Student:
    school = "PTIT"       # class variable — dùng chung

    def __init__(self, name):
        self.name = name  # instance variable — riêng mỗi object

s1 = Student("An")
s2 = Student("Bình")

Student.school = "VNU"    # thay đổi class variable → ảnh hưởng cả s1 và s2
print(s1.school, s2.school)  # VNU VNU
s1.name = "Cường"            # chỉ thay đổi s1
print(s1.name, s2.name)      # Cường Bình
```

---

## 3. Các phương thức đặc biệt (Dunder Methods)

Các phương thức có dạng `__tên__` được Python tự động gọi trong các tình huống đặc biệt.

### Khởi tạo và huỷ
```python
class Point:
    def __init__(self, x, y):   # gọi khi tạo object
        self.x = x
        self.y = y

    def __del__(self):           # gọi khi object bị xoá
        print("Point deleted")

    def __str__(self):           # gọi khi print(obj)
        return f"({self.x}, {self.y})"

    def __repr__(self):          # gọi khi debug / repr(obj)
        return f"Point(x={self.x}, y={self.y})"

p = Point(3, 4)
print(p)         # (3, 4)
```

### Toán tử số học
| Toán tử | Phương thức |
|---------|-------------|
| `+` | `__add__` |
| `-` | `__sub__` |
| `*` | `__mul__` |
| `/` | `__truediv__` |
| `//` | `__floordiv__` |
| `%` | `__mod__` |
| `**` | `__pow__` |

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

v1 = Vector(1, 2)
v2 = Vector(3, 4)
print(v1 + v2)   # (4, 6)
```

### Toán tử so sánh
| Toán tử | Phương thức |
|---------|-------------|
| `==` | `__eq__` |
| `!=` | `__ne__` |
| `<` | `__lt__` |
| `<=` | `__le__` |
| `>` | `__gt__` |
| `>=` | `__ge__` |

```python
class Student:
    def __init__(self, score):
        self.score = score

    def __lt__(self, other):
        return self.score < other.score

a = Student(8)
b = Student(9)
print(a < b)    # True
```

### Container và Iterator
```python
class MyList:
    def __init__(self, data):
        self.data = data

    def __len__(self):        # len(obj)
        return len(self.data)

    def __getitem__(self, i): # obj[i]
        return self.data[i]

    def __contains__(self, x):# x in obj
        return x in self.data

ml = MyList([1, 2, 3])
print(len(ml))    # 3
print(ml[1])      # 2
print(2 in ml)    # True
```

```python
class Counter:
    def __init__(self, n):
        self.n = n
        self.i = 0

    def __iter__(self):   # trả về iterator
        return self

    def __next__(self):   # lấy phần tử tiếp theo
        if self.i < self.n:
            self.i += 1
            return self.i
        raise StopIteration

for x in Counter(3):
    print(x)   # 1, 2, 3
```

---

## 4. Kế thừa (Inheritance)

**Kế thừa** cho phép lớp con (subclass) sử dụng lại thuộc tính và phương thức của lớp cha (superclass), đồng thời có thể mở rộng hoặc ghi đè chúng.

**Thuật ngữ:**
- Lớp cha = superclass = base class = parent class
- Lớp con = subclass = derived class = child class

```
class <tên lớp con>(<tên lớp cha>):
    <nội dung>
```

```python
class Animal:
    def __init__(self, name):
        self.name = name

    def speak(self):
        return "..."

class Dog(Animal):
    def __init__(self, name, breed):
        super().__init__(name)  # gọi __init__ của lớp cha
        self.breed = breed

    def speak(self):            # ghi đè (override) phương thức cha
        return "Gâu gâu!"

dog = Dog("Lucky", "Husky")
print(dog.name, dog.breed)  # Lucky Husky
print(dog.speak())          # Gâu gâu!
```

### 4.1. Khởi tạo thuộc tính lớp cha với `super()`

Khi lớp con có `__init__` riêng, cần gọi `super().__init__(...)` để khởi tạo các thuộc tính của lớp cha. Nếu lớp con không định nghĩa `__init__`, Python tự động dùng `__init__` của lớp cha.

```python
class Account:
    def __init__(self, owner, balance=0):
        self._owner = owner
        self._balance = balance

class CreditAccount(Account):
    def __init__(self, owner, balance, limit):
        super().__init__(owner, balance)  # khởi tạo thuộc tính của Account
        self._limit = limit               # thuộc tính riêng của CreditAccount

class SavingAccount(Account):
    pass  # không có __init__ → tự dùng Account.__init__

acc = CreditAccount("An", 1000, 5000)
sav = SavingAccount("Bình", 2000)
```

### 4.2. Quy tắc tìm phương thức từ dưới lên (Bottom-Up Rule)

Khi gọi `obj.method()`, Python tìm `method` theo thứ tự:
1. Tìm trong class của chính `obj`
2. Nếu không có, tìm lên lớp cha
3. Tiếp tục lên các lớp trên cho đến khi tìm thấy
4. Nếu không tìm thấy ở bất kỳ đâu → `AttributeError`

```python
class Account:
    def deposit(self, amount):
        self._balance += amount

class InterestAccount(Account):
    def addInterest(self, rate):
        self.deposit(self._balance * rate)  # deposit tìm thấy ở Account

acct = InterestAccount("An", 1000)
acct.deposit(500)       # tìm ở InterestAccount → không có → tìm lên Account → có
acct.addInterest(0.05)  # tìm ở InterestAccount → có
```

### 4.3. Phân cấp lớp (Class Hierarchy)

Một lớp có thể là lớp cha của nhiều lớp con, tạo thành cây phân cấp:

```
Account
├── DepositAccount
│   └── InterestAccount
└── CreditAccount
```

```python
class Account:
    def __init__(self, owner):
        self._owner = owner
        self._balance = 0.0

class DepositAccount(Account):
    def deposit(self, amount):
        self._balance += amount

class InterestAccount(DepositAccount):
    def addInterest(self, rate):
        self.deposit(self._balance * rate)

class CreditAccount(Account):
    def __init__(self, owner, limit):
        super().__init__(owner)
        self._limit = limit

    def charge(self, amount):
        if self._balance - amount < -self._limit:
            print("Vượt hạn mức!")
        else:
            self._balance -= amount
```

### 4.4. Lớp `object` — gốc của mọi lớp

Mọi class trong Python đều ngầm kế thừa từ `object`. Hai cách viết dưới đây tương đương nhau:

```python
class MyClass:        # thực chất là...
    pass

class MyClass(object): # ...giống hệt thế này
    pass
```

Lớp `object` cung cấp các dunder method mặc định như `__str__`, `__eq__`, v.v. Khi ta tự định nghĩa các phương thức này trong class, ta đang **ghi đè** hành vi mặc định của `object`.

### 4.5. Kiểm tra kiểu: `isinstance()` và `type()`

| Hàm | Ý nghĩa |
|-----|---------|
| `isinstance(obj, C)` | `True` nếu `obj` là instance của `C` **hoặc bất kỳ lớp cha nào** của `C` |
| `type(obj) == C` | `True` chỉ khi `obj` thuộc **đúng** class `C`, không tính lớp cha |

```python
acct = InterestAccount("An", 1000)

isinstance(acct, InterestAccount)  # True
isinstance(acct, DepositAccount)   # True  (lớp cha)
isinstance(acct, Account)          # True  (lớp ông)
isinstance(acct, CreditAccount)    # False (không liên quan)

type(acct) == InterestAccount      # True
type(acct) == Account              # False
```

> **Dùng `isinstance()` khi nào?** Hầu hết các trường hợp thực tế — nó linh hoạt hơn và phù hợp với nguyên tắc OOP. `type()` dùng khi cần phân biệt chính xác từng class.

### 4.6. Ghi đè phương thức (Method Overriding)

Lớp con định nghĩa lại phương thức đã có ở lớp cha → phương thức lớp con được dùng (theo quy tắc bottom-up).

**Ghi đè hoàn toàn:**
```python
class Account:
    def printStatement(self):
        print(f"Chủ tài khoản: {self._owner}")
        print(f"Số dư: {self._balance}")

class CreditAccount(Account):
    def printStatement(self):          # ghi đè
        print(f"Chủ tài khoản: {self._owner}")
        print(f"Số dư: {self._balance}")
        print(f"Hạn mức: {self._limit}")  # thêm thông tin riêng
```

**Ghi đè kết hợp `super()` — tránh lặp code:**
```python
class CreditAccount(Account):
    def printStatement(self):
        super().printStatement()           # gọi phương thức của lớp cha
        print(f"Hạn mức: {self._limit}")  # chỉ thêm phần riêng
```

> `super().<method>(<args>)` gọi phương thức của lớp cha nhưng vẫn dùng `self` là object hiện tại. Việc tìm kiếm phương thức bắt đầu từ lớp cha, không phải từ lớp hiện tại.

### 4.7. Tương đương đối tượng: `==` và `is`

| Toán tử | Ý nghĩa |
|---------|---------|
| `is` | Hai biến trỏ đến **cùng một object** (cùng địa chỉ bộ nhớ) |
| `==` | Hai object có **giá trị tương đương** (có thể là hai object khác nhau) |

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

p1 = Point(0, 0)
p2 = Point(0, 0)

p1 is p2    # False — hai object khác nhau
p1 == p2    # False — mặc định object dùng `is` để so sánh
```

Mặc định, `==` với class tự định nghĩa hoạt động giống `is`. Để tùy chỉnh `==`, ghi đè `__eq__`:

```python
class Point:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __eq__(self, other):
        return type(other) == Point \
            and self.x == other.x \
            and self.y == other.y

p1 = Point(0, 0)
p2 = Point(0, 0)
print(p1 == p2)   # True — cùng tọa độ
print(p1 is p2)   # False — vẫn là hai object khác nhau
```

> **Lưu ý:** Trong `__eq__`, nên kiểm tra `type(other) == <Class>` trước khi truy cập thuộc tính để tránh lỗi khi so sánh với object khác loại.

---

## 5. Đóng gói (Encapsulation)

| Tiền tố | Ý nghĩa | Ví dụ |
|---------|---------|-------|
| Không có | Công khai (public) | `self.name` |
| `_` | Bán riêng tư (protected) — quy ước | `self._balance` |
| `__` | Riêng tư (private) — Python đổi tên | `self.__secret` |

```python
class Account:
    def __init__(self, balance):
        self._balance = balance    # protected — dùng quy ước

    def get_balance(self):
        return self._balance

    def deposit(self, amount):
        if amount > 0:
            self._balance += amount

acc = Account(1000)
print(acc.get_balance())   # 1000
```

---

## 6. @property

Cho phép truy cập phương thức **như thuộc tính** (không cần gọi `()`).

```python
class Circle:
    def __init__(self, r):
        self._r = r

    @property
    def area(self):
        return 3.14 * self._r ** 2

    @property
    def radius(self):
        return self._r

    @radius.setter
    def radius(self, value):
        if value > 0:
            self._r = value

c = Circle(5)
print(c.area)    # 78.5 — gọi như thuộc tính, không cần c.area()
c.radius = 10    # gọi setter
print(c.area)    # 314.0
```

---

## 7. @classmethod và @staticmethod

| Loại | Decorator | Tham số đầu | Truy cập |
|------|-----------|-------------|---------|
| Instance method | — | `self` | Thuộc tính instance và class |
| Class method | `@classmethod` | `cls` | Chỉ class variable |
| Static method | `@staticmethod` | Không có | Không truy cập class/instance |

```python
class MathUtils:
    pi = 3.14

    @classmethod
    def circle_area(cls, r):    # cls là class MathUtils
        return cls.pi * r * r

    @staticmethod
    def add(a, b):              # hàm tiện ích, không cần self/cls
        return a + b

print(MathUtils.circle_area(3))  # 28.26
print(MathUtils.add(2, 5))       # 7
```

---

## Tóm tắt nhanh

| Khái niệm | Cú pháp |
|-----------|---------|
| Định nghĩa class | `class TênClass:` |
| Hàm khởi tạo | `def __init__(self, ...):` |
| Kế thừa | `class Con(Cha):` |
| Gọi hàm cha | `super().__init__(...)` |
| In object | `def __str__(self):` |
| Cộng hai object | `def __add__(self, other):` |
| Thuộc tính tính toán | `@property` |
| Phương thức lớp | `@classmethod` |
| Phương thức tĩnh | `@staticmethod` |


---

# Ngoại lệ (Exception) trong Python

**Ngoại lệ** là lỗi xảy ra trong lúc chạy chương trình. Python cho phép **bắt** và **xử lý** ngoại lệ thay vì để chương trình bị dừng đột ngột.

---

## 1. Cấu trúc try – except – else – finally

```
try:
    <code có thể gây lỗi>
except <LoạiLỗi>:
    <xử lý khi có lỗi>
else:
    <chạy khi KHÔNG có lỗi>
finally:
    <luôn luôn chạy dù có lỗi hay không>
```

```python
try:
    x = int(input("Nhập số: "))
    print(10 / x)
except ValueError:
    print("Không phải số nguyên!")
except ZeroDivisionError:
    print("Không chia được cho 0!")
else:
    print("Tính toán thành công.")
finally:
    print("Kết thúc.")  # luôn chạy
```

---

## 2. Các loại ngoại lệ thường gặp

| Ngoại lệ | Nguyên nhân |
|----------|-------------|
| `ValueError` | Giá trị không hợp lệ (vd: `int("abc")`) |
| `TypeError` | Sai kiểu dữ liệu (vd: `"a" + 1`) |
| `ZeroDivisionError` | Chia cho 0 |
| `IndexError` | Chỉ số ngoài phạm vi list |
| `KeyError` | Key không tồn tại trong dict |
| `FileNotFoundError` | Không tìm thấy file |
| `AttributeError` | Object không có thuộc tính/phương thức đó |
| `NameError` | Biến chưa được khai báo |

```python
# Bắt nhiều loại lỗi cùng lúc
try:
    lst = [1, 2, 3]
    print(lst[10])
except (IndexError, KeyError) as e:
    print(f"Lỗi truy cập: {e}")
```

---

## 3. raise — tự ném ngoại lệ

Dùng `raise` để **tự ném lỗi** khi đầu vào không hợp lệ.

```python
def max_and_min(nums):
    if len(nums) == 0:
        raise ValueError("Danh sách không được rỗng")
    return max(nums), min(nums)

def three_smallest(nums):
    if len(nums) < 3:
        raise ValueError("Cần ít nhất 3 phần tử")
    return sorted(nums)[:3]

try:
    max_and_min([])
except ValueError as e:
    print(e)   # Danh sách không được rỗng
```

---

## 4. Ngoại lệ tự định nghĩa (Custom Exception)

Tạo lớp ngoại lệ riêng bằng cách kế thừa từ `Exception`.

```python
class AgeError(Exception):
    pass

class NegativeValueError(Exception):
    def __init__(self, value):
        super().__init__(f"Giá trị âm không hợp lệ: {value}")
        self.value = value

def set_age(age):
    if age < 0:
        raise NegativeValueError(age)
    if age > 150:
        raise AgeError("Tuổi không hợp lệ")
    return age

try:
    set_age(-5)
except NegativeValueError as e:
    print(e)   # Giá trị âm không hợp lệ: -5
```

---

## 5. Kết hợp Exception với Class

```python
class BankAccount:
    def __init__(self, owner, balance=0):
        self.owner = owner
        self.balance = balance

    def withdraw(self, amount):
        if amount <= 0:
            raise ValueError("Số tiền rút phải lớn hơn 0")
        if amount > self.balance:
            raise ValueError("Số dư không đủ")
        self.balance -= amount

acc = BankAccount("Long", 1000)
try:
    acc.withdraw(2000)
except ValueError as e:
    print(e)   # Số dư không đủ
```

---

## Tóm tắt nhanh

| Cú pháp | Ý nghĩa |
|---------|---------|
| `try: ... except E:` | Bắt ngoại lệ loại E |
| `except E as e:` | Lấy thông tin lỗi vào biến e |
| `except (E1, E2):` | Bắt nhiều loại lỗi |
| `else:` | Chạy khi không có lỗi |
| `finally:` | Luôn chạy dù có lỗi hay không |
| `raise E(msg)` | Ném ngoại lệ thủ công |
| `class MyErr(Exception):` | Tạo ngoại lệ tự định nghĩa |


---

# Đọc/Ghi File (File I/O) trong Python

Python cho phép đọc và ghi file văn bản (`.txt`, `.csv`,...) và file nhị phân.

---

## 1. Mở file — hàm `open()`

```python
f = open("ten_file.txt", mode)
# ... làm việc với f ...
f.close()  # phải đóng file sau khi dùng
```

### Các chế độ mở file (mode)

| Mode | Ý nghĩa |
|------|---------|
| `"r"` | Đọc (mặc định). Lỗi nếu file không tồn tại |
| `"w"` | Ghi (tạo mới hoặc xoá nội dung cũ) |
| `"a"` | Ghi tiếp (append) vào cuối file |
| `"x"` | Tạo file mới. Lỗi nếu file đã tồn tại |
| `"r+"` | Đọc và ghi |
| `"rb"`, `"wb"` | Đọc/ghi file nhị phân |

---

## 2. Dùng `with` — cách khuyến nghị

`with` tự động đóng file khi ra khỏi khối lệnh, kể cả khi có lỗi.

```python
with open("data.txt", "r", encoding="utf-8") as f:
    noi_dung = f.read()
    print(noi_dung)
# file tự đóng ở đây
```

> **Luôn dùng `encoding="utf-8"`** khi làm việc với file tiếng Việt.

---

## 3. Đọc file

```python
# Đọc toàn bộ nội dung thành 1 chuỗi
with open("data.txt", "r", encoding="utf-8") as f:
    content = f.read()

# Đọc từng dòng vào list
with open("data.txt", "r", encoding="utf-8") as f:
    lines = f.readlines()   # ["dòng 1\n", "dòng 2\n", ...]

# Duyệt từng dòng (tiết kiệm bộ nhớ)
with open("data.txt", "r", encoding="utf-8") as f:
    for line in f:
        print(line.strip())  # strip() bỏ ký tự xuống dòng \n
```

---

## 4. Ghi file

```python
# Ghi đè (tạo mới hoặc xoá nội dung cũ)
with open("output.txt", "w", encoding="utf-8") as f:
    f.write("Dòng 1\n")
    f.write("Dòng 2\n")

# Ghi nhiều dòng cùng lúc
lines = ["Táo\n", "Chuối\n", "Cam\n"]
with open("output.txt", "w", encoding="utf-8") as f:
    f.writelines(lines)

# Ghi tiếp vào cuối file (không xoá nội dung cũ)
with open("output.txt", "a", encoding="utf-8") as f:
    f.write("Thêm dòng mới\n")
```

---

## 5. Xử lý lỗi khi làm việc với file

```python
try:
    with open("khong_ton_tai.txt", "r", encoding="utf-8") as f:
        content = f.read()
except FileNotFoundError:
    print("File không tồn tại!")
except PermissionError:
    print("Không có quyền đọc file!")
```

---

## 6. Ví dụ thực tế — đọc và xử lý dữ liệu

```python
# Đọc danh sách điểm từ file, tính trung bình
def doc_diem(ten_file):
    diem = []
    try:
        with open(ten_file, "r", encoding="utf-8") as f:
            for line in f:
                line = line.strip()
                if line:
                    diem.append(float(line))
    except FileNotFoundError:
        raise FileNotFoundError(f"Không tìm thấy file: {ten_file}")
    return diem

def ghi_ket_qua(ten_file, diem):
    with open(ten_file, "w", encoding="utf-8") as f:
        for d in diem:
            ket_qua = "Đậu" if d >= 5 else "Rớt"
            f.write(f"{d} - {ket_qua}\n")
        f.write(f"Trung bình: {sum(diem)/len(diem):.2f}\n")
```

---

## Tóm tắt nhanh

| Thao tác | Code |
|----------|------|
| Mở và đọc toàn bộ | `f.read()` |
| Đọc từng dòng | `f.readlines()` hoặc `for line in f` |
| Ghi chuỗi | `f.write(chuoi)` |
| Ghi nhiều dòng | `f.writelines(list)` |
| Mở an toàn | `with open(...) as f:` |
| Đọc không lỗi | `try/except FileNotFoundError` |
