Bước **2.2: Tổ chức workshop thu thập yêu cầu phi chức năng (NFRs)**.

Nếu bước 2.1 cần sự nhạy bén về sản phẩm, thì bước 2.2 đòi hỏi tư duy hệ thống, kinh nghiệm kỹ thuật và khả năng lường trước tương lai. Kết quả của bước này sẽ định hình bộ xương của toàn bộ giải pháp kiến trúc.

### **Quy trình và Cách thức thực hiện Bước 2.2**

#### **Mục tiêu chính:**

* **Định lượng Chất lượng:** Chuyển đổi các khái niệm chất lượng mơ hồ (như "nhanh", "an toàn", "ổn định") thành các chỉ số có thể đo lường và kiểm chứng được (quantifiable metrics).  
* **Xác định các Ràng buộc Kỹ thuật:** Ghi nhận các giới hạn về công nghệ, chi phí, và vận hành mà kiến trúc phải tuân thủ.  
* **Làm rõ các Trade-offs:** Hiểu và thống nhất về những sự đánh đổi. Ví dụ: Tăng tính sẵn sàng (availability) thường đi đôi với việc tăng chi phí.  
* **Tạo ra Giao phẩm:** Hoàn thành "Danh sách các Yêu cầu Phi chức năng (NFRs)" chi tiết, làm cơ sở cho việc thiết kế kiến trúc.

---

### **A. Chuẩn bị TRƯỚC workshop (Công việc của CTO Giang)**

Đây là bước ông Giang chủ động dẫn dắt và chuẩn bị.

1. **Nghiên cứu Đầu vào:**  
   * **Nghiên cứu kỹ lưỡng kết quả của bước 2.1:** Đọc lại Tài liệu Yêu cầu Kinh doanh (BRD) và các User Story. Gạch chân những cụm từ có thể ám chỉ đến NFRs.  
   * Ví dụ:  
     * User story "Tôi muốn cộng tác thời gian thực với bạn bè trong TwinSpace" \=\> Gợi ý yêu cầu về **độ trễ (latency)** thấp và **số lượng người dùng đồng thời (concurrency)** cao.  
     * Yêu cầu "Nền tảng sẽ tổ chức các cuộc thi Robothon toàn quốc" \=\> Gợi ý yêu cầu về **khả năng chịu tải đột biến (peak load)** và **khả năng mở rộng (scalability)**.  
2. **Xây dựng Khung sườn Thảo luận (Framework):**  
   * Đừng bước vào workshop với một trang giấy trắng. Ông Giang cần chuẩn bị một danh sách các hạng mục NFRs (còn gọi là các "-ilities") để dẫn dắt buổi thảo luận. Dưới đây là khung sườn gợi ý cho Pythaverse:  
     * **Hiệu suất (Performance):**  
       * *Độ trễ phản hồi (Response Time/Latency):* Thời gian từ lúc người dùng thao tác đến khi hệ thống phản hồi là bao lâu? (Ví dụ: Tương tác trong TwinSpace phải dưới 200ms).  
       * *Lưu lượng (Throughput):* Hệ thống xử lý được bao nhiêu yêu cầu/giây? (Ví dụ: API xác thực người dùng phải xử lý được 500 yêu cầu/giây).  
     * **Khả năng mở rộng (Scalability):**  
       * *Người dùng đồng thời (Concurrent Users):* Hệ thống hỗ trợ bao nhiêu người dùng cùng lúc? (Ví dụ: 10,000 học sinh tham gia một sự kiện trực tiếp).  
       * *Tăng trưởng dữ liệu (Data Growth):* Dự kiến dữ liệu sẽ tăng bao nhiêu GB/tháng?  
     * **Tính sẵn sàng (Availability):**  
       * *Thời gian hoạt động (Uptime/SLA):* Cam kết hệ thống hoạt động bao nhiêu % thời gian? (Ví dụ: 99.9% trong giờ hành chính, tương đương khoảng 43 phút downtime/tháng).  
       * *Thời gian phục hồi (RTO/RPO):* Nếu sự cố xảy ra, mất bao lâu để hệ thống hoạt động lại (RTO)? Và lượng dữ liệu bị mất tối đa là bao nhiêu (RPO)?  
     * **Bảo mật (Security):**  
       * *Bảo vệ dữ liệu:* Hệ thống cần tuân thủ các tiêu chuẩn nào? (COPPA, GDPR \- đặc biệt quan trọng với dữ liệu trẻ em). Dữ liệu nhạy cảm phải được mã hóa.  
       * *Xác thực & Phân quyền:* Phương thức đăng nhập là gì? Phân quyền truy cập ra sao?  
     * **Khả năng vận hành & bảo trì (Operability & Maintainability):**  
       * *Giám sát (Monitoring):* Chúng ta cần theo dõi những chỉ số nào để biết hệ thống đang "khỏe"?  
       * *Triển khai (Deployment):* Thời gian để triển khai một phiên bản mới là bao lâu? Có thể rollback nhanh chóng không?  
     * **Chi phí (Cost):**  
       * Ngân sách dự kiến cho hạ tầng cloud hàng tháng là bao nhiêu?  
3. **Chuẩn bị câu hỏi gợi mở và gửi trước tài liệu:**  
   * Gửi Agenda và khung sườn thảo luận NFRs cho những người tham gia (Tech Leads, DevOps, Security) trước 1-2 ngày.  
   * Yêu cầu họ xem lại tài liệu yêu cầu từ bước 2.1 và suy nghĩ trước về các NFRs từ góc nhìn chuyên môn của họ.

---

### **B. TRONG workshop (Vai trò của CTO Giang là người điều phối)**

1. **Bắt đầu bằng Bối cảnh Kinh doanh:**  
   * Dành 5 phút đầu để nhắc lại các mục tiêu kinh doanh quan trọng nhất đã xác định ở bước 2.1. Điều này giúp đội ngũ kỹ thuật hiểu rằng NFRs không phải là những con số vô hồn, mà chúng tồn tại để **phục vụ mục tiêu kinh doanh**.  
2. **Đi theo Khung sườn đã chuẩn bị:**  
   * Dẫn dắt cuộc thảo luận đi qua từng hạng mục: Performance, Scalability, Availability... Điều này giúp cuộc thảo luận có cấu trúc và không bỏ sót các khía cạnh quan trọng.  
3. **Nghệ thuật Định lượng hóa (The Art of Quantification):**  
   * Đây là kỹ năng quan trọng nhất của ông Giang trong buổi này. Liên tục đẩy đội ngũ ra khỏi vùng an toàn của những từ ngữ định tính.  
   * **Khi ai đó nói:** "Hệ thống phải nhanh."  
     * **Ông Giang hỏi:** "Nhanh là bao nhiêu? Với người dùng cuối, hành động X phải hoàn thành trong bao lâu thì được coi là nhanh? 1 giây? 500ms? Chúng ta đo lường ở phân vị thứ 95 (p95) hay trung bình?"  
   * **Khi ai đó nói:** "Hệ thống phải chịu được tải lớn."  
     * **Ông Giang hỏi:** "Tải lớn vào lúc nào? Lớn là bao nhiêu người dùng đồng thời? 1,000 hay 50,000? Họ thực hiện hành động gì khi đó?"  
   * **Khi ai đó nói:** "Hệ thống phải luôn hoạt động."  
     * **Ông Giang hỏi:** "SLA 99.999% (5 phút downtime/năm) sẽ tốn kém hơn rất nhiều so với 99.9% (gần 9 tiếng downtime/năm). Mục tiêu kinh doanh có thực sự yêu cầu mức độ sẵn sàng đó không? Hay chúng ta có thể chấp nhận downtime vào nửa đêm?"  
4. **Làm rõ các Trade-offs:**  
   * Chủ động đưa ra các kịch bản đánh đổi để mọi người cùng thảo luận và đưa ra quyết định. "Để đạt được độ trễ dưới 100ms, chúng ta có thể phải dùng một dịch vụ database đắt tiền hơn gấp 3 lần. Mọi người nghĩ sao?"  
5. **Ghi lại mọi thứ:**  
   * Chỉ định một người làm thư ký hoặc tự mình ghi chép lên bảng trắng/Miro. Việc trực quan hóa các con số và quyết định giúp mọi người có chung một cái nhìn.

---

### **C. SAU workshop (Hoàn thiện Giao phẩm)**

1. **Tổng hợp và Chuẩn hóa:**  
   * Tập hợp tất cả ghi chú từ workshop vào một tài liệu có cấu trúc. Cách tốt nhất là tạo một bảng.

| Hạng mục | Yêu cầu Phi chức năng | Chỉ số đo lường (Metric) | Giá trị mục tiêu (Target Value) | Lý do/Ghi chú |
| :---- | :---- | :---- | :---- | :---- |
| Hiệu suất | Tải trang khóa học | Time to Interactive (TTI) | \< 3 giây | Để giữ chân người dùng |
| Khả năng mở rộng | Sự kiện Robothon | Người dùng đồng thời | 10,000 users | Hỗ trợ các cuộc thi quy mô lớn |
| Tính sẵn sàng | Dịch vụ học tập cốt lõi | Uptime (SLA) | 99.9% (trong giờ 7am-10pm) | Đảm bảo không gián đoạn việc học |
| Bảo mật | Dữ liệu cá nhân của học sinh | Tuân thủ (Compliance) | COPPA & GDPR | Bắt buộc về mặt pháp lý |

1. **Gửi rà soát và Lấy xác nhận:**  
   * Gửi tài liệu NFRs đã được chuẩn hóa cho tất cả những người đã tham gia workshop để họ rà soát lại lần cuối.  
   * Sau khi nhận được sự đồng thuận, đây sẽ là **"Danh sách các NFRs đã được phê duyệt"**.

Tài liệu này, cùng với tài liệu yêu cầu chức năng từ bước 2.1, sẽ là hai bản đồ sao cực kỳ quan trọng, soi đường cho ông Giang và đội ngũ trong suốt Giai đoạn 3: Soạn thảo Kiến trúc.  
