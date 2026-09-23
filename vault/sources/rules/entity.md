---
description: Quy ước entity JPA
globs: src/main/java/com/haitt/tinh_nhanh/entity/**/*.java
alwaysApply: false
---

# Entity

- Một class = một bảng. Package `com.haitt.tinh_nhanh.entity`
- Dùng `@Entity` và `@Table(name = "snake_case")`
- Id: `Long` + `@Id` + `@GeneratedValue(strategy = GenerationType.IDENTITY)`
- Lombok: `@Getter` `@Setter` `@NoArgsConstructor`. Không dùng `@Data` trên entity (equals/hashCode với collection lazy)
- Tên cột: snake_case qua `@Column(name = "...")` khi khác tên Java
- Quan hệ: `@ManyToOne(fetch = FetchType.LAZY)` mặc định. Không dùng `EAGER`
- Không viết repository, service, hay logic HTTP trong entity
- Không đưa entity trực tiếp ra form Thymeleaf; dùng DTO trong `dto`

```java
@Entity
@Table(name = "example")
@Getter
@Setter
@NoArgsConstructor
public class Example {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
}
```
