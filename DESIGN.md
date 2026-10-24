# DESIGN.md — Khung Sáng Studio (portfolio nhiếp ảnh gia kiến trúc)

Nguồn: task TEC-127 (con của Epic TEC-126). Tài liệu này là quyết định thiết kế duy nhất mà task Dev phải bám theo. Mọi màu, font, tỉ lệ khung dưới đây đều có số liệu cụ thể; nếu bản dựng lệch khỏi các số liệu này thì coi là chưa đạt.

## 1. Phong cách tham chiếu (chỉ một)

**Portfolio kiến trúc tối giản kiểu tạp chí editorial** — ảnh khổ lớn chiếm phần lớn màn hình, tiêu đề serif cỡ lớn như tiêu đề bài tạp chí, chú thích ngắn 1 dòng, khoảng trắng rộng giữa các khối.

## 2. Bảng màu (mã hex kèm vai trò từng màu)

| Mã hex | Vai trò |
|---|---|
| `#FAF7F2` | Nền chính toàn trang — trắng ấm, dùng cho mọi section |
| `#1C1A17` | Chữ chính — tiêu đề, đoạn văn, nhãn điều hướng |
| `#B4552D` | Điểm nhấn đất nung — link đang chọn, nút chính, giá gói nổi bật, gạch dưới tiêu đề section |
| `#E9DFD3` | Màu phụ: đường kẻ chia section, nền thẻ giá không nổi bật |
| `#6B6259` | Màu phụ: chữ phụ — chú thích ảnh, ngày chụp, mô tả phụ |
| `#FFFFFF` | Màu phụ: nền thẻ ảnh khi ảnh đặt trên nền có kẻ viền, nền form liên hệ |

Quy tắc dùng màu: nền luôn là `#FAF7F2`, không dùng nền tối cho section nào. Màu đất nung `#B4552D` chỉ dùng cho tối đa 1 nút chính mỗi màn hình và cho trạng thái đang chọn; không tô nền lớn bằng màu này.

## 3. Font chữ (tên cụ thể)

- **Tiêu đề: Fraunces** (serif, kiểu tạp chí) — dùng cho tên studio, tiêu đề hero, tiêu đề mỗi section, tên bộ sưu tập.
- **Nội dung: Inter** — dùng cho đoạn văn, chú thích ảnh, nhãn nút, nhãn form, giá, nhận xét.

Cỡ chữ cụ thể:

| Vị trí | Font | Cỡ desktop / mobile | Chiều cao dòng |
|---|---|---|---|
| Tiêu đề hero | Fraunces, đậm 600 | 64px / 40px | 1.15 |
| Tiêu đề section | Fraunces, đậm 600 | 40px / 28px | 1.2 |
| Tên bộ sưu tập / tên gói | Fraunces, đậm 600 | 24px / 20px | 1.3 |
| Đoạn văn | Inter, thường 400 | 17px / 16px | 1.7 |
| Chú thích ảnh, nhãn | Inter, thường 400 | 14px / 13px | 1.5 |
| Nút | Inter, đậm 600 | 16px | 1.5 |

## 4. Bố cục visual-first (OPERATIONS.md mục 16.1)

- Ảnh là nội dung chính, chữ chỉ làm khung: mỗi section tối đa 2 đoạn văn ngắn, mỗi đoạn tối đa 3 câu.
- Khoảng trắng: lề ngoài section 96px trên desktop / 48px trên mobile; khoảng cách giữa các section tối thiểu 80px trên desktop.
- Lưới: tối đa 12 cột trên desktop, nội dung chính rộng tối đa 1200px, căn giữa. Mobile: 1 cột, ảnh chiếm toàn bộ chiều rộng màn hình.
- Thứ tự 7 section (đúng thứ tự này): (1) hero toàn màn hình, (2) bộ sưu tập lọc 3 nhóm, (3) giới thiệu, (4) quy trình 4 bước, (5) 3 gói giá, (6) nhận xét mẫu, (7) form liên hệ.

Chi tiết từng section:

1. **Hero toàn màn hình:** ảnh kiến trúc chiếm 100% chiều cao màn hình (100vh), tỉ lệ khung 16:9 trên desktop; tiêu đề Fraunces 64px đặt chồng lên ảnh ở góc dưới trái, có lớp phủ tối nhẹ chỉ đủ để chữ `#FFFFFF` đọc được; 1 nút chính màu đất nung `#B4552D` dẫn xuống bộ sưu tập.
2. **Bộ sưu tập lọc 3 nhóm:** 3 nút lọc — Nhà ở, Công trình công cộng, Nội thất (tên 3 nhóm cố định); lưới ảnh 3 cột trên desktop, 1 cột trên mobile; mỗi ảnh tỉ lệ khung 4:3; chú thích 1 dòng (tên công trình + năm) bằng Inter 14px màu `#6B6259`.
3. **Giới thiệu:** 2 cột trên desktop (ảnh chân dung tỉ lệ 3:4 bên trái, tối đa 2 đoạn văn bên phải); mobile xếp dọc, ảnh trước, chữ sau.
4. **Quy trình 4 bước:** 4 ô ngang hàng trên desktop, xếp dọc trên mobile; mỗi ô gồm số thứ tự lớn Fraunces màu `#B4552D`, tên bước, mô tả tối đa 2 câu.
5. **3 gói giá:** 3 thẻ ngang hàng trên desktop, xếp dọc trên mobile; gói giữa nổi bật bằng viền 2px màu `#B4552D` và nhãn "Phổ biến nhất"; mỗi thẻ ghi tên gói, giá, tối đa 5 dòng quyền lợi.
6. **Nhận xét mẫu:** tối đa 3 nhận xét, mỗi nhận xét tối đa 3 câu, ghi rõ là mẫu; nền thẻ `#FFFFFF`, viền 1px màu `#E9DFD3`.
7. **Form liên hệ:** nền `#FFFFFF`; đúng 4 trường — họ tên (bắt buộc), email (bắt buộc), loại công trình (chọn 1 trong 3 nhóm ở section 2), nội dung (tùy chọn); nút gửi màu `#B4552D`; ghi rõ form chỉ là giao diện demo, chưa gửi đi thật.

## 5. Quy tắc hình ảnh

- **Tỉ lệ khung:** hero 16:9 (toàn màn hình); ảnh bộ sưu tập 4:3; ảnh giới thiệu 3:4; ảnh trong thẻ gói giá (nếu có) 16:9.
- **Tông ảnh:** đồng tông sáng ấm — ảnh kiến trúc chụp ban ngày, ánh sáng tự nhiên, độ sáng và độ ấm đồng đều giữa các ảnh; không dùng lọc màu lạnh, không dùng ảnh tối nặng, không dùng ảnh lệch tông rõ rệt trong cùng một lưới.
- **Ảnh mẫu:** từ bản demo đầu tiên, Dev dùng ảnh mẫu chất lượng cao, đồng tông sáng ấm, đúng tỉ lệ khung ở trên; ảnh mẫu phải ghi rõ là ảnh mẫu trong kết quả bàn giao. Khi có ảnh thật của studio, thay đúng vị trí và đúng tỉ lệ khung, không đổi bố cục.
- **Chất lượng:** ảnh không vỡ, không méo (dùng cắt khung đúng tỉ lệ, không kéo giãn); ảnh bộ sưu tập tối thiểu 1200px chiều ngang.
- **Chú thích:** mỗi ảnh bộ sưu tập có đúng 1 dòng chú thích (tên công trình + năm chụp); không viết đoạn dài dưới ảnh.

## 6. Kiểm tra đối chiếu (cho QA và Hỗ trợ)

Bản dựng đạt khi kiểm tra đủ: nền `#FAF7F2` toàn trang; tiêu đề dùng Fraunces, nội dung dùng Inter; điểm nhấn đúng `#B4552D` và không lạm dụng; hero 100vh tỉ lệ 16:9; lưới bộ sưu tập 3 nhóm, ảnh 4:3; 7 section đúng thứ tự; tông ảnh sáng ấm đồng đều; form 4 trường đúng như mục 4.7. Lệch màu chủ đạo, sai font, sai tỉ lệ khung hoặc vỡ bố cục là lỗi cần Dev sửa.
