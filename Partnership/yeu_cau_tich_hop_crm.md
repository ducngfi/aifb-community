# 📋 Yêu cầu Tích hợp Dữ liệu Thành viên vào Master CRM

**Người phụ trách:** Project Manager  
**Ngày:** 26/03/2026  
**Gửi đến:** Vendor phụ trách website & Nhóm Admin

---

## 1. Bối cảnh & Mục tiêu

Hiện tại tổ chức đang quản lý 2 nguồn dữ liệu quan trọng:

| Nguồn | Mô tả | Trạng thái |
|---|---|---|
| **Danh sách Lead** | Doanh nghiệp thu thập từ webinar & BTC tổng hợp | Google Sheet – cập nhật thủ công |
| **Thành viên Cộng đồng** | Người đăng ký tham gia cộng đồng qua website | Website – chưa kết nối CRM |

**Mục tiêu:** Xây dựng **Master CRM tự động** – nơi mọi thành viên mới từ website được đồng bộ thời gian thực, kết hợp với danh sách lead, để đội Partnership có thể theo dõi và thúc đẩy deal hiệu quả.

---

## 2. Yêu cầu Nghiệp vụ (Business Requirements)

### 2.1 Tự động đồng bộ dữ liệu thành viên mới
- Mỗi khi có thành viên mới đăng ký trên website → **tự động thêm vào Master CRM** (không cần thao tác thủ công)
- Dữ liệu phải được cập nhật **trong vòng tối đa 15 phút** sau khi đăng ký

### 2.2 Các trường dữ liệu cần thu thập từ website

| Trường | Bắt buộc | Ghi chú |
|---|---|---|
| Họ và tên | ✅ | |
| Email | ✅ | Dùng làm khóa định danh chính |
| Số điện thoại | ✅ | |
| Tên công ty | ✅ | |
| Chức vụ / Vai trò | ✅ | |
| Ngành nghề | ✅ | |
| Quy mô công ty | 🔲 Khuyến nghị | Dưới 10 / 10–50 / 50–200 / 200+ |
| Bài toán đang quan tâm | 🔲 Khuyến nghị | Multi-select hoặc text tự do |
| Ngày đăng ký | ✅ | Tự động từ hệ thống |

### 2.3 Không trùng lặp dữ liệu
- Hệ thống phải **kiểm tra email trùng** trước khi thêm mới
- Nếu trùng → cập nhật bản ghi hiện có, **không tạo bản ghi mới**

### 2.4 Phân loại nguồn
- Mỗi bản ghi phải được gắn nhãn `Nguồn = "Community"` để phân biệt với lead từ webinar/BTC

---

## 3. Câu hỏi cần Vendor trả lời

> [!IMPORTANT]
> Vendor vui lòng trả lời các câu hỏi dưới đây để đội kỹ thuật có thể thiết kế giải pháp tích hợp phù hợp.

1. **Website đang dùng nền tảng/CMS gì?**  
   *(WordPress, custom build, Webflow, v.v.)*

2. **Dữ liệu thành viên được lưu ở đâu?**  
   *(Database riêng, plugin quản lý thành viên, bên thứ 3?)*

3. **Website hiện có hỗ trợ Webhook không?**  
   *(Khi có thành viên mới đăng ký, hệ thống có thể gửi dữ liệu tự động ra ngoài không?)*

4. **Có API công khai hoặc API nội bộ để truy vấn danh sách thành viên không?**  
   *(Cần tài liệu API nếu có)*

5. **Có thể export danh sách thành viên định kỳ (CSV/JSON) không?**  
   *(Phương án dự phòng nếu không có webhook/API)*

6. **Form đăng ký thành viên hiện thu thập những trường nào?**  
   *(Đối chiếu với yêu cầu mục 2.2)*

7. **Có thể thêm trường mới vào form đăng ký không?**  
   *(Ví dụ: Quy mô công ty, Bài toán quan tâm)*

---

## 4. Kiến trúc Kỹ thuật Đề xuất

```
Thành viên đăng ký trên Website
         ↓
   Webhook / API trigger (từ website)
         ↓
   Automation tool: Make.com hoặc Zapier
         ↓  (chuẩn hóa + kiểm tra trùng)
   Master CRM (Google Sheet / Notion / HubSpot)
         ↓
   Auto Lead Scoring (formula tự động)
         ↓
   ┌─────────────────────────────────┐
   │ Hot Lead  → Alert Zalo cho Sales│
   │ Warm Lead → Vào chuỗi nurture   │
   │ Cold Lead → Newsletter tự động  │
   └─────────────────────────────────┘
```

### Công cụ tích hợp đề xuất

| Phương án | Công cụ | Chi phí | Phù hợp khi |
|---|---|---|---|
| **Ưu tiên 1** | Make.com | ~$9/tháng | Website có Webhook hoặc API |
| **Ưu tiên 2** | Zapier | ~$20/tháng | Dễ dùng, tích hợp nhanh |
| **Ưu tiên 3** | Google Apps Script | Miễn phí | Website có thể export CSV định kỳ |

---

## 5. Checklist thống nhất với Admin

- [ ] Xác nhận nền tảng website và khả năng tích hợp (vendor phản hồi)
- [ ] Đồng ý danh sách trường dữ liệu cần thu thập (mục 2.2)
- [ ] Cập nhật form đăng ký thành viên nếu thiếu trường
- [ ] Chọn nơi lưu Master CRM: Google Sheet / Notion / HubSpot Free
- [ ] Phân công người phụ trách vận hành CRM hàng ngày
- [ ] Thống nhất quy trình xử lý Hot Lead (ai nhận alert? xử lý trong bao lâu?)
- [ ] Thống nhất tần suất review và làm sạch dữ liệu (đề xuất: mỗi 2 tuần)

---

## 6. Bước triển khai (sau khi có phản hồi từ Vendor)

| Tuần | Việc cần làm |
|---|---|
| Tuần 1 | Vendor xác nhận phương án kỹ thuật → Setup automation tool |
| Tuần 1 | Import toàn bộ dữ liệu thành viên hiện có vào Master CRM |
| Tuần 2 | Kết nối website → CRM, test với 10 đăng ký thử |
| Tuần 2 | Cấu hình Lead Scoring + phân luồng tự động |
| Tuần 3 | Go-live, training admin sử dụng CRM |

