# Bài 3 : Sử dụng AI an toàn khi xử lý lỗi phần mềm

**Báo cáo phân tích (IPO):**

1. Input:
- Người dùng nhập câu Câu trả lời và câu lệnh Terminal do AI cung cấp nhằm khắc phục lỗi "Path not found" khi cài đặt Python.
- AI đưa ra câu sudo rm -rf /system/library/framework/python_framework/Version/Current  &&

2. Process: Quy trình kiểm chứng
- Đọc kỹ các câu lệnh của AI như -rf, sudo, rm
- tra cứu web, sử dụng -site:stackoverflow.com "Path not found" để xác định mã nguồn có khớp câu trả lời của AI không

3. Output:
- Nhận diện lệnh sudo rm -rf sẽ xóa trực tiếp file hệ thống, nguy cơ làm hỏng môi trường system của macOS , Xác nhận lệnh không an toàn do Ai bị ảo giác Hallucination.

**Thiết kế một câu lệnh (Prompt) "hỏi ngược lại" AI để yêu cầu nó giải thích độ an toàn của câu lệnh trước khi bạn thực thi:**

- Tôi đang gặp lỗi Path not found khi cài đặt Python. Thì bạn có gửi cho tôi câu lệnh để sửa là: sudo rm-rf/System/Library/Framework/Python.framework/Version/Current  &&. Thì trước khi tôi dùng lệnh này bạn hãy giải thích lại những lệnh này có ý nghĩa gì nó sẽ ra sao đối với hệ điều hành MacOS của tôi. và tại sao câu lệnh này lại giúp giải quyết được lỗi "Path not found" và phương pháp nào khác không