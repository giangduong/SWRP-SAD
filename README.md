# SAD STRUCTURE

## 1. Mục đích của Tài Liệu Kiến Trúc Giải Pháp (SAD)  
SAD đóng vai trò thiết yếu trong việc đảm bảo tất cả các bên liên quan, từ quản lý cấp cao đến nhóm phát triển và người dùng cuối, đều có cùng một cái nhìn về giải pháp được đề xuất. Các mục tiêu chính của SAD bao gồm:  
- **Truyền đạt giải pháp ứng dụng đầu cuối** cho tất cả các bên liên quan.  
- Cung cấp tổng quan cấp cao về kiến trúc và các góc nhìn khác nhau của thiết kế ứng dụng để đáp ứng các yêu cầu chất lượng dịch vụ như độ tin cậy, bảo mật, hiệu suất và khả năng mở rộng.  
- Đảm bảo khả năng truy vết của giải pháp trở lại các yêu cầu kinh doanh, bao gồm cả yêu cầu chức năng (FRs) và phi chức năng (NFRs).  
- Cung cấp tất cả các góc nhìn cần thiết cho việc thiết kế, xây dựng, thử nghiệm và triển khai.  
- Xác định các tác động của giải pháp cho mục đích ước tính, lập kế hoạch và phân phối.  
- Xác định quy trình kinh doanh, sự liên tục và các hoạt động cần thiết để giải pháp hoạt động không gián đoạn sau khi ra mắt sản phẩm.  
- SAD giúp **thu hẹp khoảng cách giao tiếp** giữa người dùng kinh doanh và nhóm phát triển.  
- Nó còn giúp **duy trì kiến thức** trong trường hợp thay đổi nhân sự và làm cho quy trình thiết kế tổng thể không phụ thuộc vào con người.  
- Đối với các ứng dụng cũ cần hiện đại hóa, SAD trình bày một cái nhìn trừu tượng về kiến trúc hiện tại và tương lai, cùng với một kế hoạch chuyển đổi.  

## 2. Các góc nhìn của Tài Liệu Kiến Trúc Giải Pháp (SAD)  
SAD cần cung cấp nhiều góc nhìn khác nhau để đáp ứng nhu cầu của cả người dùng kinh doanh và kỹ thuật:  
- **Góc nhìn Kinh doanh (Business View)**: Thể hiện đề xuất giá trị của giải pháp và sản phẩm tổng thể, các kịch bản cấp cao liên quan đến kinh doanh dưới dạng biểu đồ trường hợp sử dụng, mô tả các bên liên quan và tài nguyên cần thiết.  
- **Góc nhìn Logic (Logical View)**: Trình bày các gói khác nhau trong hệ thống theo một thứ tự tuần tự để người dùng kinh doanh và nhà thiết kế hiểu các thành phần logic và cách chúng kết nối.  
- **Góc nhìn Quy trình (Process View)**: Trình bày chi tiết cách các quy trình quan trọng của hệ thống hoạt động cùng nhau, có thể phản ánh bằng biểu đồ trạng thái hoặc biểu đồ trình tự.  
- **Góc nhìn Triển khai (Deployment View)**: Minh họa cách ứng dụng sẽ hoạt động trong môi trường sản xuất, bao gồm các thành phần hệ thống được kết nối như tường lửa mạng, bộ cân bằng tải, máy chủ ứng dụng và cơ sở dữ liệu.  
- **Góc nhìn Triển khai thực tế (Implementation View)**: Là phần cốt lõi của SAD, trình bày các lựa chọn kiến trúc và công nghệ (ví dụ: kiến trúc 3 tầng, N-tầng, hoặc hướng sự kiện) cùng với lý do đằng sau, và biện minh cho các tài nguyên và kỹ năng cần thiết.  
- **Góc nhìn Dữ liệu (Data View)**: Mô tả cách dữ liệu sẽ luân chuyển giữa các thành phần khác nhau và cách nó sẽ được lưu trữ, bao gồm bảo mật và tính toàn vẹn dữ liệu. Thường sử dụng biểu đồ quan hệ thực thể (ERD).  
- **Góc nhìn Vận hành (Operational View)**: Giải thích cách hệ thống sẽ được duy trì sau khi ra mắt, bao gồm các thỏa thuận cấp độ dịch vụ (SLA), chức năng cảnh báo và giám sát, kế hoạch khôi phục sau thảm họa và kế hoạch hỗ trợ.  

## 3. Cấu trúc của Tài Liệu Kiến Trúc Giải Pháp (SAD)  
Cấu trúc SAD có thể khác nhau tùy theo dự án, nhưng thường bao gồm các phần chính sau:  
- **Tổng quan Giải pháp (Solution Overview)**: Giới thiệu ngắn gọn về giải pháp, các thành phần ở cấp độ rất cao, mục đích, phạm vi, các giả định, ràng buộc (kỹ thuật, kinh doanh, tài nguyên, tuân thủ), các phụ thuộc và các quyết định kiến trúc chính.  
- **Bối cảnh Kinh doanh (Business Context)**: Cung cấp tổng quan cấp cao về các khả năng và yêu cầu kinh doanh mà giải pháp sẽ giải quyết, các quy trình kinh doanh chính, các bên liên quan và các yêu cầu phi chức năng (NFRs).  
- **Tổng quan Giải pháp Khái niệm (Conceptual Solution Overview)**: Trình bày một biểu đồ cấp độ trừu tượng, nắm bắt cái nhìn tổng thể về giải pháp, bao gồm cả khía cạnh kinh doanh và kỹ thuật.  
- **Kiến trúc Giải pháp (Solution Architecture)**: Đi sâu vào từng phần của kiến trúc, cung cấp các góc nhìn chi tiết cho đội ngũ kỹ thuật. Bao gồm các kiến trúc thông tin, ứng dụng, dữ liệu, tích hợp, hạ tầng và bảo mật.  
- **Triển khai Giải pháp (Solution Implementation)**: Thảo luận về công cụ phát triển, ngôn ngữ lập trình, kho mã nguồn, phương pháp triển khai, công cụ triển khai, và cách tiếp cận di chuyển dữ liệu.  
- **Quản lý Giải pháp (Solution Management)**: Đề cập đến việc quản lý nâng cấp ứng dụng, phát hành mới, hạ tầng hệ thống, giám sát, cảnh báo, hỗ trợ sản xuất, SLA, quản lý sự cố, khôi phục sau thảm họa và liên tục quy trình kinh doanh.  
- **Phụ lục (Appendix)**: Chứa bất kỳ dữ liệu hỗ trợ nào cho kiến trúc và lựa chọn giải pháp tổng thể, như kết quả POC, dữ liệu so sánh công cụ và thông tin nhà cung cấp/đối tác.  

## 4. Vòng đời của Tài Liệu Kiến Trúc Giải Pháp (SAD)  
SAD là một tài liệu sống, được tạo ra trong các giai đoạn đầu của dự án và được cập nhật theo thời gian dựa trên các thay đổi trong vòng đời ứng dụng. Các giai đoạn trong vòng đời SAD bao gồm:  
- **Khởi tạo (Initiation)**: Xác định nhu cầu và mục tiêu của SAD khi dự án bắt đầu.  
- **Thu thập yêu cầu (Gathering requirements)**: Thu thập các yêu cầu chi tiết từ các bên liên quan chính.  
- **Phác thảo (Drafting)**: Tạo phiên bản ban đầu của SAD, là bản thiết kế cho việc triển khai kỹ thuật của dự án.  
- **Xem xét và phản hồi (Review and feedback)**: Chia sẻ bản nháp với các bên liên quan để nhận phản hồi.  
- **Hoàn thiện (Finalization)**: SAD được hoàn thiện sau khi kết hợp các phản hồi.  
- **Triển khai (Implementation)**: Tài liệu đã hoàn thiện hướng dẫn việc triển khai dự án.  
- **Bảo trì (Maintenance)**: SAD được xem xét và cập nhật định kỳ để phản ánh các thay đổi công nghệ, mục tiêu kinh doanh hoặc các yếu tố bên ngoài.  

## 5. Các phương pháp hay nhất và cạm bẫy cần tránh với SAD  
Để quản lý SAD hiệu quả, cần tuân thủ các phương pháp hay nhất và tránh các cạm bẫy phổ biến:  
- **Phương pháp hay nhất**:  
    - Giữ tài liệu **rõ ràng và súc tích**, tránh biệt ngữ kỹ thuật.  
    - **Thường xuyên thu hút các bên liên quan** để đảm bảo tài liệu phù hợp với yêu cầu kinh doanh và kỹ thuật.  
    - Giữ SAD **cập nhật** với các thay đổi và phát triển dự án mới nhất.  
    - Đảm bảo kiến trúc được phác thảo trong SAD phù hợp với các mục tiêu kinh doanh rộng lớn hơn của tổ chức.  
- **Cạm bẫy phổ biến**:  
    - **Phức tạp hóa kiến trúc quá mức** có thể dẫn đến thách thức trong triển khai và bảo trì.  
    - **Thiếu linh hoạt** trong tài liệu có thể cản trở khả năng thích ứng với các thay đổi trong phạm vi hoặc mục tiêu dự án.  
    - **Tham gia không đủ của các bên liên quan** có thể dẫn đến sự không phù hợp với nhu cầu và yêu cầu kinh doanh thực tế.  
    - **Thực hành tài liệu kém** có thể dẫn đến hiểu lầm, lỗi triển khai và thách thức trong việc thực hiện dự án.  

## 6. Tài liệu mua sắm CNTT cho kiến trúc giải pháp  
Kiến trúc sư giải pháp cũng thường xuyên tham gia vào các tài liệu mua sắm CNTT, còn gọi là tài liệu RFx (Request for x), bao gồm RFI (Request for Information), RFP (Request for Proposal) và RFQ (Request for Quotation).  
- **RFI (Request for Information)**: Giai đoạn đầu, thu thập thông tin từ các nhà cung cấp khác nhau để đưa ra quyết định sáng suốt về lựa chọn mua sắm.  
- **RFP (Request for Proposal)**: Nhà cung cấp được chọn lọc từ RFI sẽ nhận thêm thông tin về kết quả dự án và có thể đề xuất giải pháp tốt nhất với nhiều lựa chọn, ưu nhược điểm.  
- **RFQ (Request for Quotation)**: Các yêu cầu được thu hẹp hơn so với RFP, nhà cung cấp cung cấp chi phí cho các yêu cầu cụ thể.  

**Vai trò của kiến trúc sư giải pháp** trong quá trình RFP là rất quan trọng, bao gồm đánh giá năng lực của nhà cung cấp, phân tích kỹ thuật, đánh giá rủi ro, phát triển chiến lược kỹ thuật, tài liệu hóa, chiến lược định giá và trình bày giải pháp.  
Tổng kết, Tài Liệu Kiến Trúc Giải Pháp (SAD) là một công cụ trung tâm trong bộ công cụ của Kiến trúc sư Giải pháp, đảm bảo các giải pháp được thiết kế tốt, được truyền đạt rõ ràng và có thể duy trì được trong dài hạn.  
