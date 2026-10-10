# NHẬT KÝ PROMPT ENGINEERING (VIBE CODING LOG)
- **Họ và tên: Nguyễn Thanh Toàn**
- **MSSV: 426000057**
- **Tên đề tài Website: Website bán hàng**
- **Công cụ AI đã sử dụng: ChatGPT** (ví dụ: ChatGPT, Claude, GitHub Copilot, Cursor,
v.v.)
## 1. Yêu cầu ban đầu (System/Initial Prompt)
> *Ghi lại prompt tổng quan ban đầu bạn dùng để khởi tạo khung website.*

Bạn là một chuyên gia lập trình thiết kế web. giúp tôi tạo một Website Portfolio cá nhân hiện đại.
Hãy tuân thủ nghiêm ngặt các tiêu chuẩn kỹ thuật sau:
1. Chỉ sử dụng HTML5 thuần và CSS thuần (No Bootstrap, No Tailwind, No Javascript).
2. Cấu trúc HTML phải chuẩn Semantic HTML5, sử dụng rõ ràng các thẻ ngữ nghĩa: <header>, <nav>, <main>, <section>, <footer>. TUYỆT ĐỐI không lạm dụng thẻ <div> vô nghĩa.
3. Sử dụng CSS Variables (:root) để quản lý phối màu (gồm màu primary, secondary, background, text), font chữ và spacing.
4. Giao diện phải Responsive cơ bản bằng CSS Flexbox hoặc CSS Grid.
Trước tiên, hãy phân tích bố cục các Section cần có cho một website Portfolio và đề xuất bảng phối màu UI/UX hiện đại (gồm mã màu HEX cho :root). 


## 2. Quá trình tinh chỉnh & Giải quyết sự cố (Iteration Iterations)
### Lần 1: Dựng khung Semantic HTML & CSS Variable
- ** Prompt đã dùng: 
"Bảng màu rất tốt. Bây giờ hãy viết mã nguồn cho file index.html và style.css.
• File index.html phải lồng ghép đủ 5 thành phần ngữ nghĩa chính. Trong phần <main>, hãy chia thành ít nhất 3 khối <section> rõ ràng (Ví dụ: Hero, About, Projects).
• File style.css phải khai báo đầy đủ các CSS Variables đã chọn ở phần :root và ứng dụng xuyên suốt. Sử dụng Flexbox hoặc Grid để căn chỉnh layout cho khu vực danh sách dự án (Projects) dạng thẻ (cards).
• Tự viết hiệu ứng chuyển động :hover và :focus mượt mà cho các nút bấm (CTA) và các thẻ bài viết (cards).
Hãy viết code thật sạch, dễ đọc và chú thích rõ ràng bằng tiếng Việt."
- **Kết quả AI tạo ra: ** trang web đã có phần tốt nhưng chưa hoàn chỉnh và còn thiếu nhiều hiệu ứng
- **Nhận xét & Tinh chỉnh của SV:** Tôi nhúng AOS vào HTML và thêm `data-aos="fade-up"` nhưng cuộn trang không có hiệu ứng. Đồng thời, khi hover vào thẻ sản phẩm thì giao diện bị giật lắc, đè lên layout lưới CSS Grid. Hãy phân tích nguyên nhân và cung cấp giải pháp sửa lỗi bằng code.
### Lần 2: Tích hợp thư viện Animate.css & AOS
- **Prompt đã dùng: Bây giờ hãy tích hợp thêm hiệu ứng chuyển động động từ các thư viện:
1. Nhúng CDN của thư viện Animate.css và áp dụng hiệu ứng (ví dụ: animate__fadeInDown) cho phần tiêu đề lớn trong Hero Section.
2. Nhúng CDN và viết đoạn Script khởi tạo cho thư viện AOS (Animate On Scroll) để khi cuộn trang xuống, các <section> nội dung bên dưới sẽ tự động xuất hiện sinh động. **
- **Thách thức gặp phải:** AOS không chạy khi cuộn trang do quên thêm đoạn mã AOS.init(); phía cuối thẻ body hoặc import sai thứ tự script
- **Cách sửa prompt (Debug prompt):** Yêu cầu AI cung cấp đoạn mã script khởi tạo chính xác đặt ngay trước thẻ đóng </body>.
## 3. Đánh giá cá nhân về quá trình Vibe Coding
- AI đã giúp bạn tiết kiệm thời gian ở phần nào nhất?
> AI giúp tiết kiệm thời gian nhiều nhất ở khâu gõ các đoạn code boilerplate (khung xương HTML ban đầu), cấu hình nhanh bảng mã màu hệ thống trong CSS Variables và hướng dẫn cách phối hợp các thuộc tính CSS nâng cao (`will-change`, `box-shadow`) để làm mượt chuyển động mà không cần một dòng JavaScript nào.
- Bài học rút ra khi đặt câu hỏi (Prompt) cho AI trong thiết kế web?: Khi có giới hạn công nghệ nghiêm ngặt (như không dùng JavaScript), ta cần đưa từ khóa hạn chế "thuần CSS", "tuyệt đối không dùng JS" vào prompt ngay từ đầu. Khi xử lý lỗi giao diện bằng CSS, việc mô tả chi tiết hiện tượng lỗi (giật hình, lệch Grid) giúp AI đưa ra các thuộc tính tối ưu hóa phần cứng trình duyệt chính xác hơn.