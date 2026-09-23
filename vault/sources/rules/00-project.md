---
description: Stack và phân layer của dự án tinh_nhanh
alwaysApply: true
---

# tinh_nhanh

- Spring Boot 4.1.1, Java 17, Gradle, MySQL, JPA, Thymeleaf, Bean Validation, Lombok
- Giao diện: Tailwind CSS 4 + DaisyUI (`static/css/input.css` → `output.css`; `npm run css:watch` khi sửa HTML)
- Web starter là `spring-boot-starter-webmvc` (không dùng `spring-boot-starter-web`)
- Package gốc: `com.haitt.tinh_nhanh`
- Layer: `entity` → `repository` → `service` → `controller` → `templates/{admin,user}`
- Hỗ trợ: `dto`, `exception`, `validation`, `utils`
- Controller trả về tên view Thymeleaf, không trả JSON, trừ khi task yêu cầu API
- Inject dependency qua constructor; không dùng `@Autowired` trên field
- Ưu tiên Lombok (`@RequiredArgsConstructor`, `@Getter`, `@Setter`) thay vì viết boilerplate tay
- Giữ thay đổi trong các thư mục hiện có; không tạo package song song (ví dụ `domain`, `infra`) trừ khi được yêu cầu
