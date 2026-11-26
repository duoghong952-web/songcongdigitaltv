# Sông Công TV

Website IPTV tĩnh, có thể triển khai trên Vercel.

## Tính năng
- Tự tải danh sách kênh từ playlist M3U được cấu hình trong `app.js`.
- Phân nhóm theo `group-title`, tìm kiếm, lọc danh mục.
- Trình phát HLS bằng hls.js và phát HLS native khi trình duyệt hỗ trợ.
- Danh sách yêu thích được lưu trong trình duyệt.
- Lựa chọn chất lượng dựa trên các mức thực tế mà playlist HLS cung cấp.
- Liên kết tra cứu lịch VTV.vn và TV360.vn.
- Thiết kế responsive cho máy tính và điện thoại.

## Triển khai
1. Giải nén thư mục dự án.
2. Đưa toàn bộ thư mục `songcongtv` lên một repository GitHub.
3. Đăng nhập Vercel, chọn **Add New → Project**, import repository.
4. Framework Preset: **Other**; Build Command để trống; Output Directory đặt `.`.
5. Deploy. Trong phần Domains của dự án, thêm `songcongtv.vercel.app` nếu tên miền còn khả dụng.

## Lưu ý kỹ thuật
- Website đọc playlist từ GitHub khi mở trang; playlist cập nhật sẽ được phản ánh sau khi tải lại trang.
- Các mức 1080p/720p/480p/360p/240p/144p chỉ chọn được nếu nguồn phát thực sự cung cấp các mức đó. Không thể tự tạo độ phân giải mà nguồn không có.
- Một số luồng có thể không phát trên trình duyệt do CORS, DRM, giới hạn nhà cung cấp, định dạng không tương thích hoặc nguồn đã ngừng hoạt động. Website không giải mã DRM hay vượt giới hạn truy cập.
- Lịch phát sóng được mở tại trang chính thức của VTV và TV360; chưa có API lịch công khai được tích hợp trực tiếp.
- Chỉ sử dụng các luồng mà bạn có quyền truy cập/phát lại và tuân thủ điều khoản của nhà cung cấp.
