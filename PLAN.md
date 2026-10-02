# Kế hoạch thực hiện: Sử dụng Sympy để giải quyết bài toán về tương giao đồ thị

## Định dạng kỹ thuật

Tài liệu được biên soạn bằng **LaTeX** (engine `xelatex` hoặc `pdflatex`) với độ dài mục tiêu từ **10 - 15 trang**, vì:

- **Tính chuẩn xác trong học thuật:** Quản lý công thức toán, hệ phương trình hoành độ giao điểm, giá trị tham số và tham chiếu chéo chính xác tuyệt đối.
- **Trình bày mã nguồn trực quan:** Tích hợp gói lệnh `listings` để nhúng code Python, tô màu cú pháp và quản lý ngắt dòng tự động.
- **Mô-đun hóa tài liệu:** Phân tách từng chương thành các file `.tex` độc lập để thuận tiện cho việc kiểm soát dung lượng từng trang một cách linh hoạt.

## Cấu trúc thư mục dự kiến
```
sympy-graph-intersection/
├── README.md
├── PLAN.md
├── main.tex                  # File master điều phối toàn bộ tài liệu
├── preamble.tex              # Khai báo gói lệnh (amsmath, listings, hyperref, graphicx)
├── chapters/
│   ├── 01-mo-dau.tex      # Giới thiệu & Môi trường JupyterLab (~4 trang)
│   ├── 02-giai-bai-toan-dien-hinh.tex        # Cơ sở lí thuyết toán học (~5 trang)
│   ├── 03-ket-luan-va-cheatsheet.tex   # Bài toán 1 & Bài toán 2 (~3 trang)
│   ├── tai_lieu_tham_khao.tex (~1 trang)  # Bài toán 1 & Bài toán 2 (~3 trang)
├── notebooks/                # Lưu trữ file .ipynb tải về từ server web
│   ├── 01_cac_lenh_co_ban.ipynb
│   ├── 02_giai_bai_toan_dien_hinh.ipynb
```
## Quy ước kỹ thuật & Môi trường

- **Môi trường thực thi code:**
  - Nền tảng: JupyterLab trực tuyến tại `https://py.truyenthong.edu.vn/lab/index.html`.
  - Thực thi toàn bộ tính toán trên trình duyệt web; sau mỗi buổi làm việc cần tải file `.ipynb` về thư mục `/notebooks` để lưu trữ an toàn[cite: 2].
- **Định dạng mã nguồn Python:**
  - Gói `listings` cấu hình font `\footnotesize`, bật `breaklines=true` để tránh tràn lề trang[cite: 2].
  - Chỉ trích dẫn các dòng lệnh xử lý thuật toán cốt lõi, không đưa kết quả in rườm rà vào LaTeX.
- **Ký hiệu toán học & Macro:**
  - Dùng chuẩn `amsmath`, `amssymb`, `mathtools`[cite: 2].
  - Thiết lập macro cho các đối tượng quen thuộc: `\curve{C}`, `\lineeq{d}`, `\param{m}`.
- **Phân bổ trang (Khóa chặt mục tiêu 14 trang):**
  - Chương 1: Một số lệnh thường dùng trong SymPy và Cơ sở lí thuyết toán học: 4 trang.
  - Chương 2: Giải toán tương giao bằng SymPy: 5 trang.
  - Kết luận & Bảng tra cứu: 2 trang.
  - Tài liệu tham khảo: 1 trang.

## Các giai đoạn thực hiện (Lộ trình 3 tuần)
## 📈 Kế Hoạch Thực Hiện (3 Tuần)

- [x] **Tuần 1: Thiết lập & Cơ sở lý thuyết**
  - Cấu hình khung LaTeX và workspace trên JupyterLab web.
  - Viết Chương 1: Một số lệnh thường dùng trong SymPy và Cơ sở lí thuyết toán học
  - *Mục tiêu:* Biên dịch đạt chuẩn 4 trang đầu.

- [x] **Tuần 2: Lập trình giải toán**
  - Viết Chương 2: Code giải giao điểm đồ thị bậc ba, phân thức và cô lập tham số $m$.
  - *Mục tiêu:* Lưu trữ notebook về máy, biên dịch đạt ~5 trang.

- [x] **Tuần 3: Biên tập & Đóng gói**
  - Viết Kết luận, thiết kế Bảng tra cứu lệnh (Cheat Sheet) và Tài liệu tham khảo.
  - Tinh chỉnh cỡ chữ, khoảng cách hình vẽ để khớp chính xác 14 trang (không tràn trang 15).
  - Đọc soát công thức toán, xuất bản file PDF hoàn chỉnh.

## Theo dõi tiến độ từng phần

| STT | Phần / Nội dung | File nguồn | Trang dự kiến | Trạng thái |
|:---:|---|---|:---:|:---:|
| 1 | Một số lệnh thường dùng trong SymPy và Cơ sở lí thuyết | `01-mo-dau.tex` | 4.0 | Hoàn thiện |
| 2 | Giải quyết bài toán tương giao bằng SymPy | `02-giai-bai-toan-dien-hinh.tex` | 5.0 | Hoàn thiện |
| 3 | Giải toán tương giao bằng SymPy | `03-ket-luan-va-cheatsheet.tex` | 3.0| Hoàn thiện | 
| 4 | Tài liệu tham khảo | `tai_lieu_tham_khao.tex` | 1.0 | Hoàn thiện |

*Quy ước trạng thái:* `Chưa bắt đầu` $\rightarrow$ `Đang viết code` $\rightarrow$ `Đang soạn LaTeX` $\rightarrow$ `Đang căn chỉnh trang` $\rightarrow$ `Hoàn thiện.

## Rủi ro & Biện pháp khắc phục

- **Rủi ro mất file trên server JupyterLab:** Máy chủ web có thể đặt lại dữ liệu phiên làm việc $\rightarrow$ *Giải pháp:* Sau mỗi buổi thực hành, luôn tải file `.ipynb` về máy tính và lưu vào thư mục `/notebooks.