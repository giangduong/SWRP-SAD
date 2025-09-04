### **Tài liệu Kiến trúc Giải pháp (Solution Architecture Document)**

### **Nền tảng Giáo dục Pythaverse** 

### **Phần 1: Tổng quan Giải pháp (Solution Overview)**

#### **1.1. Giới thiệu và Mục đích**

Tài liệu này trình bày kiến trúc giải pháp cho nền tảng giáo dục của Pythaverse. Đây là một hệ sinh thái học tập thế hệ mới, được xây dựng trên nền tảng đám mây, với mục tiêu cung cấp cho học sinh một trải nghiệm giáo dục STEM chân thực, hấp dẫn và mang tính thực hành cao.

Mục đích của tài liệu này là đóng vai trò là bản thiết kế kỹ thuật trung tâm, đảm bảo tất cả các bên liên quan – từ ban lãnh đạo, đội ngũ phát triển sản phẩm đến các kỹ sư – đều có chung một tầm nhìn và sự hiểu biết về cách thức hệ thống được xây dựng, triển khai và vận hành.

#### **1.2. Tóm tắt Giải pháp**

Nền tảng Pythaverse là một hệ sinh thái tích hợp nhiều công nghệ tiên tiến nhằm tạo ra một môi trường học tập sống động, nơi học sinh có thể tương tác, cộng tác và sáng tạo. Giải pháp được xây dựng theo kiến trúc microservices, kết hợp sức mạnh của các nền tảng mã nguồn mở hàng đầu với các dịch vụ tùy chỉnh để tạo ra một hệ thống gắn kết và mạnh mẽ.

Các thành phần cốt lõi của hệ sinh thái bao gồm:

* **Quản lý Danh tính Tập trung (Keycloak):** Cung cấp khả năng Đăng nhập một lần (SSO) và quản lý vai trò (học sinh, giáo viên, quản trị viên) trên toàn bộ nền tảng.  
* **Hệ thống Quản lý Học tập (Moodle Integration):** Tích hợp liền mạch với Moodle để quản lý chương trình giảng dạy, danh sách lớp học và đồng bộ hóa điểm số.  
* **Không gian Metaverse Cộng tác (TwinSpace \- dựa trên Mozilla Hubs):** Một môi trường 3D đa người dùng, nơi học sinh có thể tham gia các lớp học ảo, mô phỏng robot, và tương tác với các nhân vật AI do chính mình tạo ra.  
* **Lập trình & Kiểm soát Phiên bản (GitBucket):** Cung cấp môi trường lập trình chuyên nghiệp với kho lưu trữ Git riêng cho từng dự án của học sinh.  
* **Hệ sinh thái IoT (OpenRemote) & Robot vật lý (Leanbot):** Cho phép học sinh kết nối robot vật lý với các cảm biến, thu thập dữ liệu IoT và tạo ra các bảng điều khiển trực quan hóa.  
* **Phân tích Dữ liệu (JupyterHub):** Cung cấp môi trường khoa học dữ liệu mạnh mẽ để học sinh và giáo viên phân tích dữ liệu cảm biến và tiến độ học tập.  
* **Phát triển Ứng dụng Di động (MIT App Inventor):** Môi trường lập trình khối trực quan giúp học sinh tự tạo ra các ứng dụng di động của riêng mình.  
* **Hệ thống Quản lý Nội dung (WordPress):** Quản lý trang web công khai, blog và cơ sở kiến thức hỗ trợ.

Toàn bộ hệ thống được đóng gói bằng Docker, điều phối bởi Docker Swarm và triển khai trên mô hình hạ tầng lai (hybrid), tận dụng cả máy chủ tại chỗ và đám mây công cộng để tối ưu hóa hiệu suất và chi phí.

#### **1.3. Phạm vi Giải pháp (Solution Scope)**

**Trong phạm vi (In Scope):**

* Xây dựng và tích hợp các dịch vụ để quản lý danh tính và quyền truy cập người dùng.  
* Tích hợp sâu với hệ thống Moodle để quản lý chương trình học.  
* Thiết lập và tùy chỉnh môi trường metaverse 3D (Mozilla Hubs) cho việc học cộng tác.  
* Phát triển tính năng cho phép người dùng tạo, tùy chỉnh và tương tác với các nhân vật AI (sử dụng RAG và OpenAI).  
* Tích hợp GitBucket và trình soạn thảo mã trên trình duyệt.  
* Xây dựng giao diện người dùng (frontend) cho việc mô phỏng và hiển thị 3D (WebGL/Three.js).  
* Tích hợp nền tảng IoT (OpenRemote) để thu thập và trực quan hóa dữ liệu.  
* Triển khai và cấu hình JupyterHub cho phân tích dữ liệu.  
* Tích hợp MIT App Inventor, WordPress, và các hệ quản trị cơ sở dữ liệu (PostgreSQL, Redis).  
* Thiết lập toàn bộ hạ tầng (hybrid), quy trình CI/CD và hệ thống giám sát.

**Ngoài phạm vi (Out of Scope):**

* Phát triển phần cứng của robot Leanbot và các cảm biến IoT.  
* Xây dựng nội dung chi tiết cho từng khóa học (chương trình giảng dạy). Nền tảng chỉ cung cấp công cụ để lưu trữ và phân phối nội dung.  
* Các hệ thống quản lý nội bộ của công ty như CRM, ERP, hay hệ thống tài chính kế toán.  
* Hệ thống thanh toán, cổng thanh toán và quản lý đăng ký thuê bao.

#### **1.4. Các Quyết định Kiến trúc Chính (Key Architectural Decisions)**

Kiến trúc của nền tảng được định hình bởi các quyết định nền tảng sau đây:

1. **Kiến trúc Microservices:** Toàn bộ hệ thống được chia thành các dịch vụ nhỏ, độc lập, có thể phát triển, triển khai và mở rộng riêng biệt. Điều này tăng cường khả năng bảo trì và linh hoạt.  
2. **Mô hình triển khai Hybrid:** Kết hợp giữa hạ tầng tự lưu trữ (on-premise) cho các tác vụ đòi hỏi hiệu suất cao/bảo mật và hạ tầng đám mây công cộng (AWS/GCP) để tận dụng khả năng mở rộng linh hoạt.  
3. **Containerization làm trung tâm (Docker & Docker Swarm):** Tất cả các dịch vụ được đóng gói trong các container Docker và được điều phối bởi Docker Swarm, giúp chuẩn hóa môi trường và tự động hóa việc quản lý.  
4. **Xác thực và Ủy quyền Tập trung (Federated Identity with Keycloak):** Sử dụng Keycloak làm trung tâm quản lý danh tính, đơn giản hóa việc bảo mật và tích hợp trên toàn bộ các microservice.  
5. **Tận dụng các Nền tảng Mã nguồn mở chiến lược:** Thay vì xây dựng lại từ đầu, giải pháp ưu tiên tích hợp và tùy chỉnh các nền tảng mã nguồn mở mạnh mẽ, đã được kiểm chứng (Moodle, Mozilla Hubs, JupyterHub, GitBucket, OpenRemote) để tăng tốc độ phát triển và tập trung vào các giá trị cốt lõi.

#### **1.5. Các Giả định (Assumptions)**

* Các nền tảng mã nguồn mở được lựa chọn (Mozilla Hubs, Keycloak, JupyterHub, v.v.) có đủ tính năng, độ ổn định và khả năng tùy chỉnh để đáp ứng các yêu cầu chức năng.  
* Đội ngũ kỹ thuật của Pythaverse có đủ năng lực để làm việc với các công nghệ được lựa chọn (Docker, Microservices, Node.js, Python, TypeScript, v.v.).  
* Các API do các dịch vụ bên thứ ba (Moodle, OpenAI) cung cấp là ổn định và đáp ứng được yêu cầu về hiệu suất.  
* Mô hình hạ tầng hybrid là khả thi về mặt kỹ thuật và tối ưu về mặt chi phí cho quy mô hoạt động dự kiến.

#### **1.6. Các Ràng buộc (Constraints)**

* **Ràng buộc Pháp lý:** Hệ thống phải tuân thủ nghiêm ngặt các quy định về bảo vệ dữ liệu cá nhân của trẻ em, bao gồm **COPPA** và **GDPR**.  
* **Ràng buộc Hiệu suất:** Các tương tác trong môi trường 3D metaverse phải diễn ra trong thời gian thực, với độ trễ thấp và hỗ trợ lên đến **10,000 người dùng đồng thời** trong các sự kiện lớn.  
* **Ràng buộc Vận hành:** Các dịch vụ học tập cốt lõi phải đạt thời gian hoạt động (SLA) tối thiểu là **99.9%** trong khung giờ từ 7 giờ sáng đến 10 giờ tối.  
* **Ràng buộc Công nghệ:** Giải pháp bị giới hạn trong việc sử dụng các công nghệ và nền tảng đã được chỉ định trong tài liệu yêu cầu (ví dụ: Keycloak cho IAM, Docker Swarm cho điều phối, PostgreSQL/Redis cho cơ sở dữ liệu).  
* **Ràng buộc Chi phí:** Kiến trúc phải được thiết kế để tối ưu hóa chi phí vận hành trên hạ tầng hybrid.
