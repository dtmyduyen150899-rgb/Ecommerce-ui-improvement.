# E-commerce UI Improvement

## 1. Giới thiệu
Dự án tập trung cải tiến giao diện người dùng (UI/UX) trên thiết bị di động (Mobile Web) cho website thương mại điện tử bán lẻ rượu vang nhập khẩu **Winemart**. Khu vực trọng tâm được thiết kế lại bao gồm: **Danh mục sản phẩm (Product Catalog)**, **Thanh tìm kiếm & bộ lọc trượt ngang (Sticky Filter & Off-canvas Drawer)**, **Trang chi tiết sản phẩm (PDP)** và **Giỏ hàng (Cart)**.

## 2. Website tham khảo
- **Tên website:** Winemart (Hệ thống phân phối rượu vang & rượu mạnh nhập khẩu)
- **URL:** https://winemart.vn/
- **Khu vực đã khảo sát:** Trang danh mục sản phẩm (Product Listing), bộ lọc thuộc tính rượu (xuất xứ, nồng độ cồn, mức giá), trang chi tiết sản phẩm và luồng thêm vào giỏ hàng trên giao diện điện thoại.

## 3. Chức năng
- **Hiển thị danh sách sản phẩm trực quan:** Hỗ trợ chuyển đổi linh hoạt giữa chế độ Lưới 2 cột (Grid) và Danh sách 1 cột (List).
- **Hiển thị đầy đủ thông tin sản phẩm:** Hình ảnh chai rượu sắc nét, nhãn giảm giá (`-13%`, `-15%`), xuất xứ, dung tích, nồng độ cồn (`ABV`), giá bán ưu đãi, giá gốc gạch ngang và nút thao tác nhanh (`Thêm` vào giỏ / tư vấn `Zalo`).
- **Tìm kiếm & Bộ lọc thông minh:** Thanh tìm kiếm gợi ý tự động (Autocomplete), lọc nhanh theo dòng vang (`Vang Đỏ`, `Vang Trắng`, `Vang Nổ`) và ngăn kéo lọc nâng cao theo quốc gia (`Ý`, `New Zealand`), khoảng giá, nồng độ cồn.
- **Xem chi tiết & Giỏ hàng tương tác:** Phóng to nhãn chai, xem ghi chú hương vị (Tasting Notes) & món ăn kèm, tăng/giảm số lượng và áp dụng mã ưu đãi (`WINEMART10`).
- **Responsive Design:** Hiển thị tốt trên màn hình điện thoại (`430px`) và màn hình máy tính (có khung mô phỏng điện thoại và nút mở rộng toàn màn hình).

## 4. Công nghệ
- **HTML5:** Cấu trúc ngữ nghĩa rõ ràng (`<header>`, `<aside>`, `<article>`, `<select>`, `<input>`).
- **CSS3:** Tách file riêng (`style.css`) quản lý thanh cuộn ẩn, hiệu ứng chuyển động mượt (`@keyframes fadeIn`), đóng khung hình ảnh chuẩn tỷ lệ (`object-fit: contain`), kết hợp utility classes để bố cục linh hoạt.
- **JavaScript (Vanilla JS):** Xử lý dữ liệu sản phẩm tĩnh, lọc/sắp xếp và cập nhật giỏ hàng trực tiếp trên trình duyệt (không sử dụng backend hay cơ sở dữ liệu).

## 5. Cách chạy
1. Giải nén thư mục dự án (đảm bảo giữ nguyên thư mục `images/` và file `style.css` nằm cùng cấp với `index.html`).
2. Mở trực tiếp file `index.html` bằng trình duyệt web bất kỳ (Google Chrome, Microsoft Edge, Safari...).
3. Nhấn nút **"Toàn màn hình"** ở thanh công cụ phía trên hoặc mở **Chrome DevTools (`F12` -> `Toggle Device Toolbar`)** để kiểm tra giao diện ở kích thước máy tính và điện thoại.

## 6. Cải tiến đã thực hiện
- **Vấn đề ban đầu:**
  - Trên màn hình điện thoại, thẻ sản phẩm hiển thị giá bán và giá khuyến mãi chưa nổi bật, nút thao tác chật chội khó bấm bằng một tay.
  - Bộ lọc truyền thống chiếm nhiều diện tích theo chiều dọc, buộc người dùng phải cuộn trang quá dài mới thấy danh sách rượu.
  - Hình ảnh chai rượu có chiều cao lớn dễ bị cắt mất phần cổ chai hoặc nhãn hiệu nếu dùng tỷ lệ khung ảnh thông thường.
- **Thay đổi đã thực hiện:**
  - **Thiết kế lại thẻ sản phẩm (Product Card):** Làm nổi bật giá bán màu đỏ rượu vang (`#722F37`), giá gốc gạch ngang, huy hiệu giảm giá góc trái trên và bố trí cặp nút `Thêm` + `Zalo` ngang hàng dễ thao tác.
  - **Tối ưu không gian di động:** Sử dụng thanh công cụ cố định (`sticky`) kết hợp ngăn kéo lọc trượt ngang (`Off-canvas Filter Drawer`) và các nút chọn danh mục nhanh.
  - **Chuẩn hóa hiển thị ảnh chai rượu:** Sử dụng nền trắng sạch và thuộc tính `object-fit: contain` giúp toàn bộ dáng chai và nhãn hiệu hiển thị trọn vẹn.

## 7. Hỗ trợ từ AI
- **Phần AI hỗ trợ:** Phân tích vấn đề UX trên di động, đề xuất phương án bố cục, tạo khung mã nguồn HTML5/CSS3/JS ban đầu cho 3 màn hình (Danh mục, Chi tiết, Giỏ hàng) và hỗ trợ logic lọc/giỏ hàng.
- **Phần tự kiểm tra, điều chỉnh và bổ sung:**
  - Tinh gọn danh sách sản phẩm mẫu từ 8 sản phẩm hỗn hợp xuống còn **4 sản phẩm rượu vang thực tế** (*Papale Linea Oro*, *Cloudy Bay Sauvignon Blanc*, *Bottega Gold Prosecco*, *Martini Asti Spumante*) để tập trung đúng vào nhóm sản phẩm cốt lõi.
  - Thay thế toàn bộ ảnh mẫu mạng bằng **4 hình ảnh sản phẩm thực tế** trong thư mục `images/` và điều chỉnh CSS (`product-img-contain`) để ảnh không bị cắt xén.
  - Đồng bộ lại bộ đếm trên giao diện (`Tất cả (4)`), loại bỏ các danh mục không còn sản phẩm (Whisky, Cognac, Hộp quà) và cập nhật thông tin liên hệ Zalo tư vấn thực tế.
