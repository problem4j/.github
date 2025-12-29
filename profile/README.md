![Problem4J Banner](./img/banner.jpeg)

Designing clear and consistent error responses in a REST API is often harder than it looks. Without a shared standard,
each application ends up inventing its own ad-hoc format, which quickly leads to inconsistency and confusion.
[RFC 7807 - Problem Details for HTTP APIs][rfc7807] solves this by defining a simple, extensible JSON structure for
error messages.

**Problem4J** brings this specification into the Java ecosystem, offering a practical way to model, throw, and handle
API errors using `Problem` objects. It helps you enforce a consistent error contract across your services, while staying
flexible enough for custom exceptions and business-specific details.

An example of `application/problem+json` response on HTTP API would look as follows.

```json
{
  "status" : 400,
  "title" : "Bad Request",
  "detail" : "Validation failed",
  "errors" : [ {
    "field" : "email",
    "error" : "must be a well-formed email address"
  }, {
    "field" : "age",
    "error" : "must be greater than or equal to 18"
  } ]
}
```

It focuses on a minimal core API with optional integrations for popular Java frameworks.

## Modules

- [**`problem4j-core`**](https://github.com/problem4j/problem4j-core) - core `Problem` model
- [**`problem4j-jackson`**](https://github.com/problem4j/problem4j-jackson) - JSON (de)serialization support
- [**`problem4j-spring`**](https://github.com/problem4j/problem4j-spring) - Spring & Spring Boot integration

## Documentation

📘 https://problem4j.github.io

The documentation includes usage guides, examples, and module-specific details.

---

Problem4J aims to be small, explicit, and framework-friendly.

[rfc7807]: https://datatracker.ietf.org/doc/html/rfc7807
