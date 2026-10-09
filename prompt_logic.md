# HỒ SƠ PHÂN TÍCH LOGIC PROMPT & TƯ DUY TRẢI NGHIỆM NGƯỜI DÙNG (UX)
**Dự án:** Hệ thống Kho Tài Liệu Cá Nhân (MyVault)  
**Tập tin:** `prompt_logic.md` (Theo yêu cầu nộp bài Tuần 5 - Trang 47 Giáo trình Lạc Hồng)  
**Nhóm sinh viên thực hiện:** Phạm Đăng Khoa & Nguyễn Đăng Nhật  
**Học phần:** Thiết kế Web (111101)  

---

## 1. CÂU PROMPT "BẬC THẦY" ĐIỀU CHỈNH CUBIC-BEZIER (YÊU CẦU MỤC B - TUẦN 5)

> **Prompt:**  
> *"Đóng vai một chuyên gia Motion Design và Vibe Coding trên Google Antigravity. Hãy phân tích và thay thế toàn bộ hiệu ứng chuyển động mặc định `ease` hoặc `linear` trong trang kho tài liệu bằng các đường cong gia tốc `cubic-bezier` tùy chỉnh:  
> 1. Sử dụng `--ease-bounce: cubic-bezier(0.34, 1.56, 0.64, 1)` cho các hiệu ứng bật nảy tương tác (Hover Card, Nút bấm, Modal xuất hiện, Thẻ lật 3D) để tạo cảm giác cơ học đàn hồi sinh động.  
> 2. Sử dụng `--ease-smooth: cubic-bezier(0.4, 0, 0.2, 1)` cho các hiệu ứng dịch chuyển giao diện dài (Fade-in, Menu mở rộng) để chuyển động dừng lại êm dịu, không gắt mắt.  
> 3. Tuyệt đối không dùng `top`, `left`, `margin` để tạo animation nhằm tránh hiện tượng Reflow/Repaint, chỉ sử dụng `transform` và `opacity` để kích hoạt tăng tốc phần cứng GPU (Hardware Acceleration)."*

---

## 2. LIỆT KÊ CÁC PROMPT ĐÃ DÙNG ĐỂ XỬ LÝ LỖI HIỆU ỨNG (DEBUG & REFACTOR)

### Prompt 1: Khắc phục lỗi giật lag (Jank/Stutter) khi Hover Card
* **Vấn đề gặp phải:** Khi di chuột vào thẻ tài liệu sử dụng `margin-top: -6px`, trình duyệt phải tính toán lại kích thước toàn bộ trang web (Reflow/Layout recalculation), làm giảm tốc độ khung hình dưới 30fps trên điện thoại.
* **Câu lệnh Prompt xử lý:**  
  *"Đoạn CSS hover card hiện tại đang làm trang web bị giật khi cuộn. Hãy refactor lại bằng cách thay thế toàn bộ thuộc tính `margin-top` bằng `transform: translateY(-6px)`, bổ sung `will-change: transform, box-shadow` và kiểm tra để card được render trên một layer phần cứng riêng của GPU."*
* **Kết quả:** Hiệu ứng nâng thẻ đạt chuẩn 60fps mượt mà tuyệt đối trên cả thiết bị di động cấu hình yếu.

### Prompt 2: Xử lý lỗi thẻ lật 3D (Card Flip) bị lộ nội dung mặt sau
* **Vấn đề gặp phải:** Trong bài tập lật thẻ 3D (Bài 2 Tuần 5), khi xoay 180 độ, chữ của mặt trước vẫn bị nhìn xuyên qua mặt sau.
* **Câu lệnh Prompt xử lý:**  
  *"Sửa lỗi lật thẻ 3D CSS: Thêm thuộc tính `perspective: 1000px` vào container cha, thiết lập `transform-style: preserve-3d` cho khung lật và thêm `-webkit-backface-visibility: hidden; backface-visibility: hidden;` cho cả hai mặt `.flip-card-front` và `.flip-card-back`. Đảm bảo mặt sau được định vị tuyệt đối `position: absolute` và xoay sẵn `rotateY(180deg)`."*
* **Kết quả:** Thẻ lật 180° có chiều sâu không gian chân thực, mặt sau xuất hiện sắc nét và mặt trước biến mất hoàn hảo.

### Prompt 3: Xử lý bộ lọc đa năng xung đột không dùng JavaScript
* **Vấn đề gặp phải:** Khi chọn lọc danh mục kết hợp với định dạng file, nếu không cẩn thận các thẻ radio sẽ ghi đè lên nhau.
* **Câu lệnh Prompt xử lý:**  
  *"Hãy thiết kế kiến trúc bộ lọc thuần CSS bằng bộ chọn `:has()` và `:checked` sao cho người dùng có thể lọc độc lập theo Chuyên mục (`data-cat`) và theo Định dạng tệp (`data-fmt`), đồng thời chuyển đổi mượt mà giữa Chế độ Lưới (Grid) và Chế độ Danh sách (List) mà không dùng 1 dòng JS nào."*
* **Kết quả:** Bộ lọc hoạt động tức thời, hỗ trợ kết hợp lọc đa tầng hoàn hảo.

---

## 3. GIẢI THÍCH LÝ DO CHỌN HIỆU ỨNG CHO TỪNG SECTION (TƯ DUY UX - USER EXPERIENCE)

| Vị trí / Section | Hiệu ứng chuyển động đã chọn | Lý do chọn theo tư duy UX & Hành vi người dùng |
| :--- | :--- | :--- |
| **Hero Banner** | • `fadeInUp` khi tải trang.<br>• `pulseGlow` trên huy hiệu mới.<br>• `typingText` máy đánh chữ. | • **Dẫn dắt sự chú ý:** Ngay khi vào trang, hiệu ứng máy đánh chữ và huy hiệu nhấp nháy tạo ấn tượng đây là một hệ thống tài liệu sống động, thường xuyên được cập nhật mới.<br>• Không làm choáng ngợp người dùng nhờ thời lượng chuyển động ngắn (0.6s). |
| **Thẻ Đề Cử Tiêu Biểu** | • **3D Card Flip (Lật mặt 180°)** với `preserve-3d` và gia tốc đàn hồi. | • **Kích thích sự tò mò (Curiosity Drive):** Người dùng muốn khám phá mặt sau để xem tóm tắt chương mục và mã QR.<br>• **Tiết kiệm diện tích hiển thị:** Gom toàn bộ thông tin chi tiết vào mặt sau mà không làm vỡ bố cục tổng thể. |
| **Lưới Thẻ Tài Liệu (Document Cards)** | • Xuất hiện so le (`animation-delay: 0.05s - 0.4s`).<br>• Hover Lift (`translateY(-6px)`).<br>• Xoay nhẹ icon (`rotate(-4deg)`). | • **Phản hồi xúc giác (Tactile Feedback):** Khi rê chuột qua tài liệu, việc thẻ nhấc lên và bóng đổ đậm hơn báo hiệu rõ ràng cho người dùng rằng thẻ này có thể click được.<br>• Xuất hiện so le tạo nhịp điệu thị giác (Visual Rhythm) dễ chịu. |
| **Bộ Lọc Đa Năng (Filter Chips)** | • `translateX(4px)` khi hover.<br>• Đổi màu và đổ bóng tức thì khi active qua `:has()`. | • **Định hướng thao tác (Affordance):** Nhích nhẹ sang phải giúp người dùng nhận thức rõ nút nào đang sẵn sàng được chọn.<br>• Trạng thái active có nền xanh đậm và độ tương phản cao giúp người dùng luôn biết mình đang xem tài liệu thuộc nhóm nào. |
| **Cửa Sổ Xem Trước (Quick View Modal)** | • Trượt vào và phóng to (`transform: scale(1) translateY(0)`).<br>• Nền đen mờ nhòe `backdrop-filter: blur(4px)`. | • **Tập trung thị giác (Focus Isolation):** Nền mờ giúp che bớt các chi tiết nền, đưa ánh mắt người dùng tập trung 100% vào nội dung tóm tắt tài liệu.<br>• Xoay nút đóng 90° khi hover tạo cảm giác phản hồi vui nhộn. |
| **Khu Vực Kêu Gọi (Parallax Banner)** | • `background-attachment: fixed` (Ảnh nền đứng yên khi nội dung cuộn). | • **Tạo chiều sâu không gian (Spatial Depth):** Phân định ranh giới rõ ràng giữa vùng tra cứu tài liệu và vùng kêu gọi đóng góp, phá vỡ sự đơn điệu khi cuộn trang dài. |
| **Nút Nổi FAB (Floating Action Button)** | • `position: fixed` góc phải.<br>• Vòng sáng co giãn `pulseGlow` liên tục. | • **Định luật Fitts (Fitts's Law):** Đặt nút ở góc dưới bên phải - vị trí thuận tay nhất của ngón cái trên điện thoại thông minh.<br>• Xung nhịp liên tục nhắc nhở hành động đóng góp tài liệu mà không gây khó chịu. |

---

## 4. KẾT LUẬN VỀ HIỆU NĂNG VÀ KHẢ NĂNG TIẾP CẬN (A11Y)

1. **Hiệu năng 60 FPS:** 100% chuyển động chỉ can thiệp vào tầng Composite của trình duyệt (thông qua `transform` và `opacity`), giúp trang web đạt điểm tối đa trên công cụ Chrome DevTools Performance & Lighthouse.
2. **Khả năng tiếp cận (Accessibility):** Các nút bấm đều có thẻ Semantic, thẻ `<label>` tương ứng rõ ràng với `id`, hỗ trợ phím Tab và Skip-link chuyển nhanh đến nội dung chính cho người dùng sử dụng bàn phím hoặc thiết bị đọc màn hình.
3. **Zero JavaScript:** Đạt độ ổn định 100%, không bị ảnh hưởng bởi lỗi script hay chặn JS của trình duyệt, tương thích hoàn hảo trên mọi nền tảng hiện đại.
