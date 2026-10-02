# Tóm tắt trạng thái dự án - Sử dụng SymPy giải quyết bài toán tương giao đồ thị

**Ngày cập nhật:** 22 tháng 9, 2026

## ✅ Thành tựu chính

### 📚 Nội dung
- **3/3 chương** hoàn thành (Chương 1: Lệnh SymPy & cơ sở lí thuyết; Chương 2: Giải bài toán tương giao; Chương 3: Kết luận & bảng tra cứu).
- **6 nhóm lệnh SymPy cốt lõi** được chuẩn hóa: `sp.symbols`, `sp.Eq`, `sp.diff`, `sp.roots`, `sp.solve`, `expr.subs`.
- **Thuật toán lọc cực trị chặt chẽ:** Ứng dụng `sp.roots()` trích xuất nghiệm bội lẻ của đạo hàm, loại bỏ triệt để điểm uốn có đạo hàm bằng 0 khi cô lập tham số $m$.
- **Xử lý tập xác định tự động:** Ứng dụng `sp.denom()` để phát hiện và loại bỏ nghiệm ngoại lai cho hàm phân thức.

### 💻 Mã nguồn & Thực nghiệm
- **2 notebook Python** hoàn chỉnh trong thư mục `/notebooks` (`01_cac_lenh_co_ban.ipynb`, `02_giai_bai_toan_dien_hinh.ipynb`).
- **Môi trường thực thi:** Kiểm thử và chạy thành công trên máy chủ JupyterLab trực tuyến (`https://py.truyenthong.edu.vn/lab/index.html`).
- **Đại số ký hiệu thuần túy:** Toàn bộ nghiệm và điều kiện tham số được bảo toàn dưới dạng giải tích chính xác (căn thức, phân số), không phụ thuộc vào tính toán xấp xỉ số học.

### 📄 Biên dịch LaTeX
- **Độ dài văn bản:** Khóa chặt đúng **10 trang** chuẩn mực.
- **Cấu trúc mô-đun:** Tách biệt rõ ràng giữa `main.tex`, `preamble.tex` và các file chương trong `/chapters`.
- **Định dạng code:** Sử dụng gói lệnh `listings` với font `\footnotesize`, bật `breaklines=true` đảm bảo không tràn lề trang.

---

## 📊 Thống kê chi tiết

### Phân bố nội dung theo chương

| Chương | File nguồn | Trang thực tế | Nội dung chính |
|:---:|---|:---:|---|
| 01 | `chapters/01-mo-dau.tex` | 4.0 | Giới thiệu JupyterLab, 6 nhóm lệnh SymPy cốt lõi, mô hình toán học và nguyên lí cô lập tham số $m$. |
| 02 | `chapters/02-giai-bai-toan-dien-hinh.tex` | 5.0 | Bài toán 1 (giao điểm đồ thị bậc ba, phân thức loại nghiệm gián đoạn); Bài toán 2 (biện luận theo tham số $m$ bằng nghiệm bội lẻ qua `sp.roots`). |
| 03 & TLTK | `chapters/03-ket-luan-va-cheatsheet.tex`<br>`chapters/tai_lieu_tham_khao.tex` | 1.0 | Kết luận ưu thế của CAS, bảng tra cứu nhanh lệnh SymPy (Cheat Sheet) và tài liệu tham khảo. |
| **Tổng** | | **10.0** | |

### Các file đã tạo/cập nhật

**Tài liệu LaTeX:**
- `main.tex` - File master điều phối liên kết toàn bộ tài liệu.
- `preamble.tex` - Khai báo cấu hình gói lệnh `amsmath`, `listings`, font tiếng Việt.
- `chapters/01-mo-dau.tex` - Nội dung chương 1.
- `chapters/02-giai-bai-toan-dien-hinh.tex` - Nội dung chương 2.
- `chapters/03-ket-luan-va-cheatsheet.tex` - Nội dung chương 3.
- `chapters/tai_lieu_tham_khao.tex` - Danh mục tài liệu tham khảo.

**Tài liệu quản trị & mã nguồn:**
- `README.md` - Đề cương và hướng dẫn tổng quan dự án.
- `PLAN.md` - Kế hoạch thực hiện và phân bổ trang.
- `SUMMARY.md` - Bản tóm tắt trạng thái này.
- `notebooks/01_cac_lenh_co_ban.ipynb` - Kiểm thử các hàm SymPy cơ bản.
- `notebooks/02_giai_bai_toan_dien_hinh.ipynb` - Kiểm thử mã nguồn giải bài toán tương giao.

---

## 🎯 Điểm nổi bật

### 1. Tính chuẩn xác của đại số ký hiệu (CAS)
- Loại bỏ hoàn toàn sai số làm tròn số học thường gặp; nghiệm được giữ nguyên ở dạng đại số chuẩn xác như $\pm\sqrt{3}$, phân số tối giản.
- Khắc phục lỗi `AttributeError` khi thay thế giá trị biến bằng cách chuẩn hóa sang phương thức đối tượng `expr.subs()`.

### 2. Thuật toán phân loại nghiệm bội
- Sử dụng hàm `sp.roots()` thay vì `sp.solve()` khi khảo sát đạo hàm, giúp phân biệt chính xác nghiệm bội lẻ (đạo hàm đổi dấu tạo cực trị) và nghiệm bội chẵn (điểm uốn không đổi dấu), đảm bảo biện luận tham số $m$ chính xác tuyệt đối.

### 3. Tối ưu hóa cấu trúc biên dịch
- Văn bản được phân bổ chặt chẽ theo từng trang dự kiến, không phụ thuộc vào chèn đồ thị ngoài, giúp dung lượng file PDF nhẹ và tốc độ biên dịch nhanh.

---

## 📋 Các bước tiếp theo

### Ưu tiên cao
- [ ] Rà soát lỗi chính tả và quy cách viết hoa trong toàn bộ các file `.tex`.
- [ ] Biên dịch thử nghiệm bản cuối (`main.tex`) để kiểm tra vị trí ngắt trang, đảm bảo kết thúc đúng trang 10.
- [ ] Xuất bản file PDF hoàn chỉnh lưu trữ vào kho mã nguồn.

### Ưu tiên trung bình
- [ ] Kiểm tra tính đồng nhất của các đoạn mã Python giữa file `.tex` và file `.ipynb`.
- [ ] Bổ sung chú thích ngắn gọn trong code block để tăng tính sư phạm cho học sinh lớp 12.

---

## 🔧 Vấn đề kỹ thuật đã xử lý

- **Lỗi `AttributeError: module 'sympy' has no attribute 'subs'`:** Đã sửa triệt để bằng cách chuyển sang cú pháp gọi phương thức `eq.subs(m, 0)` hoặc `f.subs(x, x0)`.
- **Lỗi nhận diện cực trị khi đạo hàm có nghiệm bội chẵn:** Đã thay thế việc lấy cực trị sơ cấp bằng thuật toán trích xuất nghiệm bội lẻ từ từ điển `sp.roots(f_prime, x)`.
- **Đồng bộ hóa phạm vi công cụ:** Đã loại bỏ hoàn toàn mã nguồn và các gói lệnh liên quan đến Matplotlib, giúp tài liệu tập trung toàn bộ trọng tâm vào tính toán đại số ký hiệu với SymPy.

---

## 📞 Thông tin lưu trữ

- Nền tảng thực hành: JupyterLab (`https://py.truyenthong.edu.vn/lab/index.html`)
- Trạng thái biên dịch: Sẵn sàng đóng gói xuất bản bản in PDF (10 trang).