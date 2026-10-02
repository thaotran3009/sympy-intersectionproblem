# Dự án Biên soạn Tài liệu: Sử dụng Sympy để giải quyết bài toán về tương giao đồ thị

Chào mừng bạn đến với kho lưu trữ dự án biên soạn tài liệu kỹ thuật **Sử dụng SymPy để giải quyết bài toán về tương giao đồ thị**. Kho lưu trữ này quản lý mã nguồn LaTeX, các notebook Python kiểm thử và tiến độ thực hiện tài liệu.

---

## 📌 1. Thông tin chung
* **Chủ đề:** Ứng dụng SymPy để giải quyết bài toán tương giao đồ thị hàm số THPT (lớp 12).
* **Mục tiêu:**
  * Xây dựng pipeline tự động bằng Python: giải phương trình hoành độ giao điểm, loại bỏ nghiệm gián đoạn của mẫu số, biện luận số giao điểm bằng phương pháp cô lập tham số $m$.
  * Hệ thống hóa cơ sở lí thuyết toán học về tương giao và chuyển hóa thành thuật toán lập trình giải tích ký hiệu.
  * Tận dụng tối đa sức mạnh của đại số máy tính (CAS) để tìm nghiệm chính xác dạng phân số và căn thức mà không phụ thuộc vào tính toán xấp xỉ số học.
* **Định dạng đầu ra:** Tài liệu biên soạn bằng LaTeX, xuất bản dạng PDF với dung lượng chuẩn từ 10-15 trang.

---

## 🗺️ 2. Đề cương chi tiết tài liệu (10 trang)

### Chương 1: Một số lệnh thường dùng trong SymPy và cơ sở lí thuyết toán học (khoảng 4 trang)
* Ý nghĩa của tính toán giải tích ký hiệu (Symbolic Computation) trong bài toán tương giao đồ thị.
* Thiết lập môi trường thực hành trực tuyến trên JupyterLab tại `https://py.truyenthong.edu.vn/lab/index.html` (không cần cài đặt cục bộ).
* Giới thiệu 6 nhóm lệnh SymPy trọng tâm dùng trong tài liệu: `sp.symbols`, `sp.Eq`, `sp.diff`, `sp.roots`, `sp.solve`, `expr.subs`.
* **Mô hình phương trình hoành độ giao điểm:**
  * Chuyển đổi bài toán số giao điểm hình học sang tìm số nghiệm thực của phương trình $f(x) = g(x)$.
  * Ý nghĩa giải tích của nghiệm đơn (đồ thị cắt xuyên qua) và nghiệm bội (tiếp xúc).
* **Phương pháp cô lập tham số:**
  * Biến đổi phương trình về dạng $m = \varphi(x)$.
  * Nguyên lí tương giao giữa đồ thị hàm số $y = \varphi(x)$ và đường thẳng nằm ngang $y = m$.
  * Mối quan hệ giữa số nghiệm phương trình với các điểm cực trị thực sự (nghiệm bội lẻ của đạo hàm) trên bảng biến thiên của $\varphi(x)$.

### Chương 2: Giải quyết bài toán tương giao bằng SymPy (khoảng 5 trang)
* **Bài toán 1: Xác định tọa độ giao điểm không chứa tham số**
  * Tương giao giữa đường thẳng và đồ thị hàm bậc ba: Thiết lập phương trình hoành độ bằng `sp.Eq()`, tìm nghiệm chính xác bằng `sp.solve()`, tính tọa độ đầy đủ $(x, y)$ bằng `.subs()`.
  * Tương giao giữa đường thẳng và đồ thị phân thức $y = \dfrac{ax+b}{cx+d}$: Tự động xác định điều kiện mẫu số bằng `sp.denom()`, đối chiếu và loại trừ nghiệm gián đoạn ngoại lai.
* **Bài toán 2: Biện luận theo tham số $m$ số giao điểm của đồ thị với trục hoành $Ox$**
  * Thiết lập phương trình hoành độ có dạng $m = \varphi(x)$.
  * Dùng `sp.diff()` lấy đạo hàm $\varphi'(x)$, dùng `sp.roots()` trích xuất các nghiệm kèm số bội để loại bỏ nghiệm bội chẵn và xác định đúng giá trị cực đại, cực tiểu.
  * Lập luận và xuất ra các khoảng giá trị của $m$ để đồ thị có đúng 1, 2 hoặc 3 giao điểm phân biệt.

### Chương 3: Kết luận & bảng tra cứu (khoảng 1 trang)
* Đánh giá ưu điểm và tính chính xác giải tích của SymPy trong giải toán tương giao.
* Bảng tra cứu nhanh (Cheat Sheet) 6 nhóm lệnh SymPy cốt lõi và cú pháp tương ứng dùng trong tài liệu.
* Danh mục tài liệu tham khảo.

---

## 📈 3. Kế hoạch & tiến độ thực hiện (thời hạn: 3 tuần)

- [x] **Tuần 1: Khởi tạo môi trường & cơ sở lí thuyết**
  - Cấu hình khung LaTeX (`main.tex`, `preamble.tex`) và không gian làm việc trên JupyterLab web (`py.truyenthong.edu.vn`).
  - Viết phần mở đầu (hướng dẫn JupyterLab, 6 nhóm lệnh SymPy cốt lõi) và cơ sở lí thuyết toán học.
  - *Mục tiêu:* Biên dịch đạt chuẩn 3–4 trang đầu.

- [x] **Tuần 2: Lập trình giải toán bằng SymPy**
  - Lập trình và soạn Chương 2: Bài toán 1 (tìm giao điểm đồ thị bậc ba, phân thức) và Bài toán 2 (cô lập tham số $m$, lọc nghiệm bội lẻ qua `sp.roots`).
  - Kiểm thử mã nguồn trên notebook, tải file `.ipynb` về thư mục `/notebooks` để lưu trữ an toàn.
  - *Mục tiêu:* Biên dịch đạt tiến độ ~9 trang.

- [x] **Tuần 3: Biên tập LaTeX, khóa 10 trang & đóng gói**[cite: 2]
  - Soạn Chương 3: Kết luận, bảng tra cứu (Cheat Sheet) và tài liệu tham khảo.
  - *Mục tiêu:* Đọc soát công thức toán, xuất bản file PDF hoàn chỉnh 10-15 trang.

---

## 📚 4. Tài liệu tham khảo (dự kiến)
1. SymPy Documentation: *Solvers & Calculus Reference Manual* (`https://docs.sympy.org`).
2. Bộ Giáo dục và Đào tạo: *Sách giáo khoa Toán 12 (Chương trình GDPT mới)* – Chuyên đề Khảo sát hàm số và tương giao đồ thị.
3. Tuyển tập bài tập và đề thi tương giao đồ thị hàm số THPT.

---

## 🛠️ 5. Cấu trúc kho lưu trữ
* `/tex`: Toàn bộ mã nguồn LaTeX (`main.tex`, các file chương `.tex`, style cấu hình).
* `/notebooks`: Các file Jupyter Notebook (`.ipynb`) lưu trữ từ server `py.truyenthong.edu.vn`.