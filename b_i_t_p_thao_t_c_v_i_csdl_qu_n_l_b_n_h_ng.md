# Bài tập: Thao tác với CSDL Quản lý Bán hàng (MySQL)

## Mục tiêu
- Sử dụng được các câu lệnh truy vấn trong MySQL.

## Mô tả
Dựa vào CSDL Quản lý bán hàng, yêu cầu thêm dữ liệu vào trong 4 bảng như dưới đây và thực hiện các câu lệnh truy vấn.

---

### Dữ liệu các bảng

#### 1. Bảng `Customer` (Khách hàng)
| cID (int primary key) | Name (VarChar(25)) | cAge (tinyint) |
| :--- | :--- | :--- |
| 1 | Minh Quan | 10 |
| 2 | Ngoc Oanh | 20 |
| 3 | Hong Ha | 50 |

#### 2. Bảng `Order` (Hóa đơn)
| oID (int primary key) | cID (foreign key tham chiếu tới cID của Customer) | oDate (Datetime) | oTotalPrice (int) |
| :--- | :--- | :--- | :--- |
| 1 | 1 | 2006-03-21 | Null |
| 2 | 2 | 2006-03-23 | Null |
| 3 | 1 | 2006-03-16 | Null |

#### 3. Bảng `Product` (Sản phẩm)
| pID (int primary key) | pName (varchar(25)) | pPrice (int) |
| :--- | :--- | :--- |
| 1 | May Giat | 3 |
| 2 | Tu Lanh | 5 |
| 3 | Dieu Hoa | 7 |
| 4 | Quat | 1 |
| 5 | Bep Dien | 2 |

#### 4. Bảng `OrderDetail` (Chi tiết hóa đơn)
| oID (int foreign key tham chiếu tới oID của Order) | pID (int foreign key tham chiếu tới pID của Product) | odQTY (int - Số lượng) |
| :--- | :--- | :--- |
| 1 | 1 | 3 |
| 1 | 3 | 7 |
| 1 | 4 | 2 |
| 2 | 1 | 1 |
| 3 | 1 | 8 |
| 2 | 5 | 4 |
| 2 | 3 | 3 |

---

## Yêu cầu truy vấn
1. Hiển thị các thông tin gồm `oID`, `oDate`, `oPrice` của tất cả các hóa đơn trong bảng `Order`.
2. Hiển thị danh sách các khách hàng đã mua hàng, và danh sách sản phẩm được mua bởi các khách.
3. Hiển thị tên những khách hàng không mua bất kỳ một sản phẩm nào.
4. Hiển thị mã hóa đơn, ngày bán và giá tiền của từng hóa đơn (giá một hóa đơn được tính bằng tổng giá bán của từng loại mặt hàng xuất hiện trong hóa đơn. Giá bán của từng loại được tính = `odQTY * pPrice`).

---

## Hướng dẫn nộp bài
1. Đưa mã nguồn và bài làm lên GitHub.
2. Dán link GitHub vào phần nộp bài trên hệ thống.