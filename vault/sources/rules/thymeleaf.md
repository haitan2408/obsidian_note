---
description: Quy ước template Thymeleaf
globs: src/main/resources/templates/**/*.html
alwaysApply: false
---

# Thymeleaf

- Màn admin: `templates/admin/` dùng `layout/admin.html`
- Màn user: `templates/user/` dùng `layout/user.html`
- Tên view `admin/dashboard` → `templates/admin/dashboard.html`
- Layout: `th:replace="~{layout/user :: html('Tiêu đề', ~{::content})}"` và `th:fragment="content"`
- CSS: Tailwind + DaisyUI. Class utility / DaisyUI (`btn`, `navbar`, `drawer`). Không thêm Bootstrap
- File CSS biên dịch: `static/css/output.css`. Sửa `input.css` rồi `npm run css:build` hoặc `css:watch`
- Dùng `th:text`, `th:href`, `th:object`, `th:field`, `th:each`
- Form POST về controller; lỗi bằng `#fields.hasErrors` / `th:errors`
- Không viết logic nghiệp vụ trong template
