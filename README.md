# Hệ thống Kho Tài Liệu Cá Nhân (MyVault)
**Học phần:** Thiết kế Web (111101)  
**Nhóm sinh viên thực hiện:** Phạm Đăng Khoa & Nguyễn Đăng Nhật  
**Dự án:** Xây dựng Trang Kho Tài Liệu số tích hợp bộ lọc đa năng thuần CSS (Zero JavaScript)  

---

## 📝 NHẬT KÝ SỬ DỤNG PROMPT (PROMPT LOG)

### 1. Nguyên văn 100% câu lệnh Prompt của người dùng (User Request)
> "Bạn là một chuyên gia vibe code bằng google antigravity, bạn hãy tạo cho mình một đoạn promtp để google antigravity tạo cho mình: Trang kho tài liệu, gồm có danh sách toàn bộ tài liệu kèm bộ lọc đa năng. Yêu cầu là phải tích hợp nhất tất cả các kiến thức từ Tuần 3 đến Tuần 5 mà mình đã gửi file word đính kèm " TUAN 3 TOI TUAN 5" gồm có: Semantic HTML, Flex/Grid, Responsive, Design System và Animations) vào 1 sản phẩm duy nhất. Trải nghiệm người dùng (UX): sử dụng các hiệu ứng chuyển động để dẫn dắt hành vi người dùng, tăng tính thẩm mỹ nhưng không làm chậm hiệu suất trang web. Toàn bộ code không sử dụng javascript . Toàn bộ code đưa vào file: trangkhotailieu.html và Tạo ghi chú giải thích từng dòng code sao cho dễ hiểu. Đồng thời  bạn hãy viết nhật kí dùng promt của mình lên file README.md theo đúng yêu cầu: giữ nguyên văn 100% câu prompt của bạn kèm theo phần tóm tắt ngắn gọn các bước xử lý kỹ thuật tương ứng."

---

### 2. Đoạn Master Prompt tối ưu chuyên sâu dành cho Google Antigravity (Expert Vibe Coding Prompt)
*Dưới đây là phiên bản Master Prompt được chuẩn hóa theo khung kỹ thuật Prompt Engineering của Google Antigravity để sinh ra toàn bộ trang web chuẩn mực:*

```markdown
Đóng vai một Kỹ sư Front-End Cao cấp & Chuyên gia Vibe Coding trên Google Antigravity.
Hãy thiết kế và viết toàn bộ mã nguồn cho trang "Kho Tài Liệu Cá Nhân" vào duy nhất tập tin `trangkhotailieu.html` theo tiêu chuẩn kỹ thuật sau:

1. RÀNG BUỘC CÔNG NGHỆ:
- TUYỆT ĐỐI 100% KHÔNG DÙNG JAVASCRIPT (No inline script, no external JS). Mọi tương tác lọc, chuyển đổi chế độ xem, và mở modal đều vận hành bằng CSS hiện đại (:has(), :checked, Radio/Checkbox Hack).
- Toàn bộ HTML và CSS tích hợp hoàn chỉnh trong file `trangkhotailieu.html`, có chú thích (comment) chi tiết bằng tiếng Việt cho từng khối mã nguồn.

2. TÍCH HỢP KIẾN THỨC TỪ TUẦN 3 ĐẾN TUẦN 5 (GIÁO TRÌNH LẠC HỒNG):
- TUẦN 3 (CSS Layout & Box Model):
  + Cấu trúc HTML5 ngữ nghĩa: <header>, <nav>, <main>, <section>, <aside>, <article>, <figure>.
  + Bố cục tổng thể trang chia 2 cột bằng CSS Grid (Sidebar bộ lọc dính sticky bên trái, Lưới tài liệu bên phải).
  + Lưới danh sách tài liệu sử dụng CSS Grid auto-fit: `grid-template-columns: repeat(auto-fit, minmax(270px, 1fr))`.
  + Từng card, menu, header và footer dàn trang linh hoạt bằng Flexbox.
  + Kiểm soát khoảng cách đồng nhất hoàn toàn bằng `gap` và chuẩn Box Model (`box-sizing: border-box`). Tuyệt đối không dùng float hay table.
- TUẦN 4 (Design System & Mobile-First Responsive):
  + Thiết lập Design System với CSS Variables tại `:root` (bảng màu, spacing scale, typography scale rem, border-radius, shadows).
  + Tư duy Mobile-First: Mặc định hiển thị hoàn hảo 1 cột trên điện thoại (< 600px), tự co giãn 2 cột trên Tablet (600px - 1024px), và mở rộng bố cục đa cột trên Desktop (> 1024px).
  + Hình ảnh và thumbnail đáp ứng: `max-width: 100%; height: auto; display: block;`. Không phát sinh thanh cuộn ngang (Horizontal scroll).
- TUẦN 5 (CSS Animations, Micro-interactions & GPU Performance):
  + Tối ưu GPU Acceleration: Chỉ chuyển động bằng thuộc tính `transform` và `opacity` (tránh Reflow / Repaint).
  + Hiệu ứng thẻ Card: Nâng thẻ khi hover (`transform: translateY(-6px)`), bóng đổ tỏa mềm mại, xoay icon tệp.
  + Hiệu ứng @keyframes: `fadeInUp` xuất hiện so le (staggered animation), `pulseGlow` cho huy hiệu Hot/Mới và nút FAB.
  + Nút Floating Action Button (FAB) ở góc dưới phải với animation xung nhịp liên tục.
  + Modal xem trước tài liệu (Quick Preview Modal) thuần CSS mở/đóng mượt mà không dùng JS.

3. TÍNH NĂNG KHO TÀI LIỆU & BỘ LỌC ĐA NĂNG:
- Thanh Hero giới thiệu kèm thống kê số lượng tài liệu, dung lượng, lượt tải.
- Bộ lọc đa năng gồm:
  + Lọc theo Chuyên mục (Tất cả, Web & UI, HĐH & Mạng, UI/UX Design, AI, Đề thi).
  + Lọc theo Định dạng tệp (Tất cả, PDF, DOCX, PPTX, ZIP).
  + Bộ chuyển đổi chế độ xem: Chế độ Lưới (Card Grid) và Chế độ Danh sách (List View).
- Danh sách tài liệu phong phú, mỗi thẻ có: icon định dạng tệp, tiêu đề, mô tả tóm tắt, dung lượng, rating sao ⭐, thanh tiến trình % tin cậy động, nút Xem trước và Tải về.
```

---

## 🛠️ TÓM TẮT CÁC BƯỚC XỬ LÝ KỸ THUẬT TƯƠNG ỨNG

### Bước 1: Trích xuất và phân tích yêu cầu từ giáo trình (Tuần 3 - Tuần 5)
- Giải nén và đọc tài liệu `TUAN 3 TOI TUAN 5.docx` để nắm trọn vẹn chuẩn đầu ra (LLO) của 3 tuần:
  * **Tuần 3:** CSS Grid Layout, Flexbox căn chỉnh 1 chiều, mô hình Box Model, cấm dùng `float`/`table`, quản lý khoảng cách bằng `gap`.
  * **Tuần 4:** Hệ thống Design System qua biến `:root`, triết lý thiết kế Mobile-First, các điểm gãy Media Queries (375px / 600px / 768px / 1024px), đơn vị tương đối `rem`.
  * **Tuần 5:** CSS Transitions cho tương tác, `@keyframes` (FadeIn, Pulse, Progress bar), tối ưu hiệu năng phần cứng bằng `transform` & `opacity` thay vì thay đổi kích thước gây giật lag (Reflow).

### Bước 2: Thiết kế kiến trúc "Bộ lọc Đa năng Thuần CSS" (Zero JavaScript)
- Thay vì dùng JavaScript bắt sự kiện `click` và lọc DOM, chúng tôi sử dụng kỹ thuật tân tiến:
  * Đặt các thẻ `<input type="radio" class="filter-controller" hidden>` ở đầu trang.
  * Tận dụng bộ chọn `:has()` và `:checked` của CSS3 hiện đại:
    + Khi chọn chuyên mục Web: `body:has(#cat-web:checked) .doc-card:not([data-cat="web"]) { display: none !important; }`
    + Khi chọn định dạng PDF: `body:has(#fmt-pdf:checked) .doc-card:not([data-fmt="pdf"]) { display: none !important; }`
    + Khi chọn chế độ Danh sách: `body:has(#view-list:checked) .docs-grid { grid-template-columns: 1fr; }` và chuyển flex-direction của thẻ card thành hàng ngang.
  * Tương tự, Modal xem trước nhanh (Quick Preview Modal) hoạt động bằng `<input type="checkbox" id="modal-preview-toggle">` và liên kết với `<label>` của nút "Xem trước" và nút đóng "X".

### Bước 3: Xây dựng cấu trúc HTML5 ngữ nghĩa (Semantic HTML5)
- Toàn bộ trang được tổ chức mạch lạc:
  * `<header>` và `<nav>`: Kế thừa menu điều hướng responsive và hamburger thuần CSS của hệ thống dự án MyVault.
  * `<main id="main-content">`: Vùng nội dung trung tâm của trang kho tài liệu.
  * `<section class="repo-hero">`: Khối giới thiệu tổng quan, huy hiệu động và thanh thống kê chỉ số.
  * `<aside class="filter-panel">`: Cột thanh điều khiển và bộ lọc đa năng (chuyên mục, định dạng, nút đặt lại).
  * `<section class="content-area">`: Vùng hiển thị tài liệu, bao gồm toolbar tìm kiếm và bộ chuyển đổi Grid/List.
  * `<article class="doc-card">`: Từng mục tài liệu độc lập với các thuộc tính dữ liệu `data-cat` và `data-fmt`.

### Bước 4: Thiết lập Design System và hiệu ứng Animations tối ưu GPU
- Khai báo hệ thống biến `:root` mở rộng cho tài liệu (`--color-pdf`, `--color-docx`, `--color-pptx`, `--color-zip`, bảng gia tốc `--ease-bounce`).
- Xây dựng đầy đủ các bài tập chuyển động Tuần 5:
  1. `@keyframes fadeInUp`: Hiệu ứng thẻ tài liệu trượt nhẹ từ dưới lên và mờ dần khi mở trang, áp dụng độ trễ `animation-delay` so le (staggered).
  2. `@keyframes pulseGlow`: Hiệu ứng nhịp đập co giãn cho huy hiệu HOT/MỚI và nút FAB nổi ở góc màn hình (Bài tập 1 Tuần 5).
  3. `@keyframes fillProgressBar`: Tự động lấp đầy thanh tiến trình đánh giá tài liệu từ 0% lên giá trị thực (Bài tập 6 Tuần 5).
  4. `@keyframes typingText` & `@keyframes blinkCursor`: Hiệu ứng máy đánh chữ chạy chữ tuần tự trên Banner Hero (Bài tập 3 Tuần 5).
  5. Hiệu ứng **3D Card Flip Showcase** (`perspective: 1000px`, `preserve-3d`, `backface-visibility: hidden`): Thẻ tài liệu tiêu biểu lật mặt 180 độ khi rê chuột (Bài tập 2 Tuần 5).
  6. Menu Hamburger 3 gạch chuyển đổi thành dấu "X" mượt mà (Bài tập 5 Tuần 5).
  7. Hover Micro-interactions: Nhấc thẻ tài liệu lên 6px (`translateY(-6px)`), xoay nhẹ icon tệp (`rotate(-4deg)`), làm sâu bóng đổ `box-shadow` giúp người dùng có cảm giác phản hồi tức thì và sinh động.

### Bước 5: Viết chú thích (Comments) giải thích chi tiết từng dòng code
- Bổ sung hệ thống chú thích tiếng Việt rõ ràng, mạch lạc xuyên suốt file `trangkhotailieu.html`, giải thích:
  * Ý nghĩa và vai trò của từng thẻ HTML Semantic.
  * Cơ chế hoạt động của Box Model, Flexbox và CSS Grid.
  * Nguyên lý hoạt động của bộ lọc không dùng JS qua `:has()` và `:checked`.
  * Lý do chọn thuộc tính `transform` thay vì `top/left` để đạt hiệu năng tối đa 60fps.

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
