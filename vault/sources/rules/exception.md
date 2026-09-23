---
description: Quy ước exception và xử lý lỗi
globs: src/main/java/com/haitt/tinh_nhanh/exception/**/*.java
alwaysApply: false
---

# Exception

- Package `com.haitt.tinh_nhanh.exception`
- Exception nghiệp vụ kế thừa `RuntimeException`. Đặt tên rõ: `{Feature}NotFoundException`, `{Feature}AlreadyExistsException`
- Service ném exception này; không ném `IllegalArgumentException` chung chung cho lỗi nghiệp vụ
- Gom xử lý HTTP/view ở `@ControllerAdvice` trong package này (ví dụ `GlobalExceptionHandler`)
- MVC/Thymeleaf: handler trả về view lỗi hoặc flash + redirect, không trả JSON trừ khi có API
- Không nuốt exception (`catch` rỗng). Không để controller tự `try/catch` rồi set status nếu advice đã lo

```java
public class ExampleNotFoundException extends RuntimeException {
    public ExampleNotFoundException(Long id) {
        super("Không tìm thấy example: " + id);
    }
}
```
