# Tổng quan dự án SmartDiary

SmartDiary là một ứng dụng di động. Ứng dụng hoạt động như một nhật ký, cho phép người dùng nhập một ngày của họ và có thể sử dụng chế độ chatbot để AI đưa ra lời khuyên và phân tích.

Nếu chưa đăng nhập thì người dùng chỉ có một entry duy nhất và không thể xem được lịch sử các nhật ký trước đó. Ngoài ra vào nửa đêm, entry sẽ bị xoá và thay bằng một entry trống. Thêm nữa, người chưa đăng nhập chỉ có 2,000 token cho chatbot.

Nếu đã đăng nhập thì người dùng ngoài lưu lại được entry của mình thì có thể xem được lịch sử các nhật ký trước đó đến 7 ngày. Những entry mà đã vượt quá 7 ngày sẽ bị xoá khỏi dữ liệu. Ngoài ra, người đã đăng nhập sẽ có đến 8,009 chatbot token để sử dụng
