# tinh_nhanh

Spring Boot 4.1.1, Java 17, Gradle, MySQL, JPA, Thymeleaf, Validation, Lombok.

Giao diện: Tailwind CSS 4 + DaisyUI. Build CSS: `npm run css:build` / `npm run css:watch`.


Package gốc: `com.haitt.tinh_nhanh`

## Bản đồ layer

| Package / thư mục  | Trách nhiệm                                           |
| ------------------ | ----------------------------------------------------- |
| [[entity]]         | Chỉ chứa entity JPA                                   |
| [[repository]]     | Spring Data JPA repository                            |
| [[service]]        | Logic nghiệp vụ                                       |
| [[dto]]            | Form / request / response, không dùng entity làm form |
| [[exception]]      | Exception nghiệp vụ + `@ControllerAdvice`             |
| [[controller]]     | HTTP + tên view Thymeleaf                             |
| [[validation]]     | Validator / constraint tùy chỉnh                      |
| [[utils]]          | Helper không trạng thái                               |
| `templates/layout` | Layout Thymeleaf (`user`, `admin`)                    |
| `templates/admin`  | Giao diện admin                                       |
| `templates/user`   | Giao diện người dùng                                  |
| `static/css`       | `input.css` (nguồn) → `output.css` (Tailwind)         |

Không đặt logic nghiệp vụ trong controller, entity, hoặc utils.

Feature mới: Entity → Repository → Service (DTO + exception) → Controller → Template.

Cấu hình nằm ở `src/main/resources/application.properties`. Không hardcode thông tin DB trong Java.
