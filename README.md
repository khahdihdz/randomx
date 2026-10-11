# RandomX

**RandomX** là website tiếng Việt hỗ trợ quay số, bốc thăm tên và chọn mục ngẫu nhiên. Website chạy hoàn toàn trên trình duyệt, không cần backend hay API trả phí.

## Tính năng

- Quay số trong một khoảng số nguyên.
- Bốc thăm tên hoặc danh sách tùy chỉnh.
- Chọn có hoặc không cho phép trùng kết quả.
- Tùy chọn loại tên trùng.
- Chế độ chọn theo trọng số cho danh sách tên.
- Lưu cấu hình và lịch sử gần đây trong `localStorage`.
- Sao chép kết quả, xuất lịch sử CSV và in kết quả.
- Giao diện sáng/tối, tương thích màn hình di động.
- GitHub Actions tự động triển khai lên GitHub Pages khi push lên `main`.

## Sử dụng

1. Mở website RandomX.
2. Chọn **Quay số**, **Quay tên** hoặc **Danh sách**.
3. Nhập khoảng số hoặc dán danh sách (mỗi dòng một mục).
4. Điều chỉnh số lượng kết quả và các tùy chọn.
5. Nhấn **Bắt đầu quay**.
6. Sao chép, xuất CSV hoặc in kết quả khi cần.

### Chế độ trọng số

Bật **Quay theo trọng số** rồi nhập một trọng số cho mỗi dòng, theo đúng thứ tự danh sách. Trọng số phải hữu hạn, không âm và có ít nhất một trọng số lớn hơn 0. Trọng số lớn hơn tương ứng xác suất được chọn cao hơn. Nếu bật không trùng, các mục đã chọn sẽ bị loại khỏi lượt chọn tiếp theo.

## Chạy tại máy

Dự án là website tĩnh, không cần cài dependency.

Có thể mở `index.html` trực tiếp hoặc chạy máy chủ HTTP cục bộ, ví dụ:

```bash
python -m http.server 8000
```

Sau đó truy cập `http://localhost:8000`.

## Triển khai GitHub Pages

Workflow tại `.github/workflows/deploy.yml` chạy khi push lên nhánh `main` hoặc được kích hoạt thủ công.

1. Mở **Settings → Pages** trong repository.
2. Nếu cần chọn nguồn triển khai, chọn **GitHub Actions**.
3. Mở tab **Actions**, chọn workflow **Deploy RandomX to GitHub Pages** và kiểm tra trạng thái.
4. Khi job deploy thành công, lấy URL từ phần deployment của workflow hoặc Settings → Pages.

URL dự kiến của repository công khai này là:

`https://khahdihdz.github.io/randomx/`

URL chỉ hoạt động sau khi GitHub Pages được bật và workflow triển khai thành công.

## Quyền riêng tư và giới hạn

- Danh sách, cấu hình và lịch sử được lưu trong bộ nhớ cục bộ của trình duyệt. Chúng không tự động đồng bộ giữa các thiết bị.
- Xóa dữ liệu website trong trình duyệt có thể xóa lịch sử đã lưu.
- Website dùng `crypto.getRandomValues()` và rejection sampling để lấy số nguyên ngẫu nhiên không lệch modulo trong các phép chọn số.
- Hiệu ứng quay chỉ trình bày kết quả đã chọn; không quyết định kết quả.
- Chế độ trọng số cố ý tạo xác suất không đồng đều.
- RandomX không phải hệ thống quay thưởng có kiểm toán độc lập; không nên xem kết quả trên trình duyệt là bằng chứng chống gian lận cho chương trình có giá trị pháp lý hoặc tài chính cao.

## Công nghệ

HTML, CSS và JavaScript thuần; GitHub Actions và GitHub Pages.

## Mã nguồn

https://github.com/khahdihdz/randomx
