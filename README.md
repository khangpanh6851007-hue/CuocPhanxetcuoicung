# Thượng Ngươn Mạt Pháp — Version 3.1 (Local)

## Phiên bản này đã loại bỏ
- Supabase PostgreSQL.
- Supabase Authentication.
- Supabase Edge Functions và toàn bộ cấu hình kết nối Supabase.
- Quy trình tự động xuất bản dựa trên cơ sở dữ liệu Supabase.

## Chế độ hoạt động
Website chạy dạng HTML tĩnh, không cần tài khoản, máy chủ ứng dụng hoặc cơ sở dữ liệu trực tuyến.

Dữ liệu sau được lưu trong `localStorage` của trình duyệt hiện tại:
- Bản nháp và lịch hiển thị bài viết do người dùng tạo.
- Nhật ký tu tập.
- Danh sách bài yêu thích.
- Ngày đã đánh dấu thực hành.
- Bình luận trên thiết bị.
- Sao lưu và phục hồi JSON.

**Lưu ý:** Dữ liệu localStorage chỉ có trên trình duyệt/thiết bị hiện tại. Xóa dữ liệu trình duyệt, đổi thiết bị hoặc dùng trình duyệt khác có thể làm mất dữ liệu. Hãy xuất file sao lưu thường xuyên.

## Bộ 365 bài viết
`content_365.json` chứa 365 bài thực hành mẫu với tiêu đề riêng. Website đã nhúng sẵn dữ liệu này để có thể mở file HTML độc lập.

Các bài là nội dung tu dưỡng phổ quát được biên soạn, không phải trích dẫn nguyên văn kinh điển. Nên biên tập và đối chiếu nguồn trước khi phổ biến.

## Giọng đọc
Dùng SpeechSynthesis của trình duyệt với giọng đọc cài sẵn trên thiết bị. Không có dịch vụ AI voice cloud hoặc đảm bảo có nhiều giọng tiếng Việt trên mọi thiết bị.

## Hỏi đáp
Bản này chỉ có tra cứu mẫu ngoại tuyến, không kết nối AI tạo sinh. Muốn dùng AI trực tuyến mà không có Supabase, cần chọn một máy chủ/backend khác để giữ API key an toàn; không đặt khóa API trong HTML/JavaScript công khai.

## Lịch bài viết
Bài có lịch chỉ được hiển thị khi người dùng mở website sau thời điểm đã chọn. Trang tĩnh không thể tự chạy tác vụ nền hoặc xuất bản khi trình duyệt đóng. Muốn tự động đăng bài thực sự mà không dùng Supabase, cần một dịch vụ lập lịch và nơi lưu trữ nội dung khác (ví dụ GitHub Actions + kho JSON trong repository).

## Triển khai GitHub Pages
1. Đẩy thư mục dự án lên repository GitHub, nhánh `main`.
2. Vào Settings → Pages và chọn GitHub Actions.
3. Workflow `.github/workflows/deploy.yml` triển khai thư mục `public`.
4. Mở URL GitHub Pages của repository.

## Sao lưu
Trong trang Quản trị nội dung, chọn **Xuất sao lưu JSON** để tải dữ liệu cá nhân. Dùng **Nhập sao lưu JSON** để phục hồi trên trình duyệt khác.

## Giới hạn bảo mật
Không có đăng nhập hay phân quyền quản trị trực tuyến. Khu vực quản trị là giao diện cục bộ, không phải cơ chế bảo mật. Không dùng bản này cho dữ liệu nhạy cảm hoặc cộng tác nhiều người dùng.
