# 📂 Members — Thành viên & Onboarding

> Luồng 3 + 4: Onboarding Flow + Quản lý 3 loại thành viên

## 3 loại thành viên

| Loại                  | Mô tả                                          | Icon |
| --------------------- | ---------------------------------------------- | ---- |
| **Doanh nghiệp**      | Chủ DN / C-Level muốn ứng dụng AI & Automation | 🏢    |
| **Solution Provider** | Nhà cung cấp giải pháp AI & Automation         | 🛠️    |
| **Reviewer**          | Chuyên gia đánh giá, so sánh giải pháp         | 🔍    |

→ Chi tiết: [`member-types.md`](member-types.md) (cần tạo)

## Cấu trúc

| Thư mục                            | Mô tả                           |
| ---------------------------------- | ------------------------------- |
| `onboarding/`                      | SOP tiếp nhận thành viên mới    |
| `onboarding/call-scripts.md`       | Kịch bản gọi điện (3 loại user) |
| `onboarding/screening-criteria.md` | Tiêu chí sàng lọc               |
| `onboarding/payment-flow.md`       | Luồng nạp/hoàn tiền             |
| `onboarding/email-templates/`      | Email accept, reject, refund    |
| `directory/`                       | Danh bạ thành viên              |

## Luồng Onboarding

```
Form đăng ký → Thanh toán 250k → Admin gọi xác minh
         ↓                                  ↓
    Chưa thanh toán              ┌── Accept → Add vào FB Group
         ↓                      └── Reject → Hoàn tiền 100%
    Email nhắc nhở
```

## Owner

**COO** sở hữu toàn bộ luồng onboarding.
