Bước **1.3: Lựa chọn công cụ và thiết lập quy trình làm việc** sẽ trả lời câu hỏi "làm việc ở đâu và như thế nào?".

Đây là bước nền tảng về mặt kỹ thuật và quy trình, giúp toàn bộ quá trình soạn thảo, rà soát và lưu trữ tài liệu diễn ra một cách có tổ chức, nhất quán và hiệu quả.

### **Quy trình và Cách thức thực hiện Bước 1.3**

#### **Mục tiêu chính:**

* **Tập trung hóa thông tin:** Tạo ra một "Nguồn sự thật duy nhất" (Single Source of Truth) cho Tài liệu Kiến trúc Giải pháp, tránh việc có nhiều phiên bản trôi nổi qua email hoặc các file cục bộ.  
* **Tăng cường cộng tác:** Cho phép các bên liên quan dễ dàng xem, bình luận và đóng góp vào tài liệu một cách minh bạch.  
* **Đảm bảo tính nhất quán:** Thiết lập một cấu trúc (template) chuẩn cho tài liệu để mọi người tuân theo.  
* **Thiết lập kênh giao tiếp rõ ràng:** Quy định rõ các kênh trao đổi thông tin để tránh nhiễu loạn.

---

### **A. Các Quyết định Chính cần Đưa ra**

Trước khi bắt tay vào thiết lập, ông Giang cần đưa ra vài quyết định quan trọng cùng với các Tech Lead:

**1\. Quyết định về Nền tảng Soạn thảo & Lưu trữ (Editing & Storage Platform):**

* **Lựa chọn 1: Confluence (Khuyến nghị):**  
  * *Ưu điểm:* Rất mạnh mẽ trong việc xây dựng tài liệu tri thức nội bộ. Dễ dàng tạo cấu trúc phân cấp, quản lý phiên bản, phân quyền chi tiết và tích hợp sâu với Jira (nếu Pythaverse đang dùng). Phù hợp cho các "tài liệu sống" (living documents).  
  * *Nhược điểm:* Tính năng soạn thảo và cộng tác theo thời gian thực không linh hoạt bằng Google Docs.  
* **Lựa chọn 2: Google Docs trong Google Drive:**  
  * *Ưu điểm:* Cực kỳ dễ sử dụng, tính năng bình luận, gợi ý và cộng tác theo thời gian thực xuất sắc. Hầu như không cần đào tạo.  
  * *Nhược điểm:* Khó quản lý cấu trúc và phiên bản cho một tài liệu lớn, phức tạp như SAD. Dễ bị lộn xộn nếu không có quy tắc tổ chức thư mục chặt chẽ.  
* **Lựa chọn 3: Docs-as-Code (ví dụ: Markdown trong Git):**  
  * *Ưu điểm:* Được các kỹ sư yêu thích. Quản lý phiên bản hoàn hảo qua Git. Có thể tích hợp vào quy trình CI/CD.  
  * *Nhược điểm:* Rào cản lớn cho các bên liên quan không rành kỹ thuật (CEO, Product, Business). Họ sẽ khó tham gia góp ý.

**\=\> Đề xuất của tôi:** Ông Giang nên chọn **Confluence** vì nó cân bằng được giữa cấu trúc, quản lý và khả năng cộng tác, phù hợp nhất với một tài liệu kỹ thuật quan trọng như SAD.

**2\. Quyết định về Công cụ Vẽ Sơ đồ (Diagramming Tool):**

* **Lựa chọn:** Lucidchart, Miro, Draw.io (nay là diagrams.net).  
* **Tiêu chí:** Cần chọn công cụ có khả năng tích hợp (embed) trực tiếp vào nền tảng đã chọn (Confluence/Google Docs) để sơ đồ luôn được cập nhật. Draw.io là một lựa chọn miễn phí và rất mạnh mẽ, tích hợp tốt với Confluence.

**3\. Quyết định về Kênh Giao tiếp (Communication Channel):**

* **Slack/Microsoft Teams:** Tạo một kênh riêng (ví dụ: \#proj-solution-architecture) cho các trao đổi nhanh, thông báo, và các câu hỏi đáp hàng ngày.  
* **Comments trên Confluence/Google Docs:** Dùng cho các góp ý trực tiếp trên nội dung tài liệu.  
* **Email:** Dùng cho các thông báo chính thức, quan trọng (ví dụ: gửi tài liệu để phê duyệt).

---

### **B. Quy trình Thực hiện Chi tiết**

**Bước 1: Thiết lập Không gian làm việc (Workspace Setup) \- (1 ngày)**

* **Hành động:** Dựa trên quyết định ở trên, ông Giang (hoặc ủy quyền cho Tech Lead) sẽ tiến hành thiết lập.  
* **Nếu dùng Confluence:**  
  1. Tạo một "Không gian" (Space) mới với tên gọi rõ ràng, ví dụ: "Pythaverse Solution Architecture".  
  2. Thiết lập quyền truy cập (Permissions): Ai có quyền xem (view), ai có quyền chỉnh sửa (edit), ai là quản trị viên (admin).  
  3. Tạo một trang chủ (homepage) cho không gian này, giới thiệu ngắn gọn về mục đích của SAD và link đến các tài liệu quan trọng.  
* **Nếu dùng Google Drive:**  
  1. Tạo một "Shared Drive" (Ổ đĩa dùng chung) để không bị phụ thuộc vào tài khoản cá nhân.  
  2. Tạo cấu trúc thư mục rõ ràng, ví dụ: /Tài liệu Kiến trúc/, /Tài liệu tham khảo/, /Biên bản họp/.  
  3. Thiết lập quyền chia sẻ cho thư mục gốc.

**Bước 2: Tạo Mẫu Tài liệu (Template Creation) \- (0.5 ngày)**

* **Hành động:** Đây là bước cực kỳ quan trọng để đảm bảo tính nhất quán. Ông Giang sẽ tạo ra một tài liệu mẫu.  
* **Trên Confluence:** Tạo một "Mẫu" (Template) mới.  
* **Trên Google Docs:** Tạo một file tài liệu mẫu và đặt tên rõ ràng, ví dụ: "\[TEMPLATE\] Solution Architecture Document".  
* **Nội dung của Template:** Dựa vào cấu trúc đã được cung cấp trong "Sổ Tay Kiến trúc sư", hãy tạo các đề mục chính:  
  * 1\. Tổng quan Giải pháp (Solution Overview)  
  * 2\. Bối cảnh Kinh doanh (Business Context)  
  * 3\. Tổng quan Giải pháp Khái niệm (Conceptual Solution Overview)  
  * 4\. Kiến trúc Giải pháp (Solution Architecture)  
    * 4.1 Kiến trúc Thông tin  
    * 4.2 Kiến trúc Ứng dụng  
    * ...  
  *   
  * 5\. Triển khai Giải pháp (Solution Implementation)  
  * 6\. Quản lý Giải pháp (Solution Management)  
  * 7\. Phụ lục (Appendix)  
* Trong mỗi mục, thêm các ghi chú placeholder, ví dụ: \[Mô tả ngắn gọn về mục đích, phạm vi, các giả định và ràng buộc tại đây...\] hoặc \[Chèn sơ đồ kiến trúc hệ thống tổng thể tại đây\].

**Bước 3: Thông báo và Hướng dẫn (Announcement & Guidance) \- (0.5 ngày)**

* **Hành động:** Sau khi mọi thứ đã sẵn sàng, ông Giang cần thông báo cho tất cả các bên liên quan.  
* **Nội dung thông báo (qua Email hoặc Slack):**  
  * Tiêu đề: Thiết lập không gian làm việc cho dự án Tài liệu Kiến trúc Giải pháp.  
  * Nội dung:  
    * Thông báo rằng không gian làm việc chính thức đã được thiết lập.  
    * **Cung cấp đường link** đến không gian Confluence hoặc thư mục Google Drive.  
    * **Giải thích quy tắc làm việc:**  
      * "Mọi tài liệu liên quan đến SAD sẽ được lưu trữ tại đây."  
      * "Vui lòng sử dụng mẫu \[link tới template\] khi tạo tài liệu mới."  
      * "Mọi góp ý/bình luận cần được thực hiện trực tiếp trên tài liệu để tiện theo dõi."  
      * "Các thảo luận nhanh sẽ diễn ra tại kênh Slack \#proj-solution-architecture."  
    * Đề nghị mọi người truy cập và làm quen với không gian làm việc.

---

### **Kết quả đầu ra của Bước 1.3:**

1. Một không gian làm việc tập trung (Confluence Space hoặc Shared Drive) đã được thiết lập và phân quyền.  
2. Một mẫu tài liệu SAD chuẩn với đầy đủ cấu trúc đề mục đã được tạo và sẵn sàng để sử dụng.  
3. Tất cả các bên liên quan đã được thông báo và hướng dẫn về cách sử dụng công cụ và tuân thủ quy trình làm việc.

