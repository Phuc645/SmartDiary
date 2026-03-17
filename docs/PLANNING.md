# Kế hoạch tổng quan

## Giai đoạn 1: Thiết lập

Thiết lập một folder tên SmartDiary. Trong đó chứa file READ.md, một folder tên docs chứa các file gồm DATABASE.md, PLANNING.md và SPEC.md

Thiết lập Git và kết nối với Github

Viết nội dung trong file, cụ thể như sau:

- README: Tổng quan dự án SmartDiary
- SPEC: Đặc tả dự án
- PLANNING: Kế hoạch cho dự án
- DATABASE: Cơ sở dữ liệu

## Giai đoạn 2: Thiết kế

Sử dụng Figma để thiết kế UI/UX cho ứng dụng. Các màn hình cần thiết bao gồm:

- Trang nhật ký
- Trang lịch sử (đăng nhập và chưa đăng nhập)
- Trang tài khoản (đăng nhập và chưa đăng nhập)
- Trang đăng nhập
- Trang đăng ký
- Trang chỉnh sửa thông tin
- Trang lịch sử
- Trang quản lý gói trả phí (nếu chưa mua gói trả phí và đã mua gói trả phí)

Mối màn hình sẽ có phiên bản sáng và tối

Sử dụng cơ chế prototype để kiểm tra user flow

## Giai đoạn 3: Frontend

Thiết lập React Native ở trong project với Expo. Cài thêm thư viện React Native Paper để sử dụng Material UI

Code các màn hình theo yêu cầu

Viết unit test và intergation test bằng Jest và React Native Testing Library

## Giai đoạn 4: Backend

Kết nối với Supabase và Firebase:

- Sử dụng Firebase cho tính năng xác thực bằng Google và Email. Tích hợp AI Logic cho tính năng chatbot
- Sử dụng Firebase cho cơ chể CRUD và lưu trữ cơ sở dữ liệu

## Giai đoạn 5: Hoàn thành

Tạo ra một file APK với tên SmartDiary.apk

Cài thư viện Reanimated 3 cho animation mượt mà hơn

Tạo lại file APK với phiên bản 1.1
