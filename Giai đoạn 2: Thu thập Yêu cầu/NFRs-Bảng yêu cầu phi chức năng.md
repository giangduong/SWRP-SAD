**Các yêu cầu không chức năng (NFRs)**

* **Hiệu suất:**  
  * NFR1: Hệ thống phải hỗ trợ tương tác thời gian thực cho nhiều người dùng đồng thời trong môi trường 3D mà không có độ trễ đáng kể.  
  * NFR2: Nền tảng phải có khả năng mở rộng để chứa một số lượng lớn học sinh và lớp học ngày càng tăng.  
  * NFR3: Thời gian tải cho các môi trường 3D và tài sản phải được tối ưu hóa để có trải nghiệm người dùng mượt mà.  
* **Khả năng mở rộng:**  
  * NFR4: Kiến trúc microservice phải tạo điều kiện thuận lợi cho việc thêm các dịch vụ mới và khả năng mở rộng của các dịch vụ hiện có một cách độc lập.  
  * NFR5: Việc sử dụng các nhà cung cấp đám mây công cộng (AWS/GCP) sẽ đảm bảo khả năng mở rộng theo chiều ngang cho nhu cầu tài nguyên.  
* **Bảo mật:**  
  * NFR6: Tất cả dữ liệu người dùng và thông tin cá nhân phải được bảo vệ bằng các giao thức mã hóa mạnh mẽ.  
  * NFR7: Hệ thống phải tuân thủ các phương pháp bảo mật tốt nhất cho xác thực và ủy quyền (Keycloak).  
  * NFR8: Dữ liệu nhạy cảm (ví dụ: điểm, thông tin cá nhân) phải được bảo vệ khỏi sự truy cập trái phép.  
* **Độ tin cậy/Khả dụng:**  
  * NFR9: Nền tảng phải có thời gian hoạt động tối thiểu là 99.9%.  
  * NFR10: Hệ thống phải có khả năng tự phục hồi và phục hồi sau lỗi dịch vụ với thời gian ngừng hoạt động tối thiểu.  
* **Khả năng bảo trì:**  
  * NFR11: Mã phải được viết rõ ràng, có tài liệu và tuân thủ các tiêu chuẩn mã hóa.  
  * NFR12: Kiến trúc microservice phải đơn giản hóa việc triển khai và cập nhật các thành phần riêng lẻ.  
  * NFR13: Quy trình CI/CD phải tự động hóa các tác vụ bảo trì và triển khai.  
* **Khả năng sử dụng:**  
  * NFR14: Giao diện người dùng phải trực quan, dễ học và sử dụng cho học sinh, giáo viên và quản trị viên.  
  * NFR15: Tài liệu và hỗ trợ phải dễ dàng truy cập và toàn diện.  
* **Tương thích:**  
  * NFR16: Nền tảng phải tương thích với các trình duyệt web phổ biến và các thiết bị khác nhau (máy tính để bàn, thiết bị di động).  
  * NFR17: Các ứng dụng di động được tạo bằng MIT App Inventor phải tương thích với các thiết bị Android và iOS.  
* **Tính toàn vẹn của dữ liệu:**  
  * NFR18: Dữ liệu được lưu trữ trong cơ sở dữ liệu phải chính xác, nhất quán và đáng tin cậy.  
  * NFR19: Các cơ chế sao lưu và phục hồi dữ liệu phải được thực hiện để ngăn ngừa mất dữ liệu.
 
---

Bảng yêu cầu phi chức năng (Sample)

| Hạng mục | Yêu cầu Phi chức năng | Chỉ số đo lường (Metric) | Giá trị mục tiêu (Target Value) | Lý do/Ghi chú |
| :---- | :---- | :---- | :---- | :---- |
| Hiệu suất | Tải trang khóa học | Time to Interactive (TTI) | \< 3 giây | Để giữ chân người dùng |
| Khả năng mở rộng | Sự kiện Robothon | Người dùng đồng thời | 10,000 users | Hỗ trợ các cuộc thi quy mô lớn |
| Tính sẵn sàng | Dịch vụ học tập cốt lõi | Uptime (SLA) | 99.9% (trong giờ 7am-10pm) | Đảm bảo không gián đoạn việc học |
| Bảo mật | Dữ liệu cá nhân của học sinh | Tuân thủ (Compliance) | COPPA & GDPR | Bắt buộc về mặt pháp lý |
