---
description: Quy ước DTO request/response
globs: src/main/java/com/haitt/tinh_nhanh/dto/**/*.java
alwaysApply: false
---

# DTO

- Package `com.haitt.tinh_nhanh.dto`
- Dùng cho form Thymeleaf, request, response. Không dùng entity làm form object
- Đặt tên: `{Feature}Request`, `{Feature}Response`, hoặc `{Feature}Form` cho form
- Lombok `@Getter` `@Setter`. Có thể `@NoArgsConstructor` cho binding form
- Annotation validation đặt trên field của DTO (`@NotBlank`, `@Size`, constraint trong `validation`)
- Không chứa `@Entity`, repository, hay logic nghiệp vụ
- Mapping Entity ↔ DTO viết ở `service` (factory `from(entity)` hoặc mapper nhỏ trong DTO chỉ chuyển field)

```java
@Getter
@Setter
public class ExampleForm {
    @NotBlank
    @Size(max = 100)
    private String name;
}
```
