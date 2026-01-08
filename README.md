# csn-da23tta-nguyenduytan-newsblog-mongodb
# ĐỒ ÁN: THIẾT KẾ VÀ CÀI ĐẶT CƠ SỞ DỮ LIỆU NOSQL CHO HỆ THỐNG BLOG TIN TỨC

## 1. Mô tả tóm tắt 
Đồ án tập trung vào việc thiết kế và cài đặt cơ sở dữ liệu NoSQL (MongoDB) cho hệ thống quản lý nội dung đa phương tiện (Blog/Tin tức). Giải pháp này thay thế các ràng buộc bảng biểu cứng nhắc của SQL truyền thống bằng cấu trúc tài liệu (Document) linh hoạt, cho phép lưu trữ bài viết với nhiều định dạng media và danh mục khác nhau trong cùng một bản ghi, giúp tối ưu hóa tốc độ truy xuất dữ liệu cho người dùng cuối.

---

## 2. Thông tin thực hiện Đồ án
* **Tên đề tài:** Thiết kế và cài đặt CSDL NoSQL cho hệ thống quản lý nội dung đa phương tiện.
* **Cơ sở dữ liệu:** MongoDB (v6.0+).
* **Môi trường thực thi:**
    * **MongoDB Compass:** Giao diện trực quan để quan sát cấu trúc dữ liệu nhúng và quản lý các Collection.

---

## 3. Công nghệ sử dụng
* **Database Engine:** MongoDB - Hỗ trợ lưu trữ dữ liệu nhúng (Embedded) 
* **Query Language:** MongoDB Query Language (MQL) dựa trên định dạng JSON/BSON.
* **Kỹ thuật tối ưu:**
    * **Embedded Data Model:** Nhúng trực tiếp thông tin `Tac_gia` và `Danh_muc` vào tài liệu `BAIVIET` để giảm thiểu các phép Join tốn kém.
    * **Projection:** Kỹ thuật lọc và chỉ trích xuất các trường dữ liệu cần thiết (như Tieu_de, Ho_ten) để tiết kiệm tài nguyên hệ thống và băng thông.

---

## 4. Các tính năng chính đã hoàn thành
1. **Khởi tạo cấu trúc CSDL:** Thiết lập thành công Database `TRANG_TIN_TUC_BLOG`.
2. **Quản lý dữ liệu đa phương tiện:** Lưu trữ thành công mảng `Media_dinh_kem` chứa đường dẫn tệp (`images/iphone16.jpg`) và loại tệp trực tiếp trong bài viết.
3. **Truy vấn nâng cao:**
    * Lọc chính xác các bài viết dựa trên tên tác giả từ đối tượng nhúng.
    * Thực hiện tìm kiếm bài viết theo từ khóa tiêu đề (ví dụ: "Tây Ban Nha") bằng biểu thức chính quy (Regex).
4. **Quản trị và tối ưu hóa:**
    * Nhận diện hiện tượng trùng lặp dữ liệu và áp dụng lệnh xóa bản ghi thừa bằng `deleteOne()`.

---

## 5. Cài đặt

### Bước 1: Khởi tạo Cơ sở dữ liệu
Mở MongoDB Shell (Mongosh) và thực hiện lệnh sau để tạo và bắt đầu làm việc với CSDL của đồ án:
```javascript
use TRANG_TIN_TUC_BLOG

```
### Bước 2: Nhập dữ liệu mẫu
Thực hiện chèn bài viết có cấu trúc dữ liệu nhúng (Tác giả, Danh mục, Media) vào collection BAIVIET:

### Bước 3: Kiểm tra và Truy vấn dữ liệu
Sử dụng các lệnh sau để kiểm tra việc cài đặt đã thành công:

+ Tìm kiếm theo từ khóa (Không phân biệt hoa thường)

+ Lọc thông tin theo Tên Tác giả

## 👤 Thông tin sinh viên
- **Người thực hiện:** Nguyễn Duy Tân
- **Email:** [tannguyentv2005k@gmail.com](mailto:annguyentv2005k@gmail.com)
