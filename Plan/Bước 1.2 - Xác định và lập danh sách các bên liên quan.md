Bước **1.2: Xác định và lập danh sách các bên liên quan** là nền tảng để đảm bảo việc giao tiếp và phối hợp diễn ra suôn sẻ.

Mục tiêu của bước này không chỉ là liệt kê ra "ai" mà còn là xác định rõ "vai trò, trách nhiệm và mức độ tham gia" của họ. Giao phẩm cuối cùng là **Ma trận RACI** hoặc một danh sách chi tiết, và đây là cách để ông Giang thực hiện nó.

### **Quy trình và Cách thức thực hiện Bước 1.2**

#### **Mục tiêu chính:**

* **Không bỏ sót ai:** Đảm bảo tất cả các cá nhân, đội nhóm có ảnh hưởng hoặc bị ảnh hưởng bởi dự án SAD đều được xác định.  
* **Làm rõ trách nhiệm:** Phân định rõ ràng ai làm gì, ai quyết định, ai cần hỏi ý kiến, và ai chỉ cần được thông báo.  
* **Quản lý kỳ vọng:** Giúp các bên liên quan hiểu rõ họ được kỳ vọng đóng góp ở mức độ nào, tránh tình trạng "tôi tưởng..." hoặc "sao không ai hỏi tôi?".  
* **Tối ưu hóa giao tiếp:** Biết chính xác cần liên hệ với ai cho từng vấn đề cụ thể, tránh các cuộc họp không cần thiết hoặc gửi email cho cả công ty.

---

### **A. Bước 1: Brainstorm và Lập danh sách (Brainstorming)**

Đầu tiên, ông Giang cần liệt kê tất cả các bên liên quan tiềm năng. Hãy suy nghĩ theo các nhóm sau để không bỏ sót:

* **Nhóm Lãnh đạo & Chiến lược (Leadership & Strategy):**  
  * **CEO:** Người có tiếng nói quyết định cuối cùng về sự phù hợp của kiến trúc với chiến lược kinh doanh.  
  * **(Có thể) Trưởng phòng Tài chính (CFO):** Quan tâm đến chi phí hạ tầng, bản quyền phần mềm được đề xuất trong kiến trúc.  
* **Nhóm Sản phẩm & Kinh doanh (Product & Business):**  
  * **Head of Product:** Người đảm bảo kiến trúc đáp ứng được lộ trình sản phẩm và các yêu cầu nghiệp vụ.  
  * **Product Managers (PMs):** Chịu trách nhiệm cho các module cụ thể (Leanbot, TwinSpace, PLab...) và là người cung cấp yêu cầu chi tiết.  
  * **(Có thể) Business Development/Sales Team:** Cung cấp thông tin về yêu cầu từ các khách hàng lớn, các trường học đối tác.  
* **Nhóm Kỹ thuật (Engineering \- Core Team):**  
  * **CTO (Dương Thành Giang):** Người chịu trách nhiệm cao nhất về mặt kỹ thuật.  
  * **Tech Leads/Team Leads:** Dẫn dắt các đội phát triển (Backend, Frontend, Mobile, AI...). Họ là người triển khai kiến trúc.  
  * **Senior Engineers/Architects:** Các chuyên gia có kinh nghiệm sâu, cung cấp tư vấn kỹ thuật quan trọng.  
  * **DevOps/SRE Team:** Chịu trách nhiệm về hạ tầng, triển khai, giám sát.  
  * **Security Team:** Đảm bảo kiến trúc tuân thủ các tiêu chuẩn bảo mật.  
  * **QA/QC Team:** Đảm bảo kiến trúc có thể kiểm thử được.  
  * **Data Team (Data Engineers/Scientists):** Quan tâm đến luồng dữ liệu, lưu trữ và phân tích.  
* **Nhóm Vận hành & Hỗ trợ (Operations & Support):**  
  * **Customer Support Team:** Cung cấp góc nhìn về các vấn đề người dùng cuối thường gặp, cần được giải quyết ở cấp độ kiến trúc.

### **B. Bước 2: Xây dựng Ma trận RACI (The Core Task)**

Sau khi có danh sách, ông Giang sẽ tạo một ma trận để gán vai trò cụ thể cho từng hoạt động chính trong dự án SAD.

**Giải thích nhanh về RACI:**

* **R \- Responsible (Người thực hiện):** Người hoặc nhóm trực tiếp làm công việc. Có thể có nhiều R.  
* **A \- Accountable (Người chịu trách nhiệm chính):** Người sở hữu cuối cùng của công việc, chịu trách nhiệm cho kết quả. **Bắt buộc chỉ có một A cho mỗi công việc.**  
* **C \- Consulted (Người được tham vấn):** Người cần được hỏi ý kiến trước khi quyết định (giao tiếp 2 chiều).  
* **I \- Informed (Người được thông báo):** Người cần được cập nhật về tiến độ hoặc kết quả sau khi quyết định đã được đưa ra (giao tiếp 1 chiều).

**Cách thực hiện:**

1. **Tạo bảng:** Dùng Google Sheets hoặc Confluence.  
   * Các **hàng (rows)** là các hoạt động/giao phẩm chính trong dự án SAD (có thể lấy từ kế hoạch tổng thể).  
   * Các **cột (columns)** là danh sách các bên liên quan đã liệt kê ở trên.  
2. **Điền vào ma trận:** Ông Giang sẽ chủ trì việc điền vào ma trận này. Dưới đây là một ví dụ minh họa:

| Hoạt động / Giao phẩm | CTO (Giang) | CEO | Head of Product | Tech Lead | DevOps Lead | Security Lead |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| **1\. Chốt phạm vi của SAD** | **A** | C | C | I | I | I |
| **2\. Định nghĩa Yêu cầu Kinh doanh** | C | I | **A** | I | I | I |
| **3\. Định nghĩa Yêu cầu Phi chức năng** | **A** | I | C | R | C | C |
| **4\. Lựa chọn công nghệ & framework** | **A** | I | I | R | C | C |
| **5\. Thiết kế kiến trúc hạ tầng** | **A** | C (về chi phí) | I | C | R | C |
| **6\. Thiết kế luồng dữ liệu & lưu trữ** | **A** | I | I | R | I | C |
| **7\. Rà soát & Góp ý bản nháp SAD** | R | C | C | C | C | C |
| **8\. Phê duyệt cuối cùng SAD v1.0** | R | **A** | C | I | I | I |

**Lưu ý quan trọng cho ông Giang khi điền:**

* **Bắt đầu với chính mình:** Điền vai trò của mình (chủ yếu là A và R) vào các công việc trước tiên.  
* **Chỉ có một 'A':** Đảm bảo mỗi hàng chỉ có duy nhất một 'A'. Nếu có hai người cùng chịu trách nhiệm chính, nghĩa là chưa phân định rõ ràng. Ví dụ, CTO chịu trách nhiệm về kỹ thuật, nhưng CEO là người phê duyệt cuối cùng để đảm bảo nó phù hợp với chiến lược công ty.  
* **Đừng lạm dụng 'C':** Chỉ đánh dấu 'C' cho những người thực sự cần thiết phải hỏi ý kiến. Quá nhiều 'C' sẽ làm chậm quá trình ra quyết định.  
* **'I' là cách hiệu quả để giữ mọi người trong cuộc:** Sử dụng 'I' một cách rộng rãi để đảm bảo tính minh bạch mà không cần sự tham gia tích cực của tất cả mọi người.

### **C. Bước 3: Rà soát và Xác nhận (Validation)**

Đây không phải là một bài tập làm một mình.

1. **Soạn thảo bản nháp:** Ông Giang tự mình hoặc cùng với 1-2 người chủ chốt (như Head of Product) điền bản nháp đầu tiên của ma trận RACI.  
2. **Tổ chức buổi họp rà soát ngắn (30-45 phút):** Mời các trưởng bộ phận/trưởng nhóm chính (Head of Product, các Tech Leads).  
   * **Mục tiêu:** Trình bày ma trận RACI và xác nhận vai trò của từng người.  
   * **Cách tiến hành:** Đi qua từng hàng và hỏi "Mọi người có đồng ý với sự phân công này không? Có ai cảm thấy mình nên là 'C' thay vì 'I' ở mục này không?".  
3. **Hoàn thiện và phổ biến:**  
   * Cập nhật ma trận dựa trên các phản hồi.  
   * Lưu trữ tài liệu ở nơi mọi người dễ dàng truy cập (Confluence, Google Drive của dự án).  
   * Gửi email thông báo cho tất cả các bên liên quan trong danh sách, đính kèm link tới ma trận RACI đã hoàn thiện và giải thích ngắn gọn mục đích của nó.

