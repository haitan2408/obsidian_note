---
description: Quy ước Spring Data JPA repository
globs: src/main/java/com/haitt/tinh_nhanh/repository/**/*.java
alwaysApply: false
---

# Repository

- Chỉ là interface, package `com.haitt.tinh_nhanh.repository`
- Kế thừa `JpaRepository<Entity, Long>`
- Đặt tên: `{Entity}Repository`
- Query derived hoặc `@Query` JPQL. Không dùng native SQL trừ khi JPQL không làm được
- Trả `Optional<T>` khi tìm một bản ghi
- Không viết nghiệp vụ, mapping, hay HTTP status ở đây
- Không gọi `EntityManager` trừ khi cần custom fragment

```java
public interface ExampleRepository extends JpaRepository<Example, Long> {
    Optional<Example> findByName(String name);
    boolean existsByName(String name);
}
```
