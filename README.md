# Mượn thiết bị câu lạc bộ

Ứng dụng web tiếng Việt để thành viên xem thiết bị, gửi yêu cầu mượn và người phụ trách duyệt.

## Link deploy
https://claude.ai/artifact/GGDgShdUzsSEUAWNXzDJY2

## Chạy
Mở `index.html` bằng trình duyệt, hoặc đưa file này lên bất kỳ dịch vụ host tĩnh nào. Không cần cài đặt.

## Tài khoản người phụ trách
`admin` / `clb2026` (kiểm tra phía trình duyệt, chỉ dùng cho demo).

## Quy tắc nghiệp vụ
- Yêu cầu mới được duyệt tự động khi thiết bị đang Sẵn sàng và không trùng lịch với yêu cầu Đã duyệt/Đang mượn khác; các trường hợp còn lại ở trạng thái Chờ duyệt. Thành viên sửa/xóa được yêu cầu khi còn Chờ duyệt.
- Sau mỗi thay đổi (đổi tình trạng thiết bị, trả, từ chối, xóa), hệ thống quét lại các yêu cầu Chờ duyệt và tự duyệt những yêu cầu đã đủ điều kiện, theo thứ tự gửi. Muốn giữ một yêu cầu không được duyệt, người phụ trách chuyển nó sang Từ chối.
- Chặn trùng lịch lúc duyệt: không chuyển sang Đã duyệt/Đang mượn nếu thiết bị đang bảo trì hoặc trùng thời gian với yêu cầu Đã duyệt/Đang mượn khác trên cùng thiết bị. Trả đúng thời điểm yêu cầu khác bắt đầu cũng tính là trùng.
- Ngày mượn/trả có cả giờ. Dữ liệu mẫu BTC chỉ có ngày nên mặc định 08:00 - 17:00.
- Chuyển yêu cầu sang Đang mượn thì thiết bị tự thành Đang mượn; xác nhận trả thì ghi thời điểm trả và thiết bị về Sẵn sàng. Người phụ trách vẫn sửa tay được tình trạng thiết bị.
- Người phụ trách thêm, sửa, xóa thiết bị; không xóa được thiết bị còn yêu cầu đã duyệt/đang mượn.

## Lưu dữ liệu
- Bản deploy trên claude.ai: dữ liệu dùng chung giữa các máy, cập nhật trực tiếp.
- Chạy ở nơi khác: lưu trong localStorage của trình duyệt.