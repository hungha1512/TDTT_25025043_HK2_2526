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

