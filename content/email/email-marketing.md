# Email Marketing — Doanh Nghiệp Thực Chiến AI & Tự Động Hoá

**Sender:** info@sisuai.net  
**Sender Name:** Doanh Nghiệp Thực Chiến AI
**Facebook Group:** https://www.facebook.com/groups/894464020046492

---

## Danh sách email

| # | Email ID | Tên email | Tiêu đề (Subject) | Trigger | Template |
|---|----------|-----------|-------------------|---------|----------|
| 1 | `after-signup-form` | Xác nhận đăng ký | Cảm ơn anh/chị đã đăng ký — Đội ngũ đang đối soát thanh toán! | Sau khi submit Google Form | [1.after-signup-form.html](email-templates/1.after-signup-form.html) |
| 2 | `approved-welcome` | Chào mừng vào cộng đồng | Chúc mừng! Anh/chị đã được duyệt vào cộng đồng 🎉 | Sau khi admin duyệt hồ sơ | [2.approved-welcome.html](email-templates/2.approved-welcome.html) |
| 3 | `rejected-refund` | Từ chối & hoàn tiền | Thông báo về đăng ký tham gia cộng đồng | Sau khi admin đánh giá hồ sơ không phù hợp | [3.rejected-refund.html](email-templates/3.rejected-refund.html) |
| 4 | `payment-reminder` | Nhắc thanh toán | Anh/chị ơi — chỉ còn 1 bước nữa để vào cộng đồng! | Thủ công — khi người đăng ký chưa thanh toán | [4.payment-reminder.html](email-templates/4.payment-reminder.html) |
| 5 | `processing-status` | Đang xử lý đăng ký | Đội ngũ đang xử lý đăng ký của anh/chị — sẽ liên hệ sớm! | Thủ công — khi chưa kịp gọi điện cho người đăng ký | [5.processing-status.html](email-templates/5.processing-status.html) |

---

## Chi tiết từng email

### Email 1: Xác nhận đăng ký (`after-signup-form`)

- **Mục đích:** Xác nhận đã nhận form, cho người đăng ký biết next step (chuẩn bị duyệt)
- **Thời điểm gửi:** Ngay sau khi submit Google Form (tự động)
- **Nội dung chính:**
  - Cảm ơn đã đăng ký
  - Đội ngũ đang tiến hành đối soát thanh toán phí tham gia
  - Thời gian đối soát: trong 24–48 giờ
  - Sẽ nhận được Email Chào Mừng kèm link Facebook Group sau khi xác nhận thành công
  - Nhắc nhở kiểm tra hộp thư Spam/Promotions

---

### Email 2: Chào mừng vào cộng đồng (`approved-welcome`)

- **Mục đích:** Thông báo đã được duyệt, gửi link tham gia Facebook Group
- **Thời điểm gửi:** Sau khi admin hoàn tất cuộc gọi và duyệt hồ sơ
- **Nội dung chính:**
  - Chúc mừng đã được duyệt
  - Link tham gia Facebook Group (private)
  - Giới thiệu nhanh các hoạt động trong group
  - Nhắc cam kết: hoàn tiền 100% trong 1 tháng đầu nếu không phù hợp

---

### Email 3: Từ chối & hoàn tiền (`rejected-refund`)

- **Mục đích:** Thông báo lịch sự rằng hồ sơ chưa phù hợp, xác nhận hoàn tiền
- **Thời điểm gửi:** Sau khi admin đánh giá hồ sơ không phù hợp (thủ công)
- **Nội dung chính:**
  - Cảm ơn đã quan tâm
  - Giải thích cộng đồng dành cho chủ doanh nghiệp / decision maker
  - Nút CTA "Yêu cầu hoàn tiền" → link tới form hoàn tiền (`{{REFUND_FORM_URL}}`)
  - Xác nhận hoàn tiền 100% trong 3–5 ngày làm việc
  - Mở cửa cho tương lai nếu hoàn cảnh thay đổi

---

### Email 4: Nhắc thanh toán (`payment-reminder`)

- **Mục đích:** Nhắc người đã submit form nhưng chưa thanh toán, cung cấp thông tin CK và QR code
- **Thời điểm gửi:** Thủ công, khi phát hiện người đăng ký chưa thanh toán
- **Đính kèm:** QR code thanh toán TPBank (`branding/images/qr-payment-tpbank.png`)
- **Nội dung chính:**
  - Nhắc nhẹ nhàng về việc chưa hoàn tất thanh toán
  - Thông tin chuyển khoản: TPBank / NGUYEN MINH DUC / 09014069303 / 250.000 VNĐ
  - Nội dung CK: Họ tên_SĐT người đăng ký
  - Mã QR để thanh toán nhanh (đính kèm inline)
  - Nếu đã thanh toán: gửi lại thời gian CK + ảnh chụp giao dịch để đối soát

---

### Email 5: Đang xử lý đăng ký (`processing-status`)

- **Mục đích:** Trấn an người đăng ký chưa được liên hệ, thông báo đang xử lý
- **Thời điểm gửi:** Thủ công, khi lượng đăng ký quá nhiều chưa kịp gọi hết
- **Nội dung chính:**
  - Xác nhận đã nhận đăng ký, đội ngũ đang xử lý lần lượt
  - Cam kết sẽ không bỏ sót, sẽ liên hệ sớm
  - Liên hệ hỗ trợ nhanh qua Zalo: 0933 909 366
