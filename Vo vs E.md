# Vo vs E
Value object have no lifespan, structural identity, immutable and not persisted independently.

```java
Text(
    String originalContent,
    Map<LanguageCode, String> translations
){}
```


Good example of aggregate root

https://www.kranio.io/en/blog/de-bueno-a-excelente-en-ddd-entendiendo-aggregates-y-aggregate-roots-en-domain-driven-design---3-10

Question, can entities not be modified outside of the root? Like the User entity.

Aggregate roots can only reference other roots by ID.
