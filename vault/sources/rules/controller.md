---
description: Quy ước MVC controller
globs: src/main/java/com/haitt/tinh_nhanh/controller/**/*.java
alwaysApply: false
---

# Controller

- Package `com.haitt.tinh_nhanh.controller`
- `@Controller` cho Thymeleaf. Chỉ dùng `@RestController` khi task yêu cầu JSON
- Tách theo vai trò: admin vs user. Prefix `/admin/**`; user dùng `/` hoặc `/app/**`
- Tên view khớp đường dẫn template: `admin/foo` → `templates/admin/foo.html`
- Form bind DTO trong `dto` + `@Valid` + `BindingResult`. Nếu `hasErrors()`, render lại cùng view
- Không inject `repository`. Chỉ gọi `service`. Lỗi nghiệp vụ để `exception` / `@ControllerAdvice` xử lý
- Inject qua constructor với `@RequiredArgsConstructor`
- POST thành công thì redirect (`redirect:/...`)

```java
@Controller
@RequestMapping("/admin/examples")
@RequiredArgsConstructor
public class AdminExampleController {
    private final ExampleService exampleService;

    @GetMapping
    public String list(Model model) {
        model.addAttribute("items", exampleService.list());
        return "admin/examples";
    }
}
```
