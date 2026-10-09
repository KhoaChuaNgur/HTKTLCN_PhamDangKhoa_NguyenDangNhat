# Hệ thống Kho Tài Liệu Cá Nhân (MyVault)
**Học phần:** Thiết kế Web (111101)  
**Nhóm sinh viên thực hiện:** Phạm Đăng Khoa & Nguyễn Đăng Nhật  
**Dự án:** Xây dựng Trang Kho Tài Liệu số tích hợp bộ lọc đa năng thuần CSS (Zero JavaScript)  

---

## 📝 NHẬT KÝ SỬ DỤNG PROMPT (PROMPT LOG)

### 📌 LẦN NHẮC 1 (PROMPT 1) — Thiết kế & Viết tiếp các Section Trang Kho Tài Liệu

#### 1. Nguyên văn 100% câu lệnh Prompt của người dùng:
> "Bạn là một chuyên gia vibe code bằng google antigravity, bạn hãy tạo cho mình một đoạn promtp để google antigravity dựa vào file trangkhotailieu.html đã có sẵn viết tiếp các section nội dung: Trang kho tài liệu, gồm có danh sách toàn bộ tài liệu kèm bộ lọc đa năng. Yêu cầu là phải tích hợp nhất tất cả các kiến thức từ Tuần 3 đến Tuần 5 mà mình đã gửi file word đính kèm " TUAN 3 TOI TUAN 5" gồm có: Semantic HTML, Flex/Grid, Responsive, Design System và Animations) vào 1 sản phẩm duy nhất. Trải nghiệm người dùng (UX): sử dụng các hiệu ứng chuyển động để dẫn dắt hành vi người dùng, tăng tính thẩm mỹ nhưng không làm chậm hiệu suất trang web. Toàn bộ code không sử dụng javascript . Toàn bộ code đưa vào file: trangkhotailieu.html và Tạo ghi chú giải thích từng dòng code sao cho dễ hiểu. Đồng thời  bạn hãy viết nhật kí dùng promt của mình lên file README.md theo đúng yêu cầu: giữ nguyên văn 100% câu prompt của bạn kèm theo phần tóm tắt ngắn gọn các bước xử lý kỹ thuật tương ứng."

#### 2. Tóm tắt ngắn gọn các bước xử lý kỹ thuật tương ứng:
- **Bước 1: Khai phá & Phân tích yêu cầu giáo trình (Tuần 3 - Tuần 5):**
  * *Tuần 3:* Semantic HTML5 (`<main>`, `<section>`, `<aside>`, `<article>`), CSS Grid 2 cột (`290px 1fr`), CSS Grid `auto-fit` `minmax(270px, 1fr)`, Flexbox dàn trang 1D, loại bỏ hoàn toàn `float`/`table`, quản lý khoảng cách bằng `gap`.
  * *Tuần 4:* Kế thừa Design System qua biến `:root` (màu nhận diện loại file, bảng màu chủ đạo, font scale rem, spacing), tư duy Mobile-First đáp ứng đa thiết bị qua Media Queries.
  * *Tuần 5:* Hiệu ứng chuyển động tối ưu GPU (`transform`, `opacity`) đạt chuẩn 60fps mượt mà, áp dụng cubic-bezier đàn hồi; tích hợp đủ 6 bài tập animation (FAB pulse, 3D flip card, typing effect, parallax banner, hamburger morphing, progress bar fill).
- **Bước 2: Thiết kế kiến trúc Bộ lọc đa năng Zero-JS:**
  * Dùng các thẻ `<input type="radio" class="filter-controller" hidden>` ở đầu `<body>`.
  * Dùng CSS3 `:has()` và `:checked` để ẩn/hiện card tức thì:
    `body:has(#cat-web:checked) .doc-card:not([data-cat="web"]) { display: none !important; }`
    `body:has(#fmt-pdf:checked) .doc-card:not([data-fmt="pdf"]) { display: none !important; }`
  * Hỗ trợ chuyển đổi chế độ xem Lưới (Grid) sang Danh sách (List) thuần CSS.
- **Bước 3: Xây dựng Quick Preview Modal 100% không dùng JS:**
  * Kích hoạt bằng `<input type="checkbox" id="modal-preview-toggle">` kết hợp `<label>` nút xem trước và nút đóng "X".
  * Áp dụng `backdrop-filter: blur(4px)` và hiệu ứng nảy nở `transform: scale(1)`.
- **Bước 4: Chú thích (Comment) chi tiết toàn bộ dòng code:**
  * Viết chú giải tiếng Việt tỉ mỉ trong [`trangkhotailieu.html`](trangkhotailieu.html) giải thích rõ Box Model, CSS Grid, Flexbox, cách hoạt động của bộ lọc và lý do chọn `transform` để tối ưu hiệu năng.

---

### 📌 LẦN NHẮC 2 (PROMPT 2) — Ghi Nhật Ký Prompt vào tệp README.md

#### 1. Nguyên văn 100% câu lệnh Prompt của người dùng:
> "Bây giờ bạn hãy viết nhật kí dùng prompt vào tệp README.md theo đúng yêu cầu giữ nguyên văn 100% câu prompt của bạn kèm theo phần tóm tắt ngắn gọn các bước xử  lý kỹ thuật tương ứng."

#### 2. Tóm tắt ngắn gọn các bước xử lý kỹ thuật tương ứng:
- **Bước 1: Trích xuất chính xác 100% nguyên văn Prompt:**
  * Lưu trữ nguyên văn từng ký tự, dấu câu của người dùng cả ở lần nhắc 1 và lần nhắc 2 vào các block trích dẫn (Blockquote Markdown).
- **Bước 2: Hệ thống hóa nhật ký theo cấu trúc báo cáo chuẩn mực:**
  * Phân mục rõ ràng giữa Prompt của người dùng (User Request) và các bước kỹ thuật (Technical Steps).
  * Bổ sung mục Master Vibe Coding Prompt sẵn sàng dùng cho Google Antigravity.
  * Bổ sung bảng đối chiếu chuẩn đầu ra (LLO) tương ứng từ Tuần 3 đến Tuần 5.
  * Cung cấp hướng dẫn kiểm thử thực tế trực quan 6 bước trên trình duyệt.

---

## 🤖 MASTER PROMPT TỐI ƯU DÀNH CHO GOOGLE ANTIGRAVITY

```markdown
Đóng vai một Kỹ sư Front-End Cao cấp & Chuyên gia Vibe Coding trên Google Antigravity.
Dựa vào file `trangkhotailieu.html` đã có sẵn trong dự án (kế thừa header, footer và hệ thống style.css của nhóm), hãy viết tiếp toàn bộ các section nội dung hoàn chỉnh cho "Trang kho tài liệu" gồm danh sách toàn bộ tài liệu kèm bộ lọc đa năng theo đúng các tiêu chuẩn kỹ thuật sau:

1. RÀNG BUỘC CÔNG NGHỆ:
- TUYỆT ĐỐI 100% KHÔNG SỬ DỤNG JAVASCRIPT (No inline JS, no external script, zero event listeners).
- Toàn bộ cơ chế tương tác (bộ lọc đa năng theo chuyên mục, lọc theo định dạng tệp, chuyển đổi chế độ xem Grid/List, đóng/mở Modal xem trước tài liệu, Menu mobile hamburger) phải vận hành hoàn toàn bằng kỹ thuật thuần CSS3 hiện đại (:has(), :checked, Radio/Checkbox Hack, CSS sibling combinators).
- Toàn bộ mã nguồn đưa vào tập tin `trangkhotailieu.html` và viết chú thích (comment) giải thích chi tiết, dễ hiểu từng dòng/khối code bằng tiếng Việt.

2. TÍCH HỢP TOÀN DIỆN KIẾN THỨC TỪ TUẦN 3 ĐẾN TUẦN 5 (GIÁO TRÌNH LẠC HỒNG):
- TUẦN 3: CSS LAYOUT SYSTEM (FLEXBOX & GRID):
  + Cấu trúc HTML5 Semantic: Sử dụng đúng vai trò của <main>, <section>, <aside>, <article>, <figure>, <nav>, <header>, <footer>.
  + Bố cục phân chia tổng thể bằng CSS Grid 2 cột: Cột trái (<aside class="filter-panel">) rộng 290px cố định/sticky và Cột phải (<section class="content-area">) chiếm toàn bộ không gian còn lại (1fr).
  + Lưới hiển thị danh sách tài liệu sử dụng CSS Grid tự động chia cột thông minh: `grid-template-columns: repeat(auto-fit, minmax(270px, 1fr))`.
  + Từng thành phần con (Thanh thống kê Hero, Toolbar, Thẻ Card tài liệu, Thanh đánh giá, Nút bấm) căn chỉnh đa chiều linh hoạt bằng CSS Flexbox.
  + Kiểm soát khoảng cách đồng nhất hoàn toàn bằng thuộc tính `gap`, loại bỏ 100% float hay layout table cũ kỹ; áp dụng triệt để Box Model (box-sizing: border-box).
- TUẦN 4: DESIGN SYSTEM & TƯ DUY RESPONSIVE (MOBILE-FIRST):
  + Thiết lập Design System với CSS Variables tại `:root` (bảng màu phân loại PDF/DOCX/PPTX/ZIP, màu thương hiệu, typography scale rem, spacing scale, border-radius, shadows, timing curves).
  + Tư duy thiết kế Mobile-First: Mặc định hiển thị chuẩn xác 1 cột trên điện thoại (< 600px), tự co giãn 2 cột trên Tablet (600px - 1024px), và mở rộng bố cục đa cột trên Desktop (> 1024px).
  + Đảm bảo ảnh đại diện, thumbnail co giãn linh hoạt (`max-width: 100%; height: auto;`), kiểm soát chặt chẽ Viewport, tuyệt đối không bị lỗi tràn ngang màn hình (Horizontal scroll).
- TUẦN 5: HIỆU ỨNG CHUYỂN ĐỘNG & TỐI ƯU HIỆU NĂNG (CSS ANIMATIONS & UX):
  + Tối ưu phần cứng GPU (Hardware Acceleration): 100% animation và transition chỉ can thiệp vào `transform` và `opacity` (tuyệt đối không dùng top, left, width, margin gây hiện tượng giật Reflow/Repaint), đảm bảo tốc độ khung hình 60 FPS mượt mà.
  + Áp dụng hàm gia tốc tự nhiên: `--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1)` cho phản hồi đàn hồi và `--ease-smooth: cubic-bezier(0.4, 0, 0.2, 1)` cho các hiệu ứng chuyển cảnh dài.
  + Tích hợp đầy đủ các bài tập chuyển động Tuần 5:
    * Bài 1: Nút nổi tương tác (FAB) ở góc phải với animation @keyframes pulse co giãn thu hút chú ý.
    * Bài 2: Thẻ đề cử tiêu biểu lật mặt 180° (3D Card Flip) sử dụng perspective, transform-style: preserve-3d, backface-visibility: hidden.
    * Bài 3: Hiệu ứng máy đánh chữ (Typing Effect) trên Banner giới thiệu bằng @keyframes.
    * Bài 4: Khu vực Banner kêu gọi đóng góp với hiệu ứng Parallax Background (background-attachment: fixed).
    * Bài 5: Menu Hamburger 3 gạch biến đổi mượt mà thành dấu "X" khi mở menu trên di động.
    * Bài 6: Thanh tiến trình độ tin cậy của tài liệu tự động chạy từ 0% đến giá trị thực (Progress bar animation).
  + Micro-interactions: Thẻ card nhấc lên 6px (`translateY(-6px)`), xoay nhẹ icon tệp (`rotate(-4deg)`), bóng đổ tỏa sâu khi rê chuột (hover).

3. CÁC SECTION NỘI DUNG CẦN TRIỂN KHAI TRONG `trangkhotailieu.html`:
- Section 1 (Hero Banner): Giới thiệu kho tri thức, huy hiệu nhịp đập, hiệu ứng máy đánh chữ và thanh thống kê chỉ số số lượng tài liệu/dung lượng/lượt tải.
- Section 2 (Thanh điều khiển & Bộ lọc đa năng):
  + Cột Filter (<aside>): Lọc theo chuyên mục (Tất cả, Web, HĐH & Mạng, UI/UX, AI, Đề thi), lọc theo định dạng (PDF, DOCX, PPTX, ZIP), nút Reset đặt lại bộ lọc.
  + Toolbar (<section>): Ô tìm kiếm giao diện chuẩn UX, bộ chuyển đổi chế độ hiển thị Lưới thẻ (Grid) / Danh sách (List).
  + Thẻ đề cử tiêu biểu 3D Card Flip.
  + Danh sách toàn bộ tài liệu (Cards Grid) gồm ít nhất 8 tài liệu đa dạng chuyên mục và định dạng, có đầy đủ icon, nhãn HOT/MỚI, rating sao, thanh tiến trình % tin cậy, nút Xem trước và Tải về.
- Section 3 (Parallax Call-To-Action Banner): Kêu gọi sinh viên đóng góp tài liệu với ảnh nền Parallax có chiều sâu 3D.
- Section 4 (Quick Preview Modal): Cửa sổ xem trước tóm tắt tài liệu popup thuần CSS, có nút đóng "X" xoay 90° khi hover.
- Section 5 (Floating Action Button - FAB): Nút nổi tròn ở góc dưới bên phải màn hình để đóng góp nhanh tài liệu.
```

---

## 📊 BẢNG ĐỐI CHIẾU KIẾN THỨC TÍCH HỢP (TUẦN 3 - 5)

| Tuần | Nội dung kiến trúc | Triển khai thực tế trong `trangkhotailieu.html` |
| :--- | :--- | :--- |
| **Tuần 3** | **CSS Grid & Flexbox** | - Layout chính 2 cột bằng CSS Grid (`290px 1fr`).<br>- Lưới tài liệu dùng `repeat(auto-fit, minmax(270px, 1fr))`.<br>- Thanh thống kê, toolbar, thẻ Card dùng Flexbox linh hoạt.<br>- Loại bỏ 100% `float` và `table`, quản lý khoảng cách bằng `gap`. |
| **Tuần 4** | **Design System & Mobile-First** | - Bộ biến `:root` quản lý màu định dạng file, spacing, font, radius, shadow.<br>- Thiết kế chuẩn Mobile-First (1 cột trên mobile < 600px, 2 cột trên tablet, đa cột trên desktop).<br>- Thẻ `<meta name="viewport">` chuẩn mực, không lỗi tràn ngang màn hình. |
| **Tuần 5** | **Animations & Micro-UX** | - Nút nổi FAB (`position: fixed`) với hiệu ứng `@keyframes pulseGlow` (Bài 1).<br>- Thẻ đề cử tiêu biểu lật mặt 180° **Card Flip 3D** với `preserve-3d` (Bài 2).<br>- Hiệu ứng máy đánh chữ **Typing Effect** trên Banner (Bài 3).<br>- Menu Hamburger 3 gạch biến thành dấu "X" (Bài 5).<br>- Thanh tiến trình độ tin cậy tự chạy **Progress Bar Animation** (Bài 6).<br>- Hoàn toàn dùng GPU Acceleration (`transform` & `opacity`). |

---

## 🚀 HƯỚNG DẪN KIỂM THỬ TRANG WEB
1. Mở trực tiếp tập tin `trangkhotailieu.html` bằng trình duyệt bất kỳ (Google Chrome, Microsoft Edge, Firefox, Safari).
2. **Kiểm tra bộ lọc Chuyên mục:** Bấm chọn các tab danh mục như "Thiết kế Web & UI", "Hệ điều hành & Mạng"... để thấy danh sách tự động lọc ngay lập tức mà không cần tải lại trang.
3. **Kiểm tra bộ lọc Định dạng:** Bấm chọn các tag "PDF", "DOCX", "PPTX", "ZIP Code".
4. **Kiểm tra chế độ xem:** Bấm vào nút "Danh sách" để xem giao diện chuyển từ dạng lưới Card sang dạng bảng ngang.
5. **Kiểm tra Modal xem trước:** Bấm nút "Xem trước" ở bất kỳ tài liệu nào để mở cửa sổ Modal chi tiết; bấm nút dấu "X" hoặc "Đóng cửa sổ" để tắt.
6. **Kiểm tra Responsive:** Bấm phím `F12` trong trình duyệt và thử nghiệm trên các kích thước màn hình iPhone, iPad và Laptop để kiểm chứng độ tương thích hoàn hảo.
