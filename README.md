# CGDN-SpringBoot-JWT-MySql
## Chức năng của các class trong package "config":
+ WebSecurityConfig: Nơi sẽ khai báo các url nào bắt buộc phải login và cái nào không, cái phải login là cần gửi token khi request
+ JwtAuthenticationEntryPoint: Để reject(từ chối) tất cả các request mà không authenticate vào hệ thống (trừ các url không cần truyền token đã khai báo trong class WebSecurityConfig - .authorizeRequests().antMatcher). Nếu 1 request mà không đăng nhập thì sẽ ném về lỗi 403
+ JwtRequestFilter: Kiểm tra tất cả các request truyền lên server có hợp lệ hay không bằng việc kiểm tra token trên header
+ JwtTokenUtil: Có nhiệm vụ sinh ra token (sau khi login đúng) dựa vào khóa bí mật (secret) cung cấp trong file application.properties và validate token clien request
