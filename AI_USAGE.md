# AI Usage Log

## 1. Công cụ AI
- **Tên công cụ:** Google Gemini

## 2. Mục đích sử dụng
- Phân tích hạn chế giao diện di động hiện tại của website Winemart (Bước 1).
- Đề xuất phương án bố cục, cấu trúc thẻ HTML5, cách tổ chức CSS3 và các tiêu chí kiểm tra khả năng sử dụng (Bước 2).
- Hỗ trợ tạo mã nguồn giao diện thương mại điện tử tách riêng file HTML và CSS (Bước 3).
- Hỗ trợ chỉnh sửa, tinh gọn dữ liệu sản phẩm và tối ưu hiển thị hình ảnh cục bộ sau khi tự kiểm tra (Bước 4).

## 3. Prompt đã sử dụng
- **Prompt Bước 2 (Đề xuất giao diện):**
  > "Tôi đang thực hiện bài tập phát triển giao diện website thương mại điện tử bằng HTML5 và CSS3. Tôi muốn cải tiến khu vực: danh mục sản phẩm, thanh tìm kiếm/bộ lọc, chi tiết sản phẩm và giỏ hàng trên di động của website Winemart. Đối tượng sử dụng: khách hàng mua sắm trực tuyến tại Việt Nam. Hãy đề xuất: 1. Bố cục giao diện. 2. Các thành phần HTML cần sử dụng. 3. Cách tổ chức CSS. 4. Cách hiển thị trên máy tính và điện thoại. 5. Những điểm cần kiểm tra về khả năng sử dụng. Trước tiên, hãy giải thích phương án thiết kế. Chưa tạo toàn bộ mã nguồn cho đến khi tôi yêu cầu."
- **Prompt Bước 3 (Tạo mã nguồn):**
  > "Dựa trên phương án đã thống nhất, hãy tạo một trang giao diện thương mại điện tử bằng HTML5 và CSS3. Yêu cầu: Giao diện có tiêu đề và khu vực sản phẩm; Có tối thiểu 4 sản phẩm mẫu; Mỗi sản phẩm có hình ảnh, tên, giá và nút thao tác; Bố cục phù hợp với màn hình máy tính và điện thoại; Mã HTML có cấu trúc rõ ràng; CSS được tách thành file riêng; Không sử dụng backend hoặc cơ sở dữ liệu; Không đưa thư viện hoặc thành phần không cần thiết vào dự án. Giải thích cách chạy trang web và những phần tôi cần kiểm tra."
- **Prompt Bước 4 (Điều chỉnh theo thực tế kiểm tra):**
  > "Bỏ 4 sản phẩm rượu mạnh và hộp quà Tết dư thừa, chỉ giữ lại 4 sản phẩm rượu vang kèm hình ảnh thực tế trong thư mục images/, đồng thời cập nhật lại bộ lọc và số lượng hiển thị cho khớp."

## 4. Kết quả AI đề xuất
- AI đề xuất giải pháp thiết kế theo hướng **Mobile-First** với khung hiển thị chuẩn `430px` (kèm nút mở rộng toàn màn hình khi xem trên máy tính), bảng màu đặc trưng ngành rượu vang (`#722F37`, `#D4AF37`, `#F9F9F6`).
- Cung cấp mã nguồn gồm file `index.html` có cấu trúc ngữ nghĩa rõ ràng và file `style.css` tách biệt, tích hợp ngăn kéo bộ lọc trượt ngang, chuyển đổi chế độ xem Lưới/Danh sách, trang chi tiết sản phẩm và giỏ hàng tính tiền tự động.

## 5. Kiểm tra và điều chỉnh
- **Quá trình kiểm tra:** Mở `index.html` trên Google Chrome, sử dụng Chrome DevTools (`F12`) kiểm tra ở các độ phân giải điện thoại (iPhone 12/14 Pro, Pixel) và chế độ toàn màn hình trên máy tính.
- **Những điểm đã tự điều chỉnh:**
  1. **Tinh gọn danh sách sản phẩm:** Bản đầu AI tạo 8 sản phẩm gồm cả Whisky, Cognac và Hộp quà Tết dùng ảnh mẫu mạng. Tôi đã quyết định loại bỏ 4 sản phẩm đó, chỉ giữ lại **4 sản phẩm rượu vang tiêu biểu** để giao diện đồng nhất và gọn gàng hơn.
  2. **Sửa lỗi cắt khung hình ảnh chai rượu:** Do chai rượu có chiều cao lớn, thuộc tính `object-fit: cover` làm mất phần cổ chai và logo. Tôi đã tự đưa 4 ảnh thực tế vào thư mục `images/` và chuyển sang class `product-img-contain` (`object-fit: contain`) trên nền trắng.
  3. **Đồng bộ bộ đếm và danh mục lọc:** Chỉnh sửa nhãn từ `Tất cả (8)` thành `Tất cả (4)`, xóa các nút danh mục không dùng đến và cập nhật dải nồng độ cồn thành `7.5% – 15%`.

## 6. Phần tôi hiểu và có thể giải thích
- **Cấu trúc HTML5 (`index.html`):**
  - Thẻ `<header>` giữ thanh tìm kiếm Autocomplete và nút giỏ hàng cố định ở đầu trang (`shrink-0`).
  - Các màn hình chức năng (`#screen-catalog`, `#screen-detail`, `#screen-cart`) được tách thành các khối độc lập và chuyển đổi mượt mà bằng JavaScript (`navigateTo()`).
  - Thẻ `<article>` bao bọc từng thẻ sản phẩm, phân cấp rõ ràng: huy hiệu giảm giá -> hình ảnh -> xuất xứ/phân loại -> tên rượu -> dung tích/nồng độ -> giá bán/giá gốc -> cụm nút thao tác (`Thêm` và `Zalo`).
  - Thẻ `<aside id="filterDrawer">` đóng vai trò ngăn kéo bộ lọc trượt ngang, giúp tiết kiệm diện tích hiển thị trên màn hình nhỏ.
- **Tổ chức CSS3 (`style.css`):**
  - Tách riêng phần CSS tùy chỉnh sang file `style.css` và liên kết qua thẻ `<link rel="stylesheet" href="style.css">`.
  - Phân biệt rõ tác dụng của `.product-img-contain` (`object-fit: contain` giữ nguyên tỷ lệ chai rượu, không cắt xén) và `.product-img-cover` (`object-fit: cover` lấp đầy khung).
  - Nắm được cách tạo hiệu ứng trượt ngăn kéo bộ lọc bằng `transform: translateX(100%)` kết hợp `transition: transform 0.3s cubic-bezier(...)` và cách ẩn thanh cuộn ngang (`.no-scrollbar`).
