**1\. Giới thiệu**

Tài liệu này phác thảo các yêu cầu nghiệp vụ và chức năng đối với nền tảng Chương trình giảng dạy SWRP (Phần mềm, Robot và Lập trình). Nền tảng này nhằm mục đích cung cấp một môi trường học tập hiện đại, dựa trên đám mây, được thiết kế cho tương tác thời gian thực, kết xuất 3D và phân tích dữ liệu, mang đến trải nghiệm công nghệ xác thực cho học sinh.

**2\. Mục tiêu Kinh doanh**

* Cung cấp nền tảng giáo dục SWRP mạnh mẽ và có khả năng mở rộng.  
* Cung cấp trải nghiệm học tập chân thực, thực hành thông qua các công cụ và công nghệ chuyên nghiệp.  
* Hỗ trợ tương tác thời gian thực, môi trường 3D và phân tích dữ liệu chuyên sâu.  
* Thúc đẩy các hoạt động cộng tác và thực hành phát triển phần mềm tốt nhất.  
* Tích hợp liền mạch các công nghệ khác nhau thành một hệ sinh thái gắn kết.  
* Nâng cao hiểu biết của học sinh về AI, IoT và phát triển ứng dụng di động.

**3\. Đối tượng Người dùng**

* **Học sinh:** Người dùng chính của nền tảng, tham gia vào các khóa học, phòng thí nghiệm ảo và dự án.  
* **Giáo viên:** Quản lý khóa học, theo dõi tiến độ của học sinh, chấm điểm và tạo tài liệu học tập.  
* **Quản trị viên:** Quản lý người dùng, cấu hình hệ thống và giám sát hoạt động của nền tảng.

**4\. Yêu cầu Nghiệp vụ (BRs)**

BR1: Nền tảng phải cung cấp khả năng quản lý người dùng và cấp phép an toàn.  
BR2: Nền tảng phải tích hợp liền mạch với chương trình giảng dạy và hệ thống quản lý học tập.  
BR3: Nền tảng phải cung cấp một môi trường 3D đa người dùng, sống động để cộng tác và mô phỏng robot.  
BR4: Nền tảng phải hỗ trợ các hoạt động kiểm soát phiên bản và lập trình robot chuyên nghiệp.  
BR5: Nền tảng phải cung cấp các khả năng mô phỏng vật lý có độ trung thực cao cho robot.  
BR6: Nền tảng phải cho phép học sinh tương tác với các thiết bị IoT vật lý và phân tích dữ liệu.  
BR7: Nền tảng phải cung cấp một môi trường khoa học dữ liệu mạnh mẽ để phân tích dữ liệu và hiểu biết sâu sắc.  
BR8: Nền tảng phải cho phép học sinh phát triển các ứng dụng di động tương tác với các dịch vụ dựa trên web.  
BR9: Nền tảng phải quản lý nội dung công cộng, tài liệu và hỗ trợ người dùng.  
BR10: Nền tảng phải hỗ trợ kiến trúc cơ sở dữ liệu mạnh mẽ và có khả năng mở rộng.  
BR11: Nền tảng phải được triển khai trên mô hình lai kết hợp cơ sở hạ tầng tại chỗ và đám mây để có hiệu suất và khả năng mở rộng tối ưu.  
BR12: Nền tảng phải cung cấp một hệ sinh thái sáng tạo hoàn chỉnh cho việc tạo thế giới ảo, hình đại diện và nhân vật AI tương tác.  
BR13: Nền tảng phải tạo điều kiện cho việc học tập hợp tác và các không gian dự án ảo.  
BR14: Nền tảng phải hỗ trợ học tập khái niệm sống động thông qua trực quan hóa dữ liệu và khám phá hệ thống cơ học.

**5\. Yêu cầu Chức năng (FRs) & Các Tính năng Chính**

**5.1. Quản lý Danh tính & Quyền truy cập (Keycloak)**

* FR1.1: Hệ thống phải cung cấp khả năng Đăng nhập một lần (SSO) cho tất cả các dịch vụ nền tảng.  
* FR1.2: Hệ thống phải quản lý các danh tính, vai trò (học sinh, giáo viên, quản trị viên) và quyền của người dùng.  
* FR1.3: Hệ thống phải tích hợp với các nhà cung cấp danh tính bên ngoài (ví dụ: LDAP, SAML, Google Workspace).

**5.2. Quản lý Học tập & Chương trình giảng dạy (Tích hợp Moodle)**

* FR2.1: Hệ thống phải đồng bộ hóa danh sách lớp học từ Keycloak vào Moodle.  
* FR2.2: Hệ thống phải hiển thị nội dung chương trình giảng dạy của Moodle trong giao diện người dùng chính của nền tảng.  
* FR2.3: Hệ thống phải đẩy điểm và tiến độ từ phòng thí nghiệm mô phỏng vào sổ điểm Moodle.  
* FR2.4: Hệ thống phải truy cập Moodle thông qua một microservice Node.js/Python tùy chỉnh hoạt động như một cổng API.

**5.3. Vũ trụ ảo cộng tác (Mozilla Hubs)**

* FR3.1: Hệ thống phải tạo các phòng ảo riêng tư, cố định cho từng lớp học hoặc nhóm dự án.  
* FR3.2: Hệ thống phải xác thực người dùng thông qua Keycloak trước khi cấp quyền truy cập vào phòng Hubs.  
* FR3.3: Hệ thống phải hiển thị các mô hình 3D của robot do học sinh thiết kế và môi trường cụ thể của chương trình giảng dạy vào phòng Hubs.  
* FR3.4: Nền tảng phải cho phép học sinh tạo các nhân vật AI đàm thoại tùy chỉnh trong một giao diện không mã.  
* FR3.5: Các nhân vật AI phải được cung cấp bởi một mô hình OpenAI cơ bản và có thể được cá nhân hóa bằng cách sử dụng lời nhắc hệ thống (persona) do học sinh xác định.  
* FR3.6: Các nhân vật AI phải có thể sử dụng cơ sở kiến thức riêng tư (tài liệu do học sinh tải lên) để trả lời các câu hỏi cụ thể, theo ngữ cảnh (Tạo tăng cường truy xuất \- RAG).  
* FR3.7: Các nhân vật AI đã tạo phải được gán cho hình đại diện 3D và có thể được triển khai dưới dạng NPC tương tác trong phòng Mozilla Hubs.  
* FR3.8: Học sinh khác phải có thể tương tác với các nhân vật AI trong Metaverse thông qua giọng nói hoặc văn bản, với các phản hồi theo thời gian thực.  
* FR3.9: Nền tảng phải cung cấp môi trường ảo được chia sẻ để học sinh có thể gặp gỡ, giao tiếp và cộng tác trong các dự án.  
* FR3.10: Học sinh phải có khả năng sử dụng bảng trắng ảo, nhập mô hình 3D và cùng gỡ lỗi mã trên một màn hình ảo được chia sẻ trong các không gian dự án.  
* FR3.11: Nền tảng phải cho phép trực quan hóa luồng dữ liệu từ cảm biến qua bộ xử lý của robot đến thiết bị truyền động trong môi trường 3D.  
* FR3.12: Nền tảng phải cho phép khám phá các hệ thống cơ học (ví dụ: tháo dỡ hộp số ảo, đi bộ qua mô hình CPU quy mô lớn).

**5.4. Mã & Kiểm soát Phiên bản (GitBucket)**

* FR4.1: Hệ thống phải tự động tạo kho lưu trữ Git cho các dự án mới của học sinh.  
* FR4.2: Trình soạn thảo mã trong trình duyệt phải cam kết mã trực tiếp vào kho lưu trữ GitBucket của học sinh.  
* FR4.3: Hệ thống phải hỗ trợ lịch sử phiên bản, phân nhánh và cộng tác trên mã.

**5.5. Mô phỏng**

* FR5.1: Hệ thống phải chạy mô phỏng vật lý có độ trung thực cao.  
* FR5.2: Giao diện người dùng phải dựa trên React.js/Vue.js với TypeScript để tương tác và bảo trì.  
* FR5.3: Hệ thống phải hiển thị mô phỏng robot 3D và môi trường Metaverse bằng cách sử dụng Three.js (WebGL) trực tiếp trong trình duyệt.  
* FR5.4: Hệ thống phải quản lý trạng thái ứng dụng phức tạp (ví dụ: vị trí robot, dữ liệu cảm biến, tương tác người dùng) bằng Redux hoặc Vuex.  
* FR5.5: Hệ thống phải hỗ trợ giao tiếp hai chiều, thời gian thực giữa người dùng và máy chủ bằng WebSockets để cộng tác trực tiếp và cập nhật.

**5.6. Nền tảng IoT & Trực quan hóa Dữ liệu (OpenRemote)**

* FR6.1: Học sinh phải có khả năng kết nối Leanbot với các cảm biến IoT (nhiệt độ, ánh sáng, chuyển động, v.v.).  
* FR6.2: Học sinh phải có khả năng cấu hình thiết bị để gửi dữ liệu đến nền tảng IoT bằng các giao thức tiêu chuẩn (ví dụ: MQTT).  
* FR6.3: Học sinh phải có khả năng tạo bảng điều khiển dựa trên web tùy chỉnh với đồ thị thời gian thực, đồng hồ đo, bản đồ và cảnh báo để trực quan hóa dữ liệu cảm biến.  
* FR6.4: Học sinh phải có khả năng sử dụng công cụ quy tắc của nền tảng IoT để tạo logic tự động hóa "nếu-thì" (ví dụ: Bật quạt nếu nhiệt độ \> 25°C).

**5.7. Phân tích Dữ liệu & Thông tin chi tiết (JupyterHub)**

* FR7.1: Hệ thống phải cung cấp môi trường khoa học dữ liệu dựa trên JupyterHub.  
* FR7.2: JupyterHub phải kết nối với cơ sở dữ liệu PostgreSQL và kho dữ liệu.  
* FR7.3: Hệ thống phải cung cấp sổ ghi chép được cấu hình sẵn để giáo viên trực quan hóa tiến độ của lớp học.  
* FR7.4: Học sinh phải có khả năng thực hiện phân tích dữ liệu trên nhật ký cảm biến của robot trong các khóa học nâng cao.

**5.8. Phát triển Ứng dụng Di động (MIT App Inventor)**

* FR8.1: Hệ thống phải cung cấp môi trường dựa trên khối cho học sinh để tạo các ứng dụng di động chức năng cho Android và iOS.  
* FR8.2: Hệ thống phải cho phép học sinh thiết kế giao diện người dùng/trải nghiệm người dùng (UI/UX) và lập trình hướng sự kiện.  
* FR8.3: Ứng dụng phải có khả năng tương tác với các API dựa trên web.

**5.9. Không gian làm việc của người dùng, Nội dung Công cộng & Tài liệu (WordPress)**

* FR9.1: Hệ thống phải quản lý nội dung hướng tới công chúng (trang web tiếp thị, blog, nghiên cứu điển hình).  
* FR9.2: Hệ thống phải quản lý cơ sở kiến thức và tài liệu hỗ trợ.  
* FR9.3: Nền tảng chính phải có khả năng kéo các bài viết trợ giúp hoặc bài đăng blog từ WordPress để hiển thị trong giao diện người dùng.

**5.10. Cơ sở dữ liệu**

* FR10.1: Hệ thống phải sử dụng MySQL/PostgreSQL làm cơ sở dữ liệu quan hệ chính.  
* FR10.2: Hệ thống phải sử dụng Redis để lưu vào bộ nhớ đệm dữ liệu truy cập thường xuyên và quản lý thông tin phiên thời gian thực.  
* FR10.3: Hệ thống phải sử dụng PostgreSQL làm kho dữ liệu để tổng hợp và phân tích dữ liệu hiệu suất của học sinh.

**5.11. Cơ sở hạ tầng & DevOps**

* FR11.1: Nền tảng phải được triển khai trên mô hình lai (máy chủ tự lưu trữ và đám mây công cộng).  
* FR11.2: Tất cả các microservice phải được đóng gói bằng Docker.  
* FR11.3: Docker Swarm phải được sử dụng để điều phối vùng chứa (tự động mở rộng quy mô, tự phục hồi, triển khai không ngừng nghỉ).  
* FR11.4: GitHub Actions phải được sử dụng cho quy trình CI/CD tự động.  
* FR11.5: LightCDN phải được sử dụng để lưu vào bộ nhớ đệm các tài sản tĩnh để cải thiện thời gian tải.

