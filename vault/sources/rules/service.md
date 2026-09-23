---
description: Quy ước tầng service
globs: src/main/java/com/haitt/tinh_nhanh/service/**/*.java
alwaysApply: false
---

# Service

- Package `com.haitt.tinh_nhanh.service`
- Class: `{Feature}Service` với `@Service` và `@RequiredArgsConstructor`
- Transaction: `@Transactional` cho method ghi; `@Transactional(readOnly = true)` cho method đọc
- Controller chỉ gọi service. Service gọi repository (và service khác)
- Map Entity ↔ DTO ở đây, không map trong controller
- Ném exception trong `exception` (ví dụ `ExampleNotFoundException`); không `return null` khi thiếu dữ liệu
- Không dùng `HttpServletRequest`, `Model`, hay kiểu Thymeleaf trong service

```java
@Service
@RequiredArgsConstructor
public class ExampleService {
    private final ExampleRepository exampleRepository;

    @Transactional(readOnly = true)
    public ExampleDto get(Long id) {
        return exampleRepository.findById(id)
                .map(ExampleDto::from)
                .orElseThrow(() -> new ExampleNotFoundException(id));
    }
}
```
