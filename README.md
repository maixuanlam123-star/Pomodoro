# 🍅 Đồng hồ Pomodoro

Đồng hồ Pomodoro giao diện 3D, cài được lên điện thoại như một app (PWA) và chạy được khi không có mạng.

## Tính năng
- 3 chế độ: Tập trung (25 phút), Nghỉ ngắn (5 phút), Nghỉ dài (15 phút). Đổi được thời lượng.
- Tự chuyển sang nghỉ dài sau mỗi 4 lượt (đổi được).
- 3 âm báo: Chuông, Leng keng, Bíp. Có nút nghe thử. Rung khi hết giờ (Android).
- Thông báo khi hết giờ lúc app đang chạy nền (nếu bạn cho phép).
- Ghi việc đang làm, thống kê số pomodoro và số phút tập trung trong ngày.
- Lưu cài đặt trên máy. Phím Space để bắt đầu/tạm dừng trên máy tính.

## Đưa lên GitHub Pages
1. Tạo repository mới trên GitHub, ví dụ `pomodoro`.
2. Tải toàn bộ file trong thư mục này lên (giữ nguyên thư mục `icons`).
3. Vào **Settings → Pages**. Ở **Source** chọn **Deploy from a branch**, chọn nhánh `main`, thư mục `/ (root)`, bấm **Save**.
4. Sau 1–2 phút, app có ở địa chỉ: `https://<tên-tài-khoản>.github.io/pomodoro/`

## Cài lên điện thoại
- **Android (Chrome):** mở địa chỉ trên → menu ⋮ → **Cài đặt ứng dụng** / **Thêm vào màn hình chính**.
- **iPhone (Safari):** mở địa chỉ trên → nút Chia sẻ → **Thêm vào MH chính**.

## Cập nhật app
Khi sửa file, mở `sw.js` và tăng số phiên bản ở dòng `const CACHE = 'pomodoro-v1'` (thành `v2`, `v3`...). Như vậy máy đã cài sẽ tải bản mới.

## Chạy ngầm (chuông + rung khi đang dùng app khác)
App bật sẵn chế độ **Chạy ngầm**. Khi bấm Bắt đầu, app tạo một file âm thanh gồm khoảng lặng đúng bằng thời gian còn lại, rồi đến tiếng chuông, và phát như nhạc. Nhờ vậy:
- Chuông kêu đúng giờ cả khi tắt màn hình hoặc mở app khác.
- Màn hình khoá / thanh thông báo có điều khiển Tạm dừng – Tiếp tục – Bỏ qua.
- Hết giờ có **thông báo hệ thống kèm rung**. Lần bấm Bắt đầu đầu tiên, hãy chọn **Cho phép** thông báo.

Lưu ý:
- Chuông dùng **âm lượng media**: hãy để âm lượng nhạc đủ lớn (kể cả khi máy để im lặng).
- Đừng vuốt tắt thanh điều khiển nhạc của app, hoặc phát nhạc/video ở app khác cùng lúc. Việc đó sẽ dừng bộ đếm ngầm.
- Một số máy Android (Xiaomi, Oppo, Samsung...) tiết kiệm pin mạnh: vào Cài đặt → Pin → cho Chrome/app Pomodoro **không giới hạn**.
- iPhone: hoạt động tốt nhất khi mở trong Safari. Thông báo cần thêm app vào màn hình chính (iOS 16.4+).

## Cấu trúc
```
index.html            App (HTML + CSS + JS trong một file)
manifest.webmanifest  Thông tin để cài app
sw.js                 Service worker (chạy offline, thông báo)
favicon.png
icons/                Icon app
.nojekyll             Để GitHub Pages phục vụ file nguyên trạng
```
