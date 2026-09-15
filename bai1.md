# TỔNG HỢP BÀI TẬP SEQUENCE DIAGRAM – RIKKEI

**Ngày hoàn thành:** 15/09/2026  
---

## BÀI 1: VẼ BIỂU ĐỒ TUẦN TỰ – CHỨC NĂNG ĐĂNG NHẬP RIKKEISHOP

### 1. Mục tiêu
- Nhận diện đúng Actor và Object
- Vẽ chính xác Sync, Return, Self và khối `alt`

### 2. Các đối tượng
- **Khách hàng** (Actor)
- **Màn hình UI** (Object)
- **AuthServer** (Object)

### 3. Luồng thông điệp đúng

| Bước | Từ → Đến              | Thông điệp                          | Loại mũi tên |
|------|-----------------------|-------------------------------------|--------------|
| 1    | Khách hàng → UI       | `nhapThongTin(username, password)`  | **Sync**     |
| 2    | UI → AuthServer       | `verifyAccount()`                   | **Sync**     |
| 3    | AuthServer → AuthServer | `checkCredentials()`              | **Self**     |
| 4a   | AuthServer → UI       | Token thành công                    | **Return**   |
| 4b   | UI → Khách hàng       | hiển thị Trang chủ                  | **Return**   |
| 5a   | AuthServer → UI       | lỗi "Sai mật khẩu"                  | **Return**   |
| 5b   | UI → Khách hàng       | hiển thị cảnh báo lỗi               | **Return**   |

