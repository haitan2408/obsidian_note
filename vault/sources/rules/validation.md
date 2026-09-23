---
description: Bean Validation và constraint tùy chỉnh
globs: src/main/java/com/haitt/tinh_nhanh/validation/**/*.java
alwaysApply: false
---

# Validation

- Package `com.haitt.tinh_nhanh.validation`
- Ưu tiên annotation Jakarta trên DTO (`@NotBlank`, `@Size`, `@Email`, `@Min`)
- Constraint tùy chỉnh = annotation + `ConstraintValidator` trong package này
- Validator không trạng thái. Chỉ inject repository khi cần kiểm tra uniqueness
- Không validate trong controller bằng `if (x == null)` nếu annotation đã diễn tả được
- Có thể dùng message tiếng Việt trong `message =`; nên để message key nếu sau này i18n

```java
@Target(ElementType.FIELD)
@Retention(RetentionPolicy.RUNTIME)
@Constraint(validatedBy = UniqueExampleNameValidator.class)
public @interface UniqueExampleName {
    String message() default "Tên đã tồn tại";
    Class<?>[] groups() default {};
    Class<? extends Payload>[] payload() default {};
}
```
