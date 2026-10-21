Đóng vai là Chuyên gia Lập trình Frontend Senior và UI/UX Designer. Hãy xây dựng mã nguồn hoàn chỉnh cho bài kiểm tra giữa kỳ môn "Thiết kế Web" theo phương pháp Vibe Coding.

ĐỀ TÀI: Website Personal Portfolio một trang (single-page) của Hoàng Hải Đăng, phong cách Dark Modern / Cyberpunk, thẩm mỹ cao, hoàn thiện tỉ mỉ.

SẢN PHẨM: 2 file riêng biệt, index.html và style.css, chạy trực tiếp trên trình duyệt (không cần framework).

1. SEMANTIC HTML5
- Dùng đúng ngữ nghĩa: <header>, <nav>, <main>, <section>, <article>, <footer>. Dùng thêm <aside>, <figure>, <figcaption>, <address>, <blockquote>, <output> khi phù hợp.
- Tuyệt đối không dùng thẻ <div>. Mọi card (bento, dự án, liên hệ) phải là <article>.
- Danh sách card dùng <ul>/<li>. Thẻ <li> chịu hiệu ứng AOS, thẻ <article> bên trong chịu hiệu ứng hover, để hai hiệu ứng không đè lên nhau.
- Hỗ trợ truy cập: liên kết "bỏ qua đến nội dung chính", aria-label cho nav, alt rõ ràng cho mọi ảnh.

2. CSS & CSS VARIABLES (style.css)
- Khai báo tại :root: --primary-color (cyan #00f0ff), --secondary-color (tím #7b2ff7), --accent-pink (hồng #ff2e97), biến font (Orbitron cho tiêu đề, Be Vietnam Pro cho nội dung), biến spacing (xs đến xl), bán kính, transition, glow shadow.
- Nền đậm đà, sống động: nhiều lớp radial-gradient (mesh gradient), lớp lưới cyberpunk mờ và lớp gradient trôi chậm bằng animation. Không để nền trống.
- Layout: CSS Grid cho Bento Grid (4 cột, các ô có kích thước khác nhau) và danh sách dự án (auto-fit); CSS Flexbox cho header, navigation và footer.
- Responsive đủ 3 mốc (992px, 768px, 480px), menu hamburger thuần CSS cho điện thoại.
- Tôn trọng prefers-reduced-motion (tắt animation, đặt iteration-count: 1).

3. THƯ VIỆN & HIỆU ỨNG
- Tích hợp CDN Animate.css 4.1.1: áp dụng cho Hero (fadeInDown, fadeInLeft, fadeInUp, zoomIn, bounce). Tiêu đề các section chạy Animate.css khi cuộn tới bằng IntersectionObserver.
- Tích hợp CDN AOS 2.3.4, gọi AOS.init({ duration: 800, easing: 'ease-out-cubic', once: true, offset: 80 }) cho các section và card. Nếu AOS không tải được thì gỡ data-aos để nội dung không bị ẩn.
- Viết tay hiệu ứng :hover, :focus, :focus-visible, :focus-within với hiệu ứng nổi (translateY) và đổ bóng phát sáng (glow shadow) cho nút .btn, thẻ bento-card, project-card, input, liên kết. Card bento có tabindex="0" để nhận :focus.
- Lưu ý kỹ thuật: Animate.css và animation float không được ghi đè nhau (đặt float trên thẻ <aside> bọc ngoài avatar, còn <figure> bên trong giữ zoomIn).

4. KHUNG ẢNH NEON (IMAGE PLACEHOLDERS)
- Viền gradient neon phát sáng, ảnh luôn lấp đầy khung (object-fit: cover), mỗi <img> có alt, width, height.
- Avatar Hero: hình khối hữu cơ 1:1, lơ lửng, vòng đứt nét xoay quanh, nhãn "Available for work".
- Ảnh hoạt động (About): tỷ lệ 3:2, nhãn "Hoạt động & sự kiện".
- Ảnh xem trước dự án: tỷ lệ 16:10, nhãn "Dự án 01/02/03", phóng nhẹ khi hover.

5. NỘI DUNG CÁC PHẦN
- Header/Nav: logo "HHĐ.", 4 liên kết (Trang chủ, Giới thiệu, Dự án, Liên hệ), nút "Thuê tôi".
- Hero: nhãn nghề nghiệp, tiêu đề "Xin chào, tôi là Hoàng Hải Đăng" (chữ gradient), mô tả, 2 nút, avatar, mũi tên cuộn xuống.
- Giới thiệu (Bento Grid, 8 ô): Tôi là ai, ảnh hoạt động, Kỹ năng (HTML5, CSS3, JavaScript, Responsive, Figma, Git), 2 ô số liệu (10+ dự án, 100% đam mê UI/UX), Học vấn, Sở thích, Phương châm.
- Dự án (3 card): Website bán hàng, Landing Page sự kiện, Dashboard quản lý. Mỗi card có ảnh, mô tả, tag công nghệ, nút "Xem demo" và "Mã nguồn".
- Liên hệ: cột thông tin (email, điện thoại, địa điểm) và form (họ tên, email, lời nhắn), có thông báo khi gửi (chỉ là demo).
- Footer: bản quyền, liên kết GitHub / Facebook / LinkedIn.

6. KIỂM TRA TRƯỚC KHI GIAO
- Đối chiếu từng yêu cầu của đề; xác nhận không có thẻ <div>, tag đóng mở đúng, mọi liên kết # đều trỏ tới id tồn tại, hover/focus hoạt động trên cả card có AOS.
- Giải thích ngắn cách sửa nếu phát hiện xung đột giữa AOS, Animate.css và hiệu ứng hover.