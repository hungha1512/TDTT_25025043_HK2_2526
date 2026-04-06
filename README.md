# Tư Duy Tính Toán — Tài liệu tham khảo mẫu

> **Lưu ý:** Đây là repo **tham khảo mẫu** phục vụ học tập môn **Tư Duy Tính Toán**.  
> Vui lòng tự làm bài trước khi tham khảo. Sao chép nguyên xi bài làm là vi phạm quy định học thuật.

---

## Nội dung repo

| File / Folder | Mô tả |
|---------------|-------|
| `LyThuyet.md` | Lý thuyết tổng hợp: toán tử, điều kiện, vòng lặp, hàm |
| `BaiTapTuan3-1.ipynb` | Bài tập tuần 3 — Biểu thức, toán tử, nhập xuất dữ liệu |
| `BaiTapTuan4.ipynb` | Bài tập tuần 4 |
| `BieuThuc_ToanTu_NhapXuat_DuLieu.ipynb` | Notebook thực hành biểu thức & toán tử |
| `*.pdf` | Đề bài gốc từng tuần |

---

## Hướng dẫn clone về máy

### Cách 1 — GitHub CLI (`gh`)

> Yêu cầu: đã cài [GitHub CLI](https://cli.github.com/). Kiểm tra bằng lệnh `gh --version`.

```bash
# Đăng nhập (chỉ cần làm 1 lần)
gh auth login

# Clone repo về thư mục hiện tại
gh repo clone hungha1512/TDTT_25025043_HK2_2526

# Di chuyển vào thư mục vừa clone
cd TDTT_25025043_HK2_2526
```

Nếu repo có cập nhật mới, kéo về bằng:

```bash
git pull
```

---

### Cách 2 — GitHub Desktop

> Yêu cầu: đã cài [GitHub Desktop](https://desktop.github.com/).

1. Mở **GitHub Desktop**.
2. Chọn menu **File → Clone Repository...** (hoặc nhấn `Ctrl+Shift+O` / `Cmd+Shift+O`).
3. Chuyển sang tab **URL**, dán địa chỉ repo:
   ```
   https://github.com/hungha1512/TDTT_25025043_HK2_2526.git
   ```
4. Chọn thư mục lưu trên máy, nhấn **Clone**.
5. Khi repo có cập nhật mới, nhấn **Fetch origin** rồi **Pull** để kéo về.

---

### Cách 3 — Git thuần (không cần công cụ bổ sung)

```bash
git clone https://github.com/hungha1512/TDTT_25025043_HK2_2526.git
cd TDTT_25025043_HK2_2526
```

---

## Yêu cầu môi trường

- **Python** >= 3.10
- **Jupyter Notebook** hoặc **VS Code** với extension Python để chạy file `.ipynb`

Cài nhanh bằng pip:

```bash
pip install notebook
```

---

## Môn học

- **Môn:** Tư Duy Tính Toán  
- **Học kỳ:** HK2 — 2025–2026
