---
description: Quy ước class tiện ích
globs: src/main/java/com/haitt/tinh_nhanh/utils/**/*.java
alwaysApply: false
---

# Utils

- Package `com.haitt.tinh_nhanh.utils`
- Chỉ helper không trạng thái (format ngày, slug, mặc định phân trang)
- Class `final` + constructor private, hoặc method `public static`
- Không Spring bean, không `@Autowired`, không gọi repository/service
- Nếu cần DI hoặc transaction thì đưa sang `service`, không để trong `utils`
- Không tạo class gom tất cả kiểu `StringUtils` / `CommonUtils`. Đặt tên theo việc: `DateTimes`, `Slugs`
