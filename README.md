# construction
Con-struct-ion - Marcos for generating struct definitions 

WORK IN PROGRESS...


## Idea
Allow generation/definition of structs.

```rust
struct A {
    foo: String,
    bar: Option<String>
}

#[construction(extend=A)]
struct B;

// generates:
struct B {
    foo: String,
    bar: Option<String>
}

#[construction(extend=A)]
struct C {
    baz: u64   
}

// generates:
struct C {
    foo: String,
    bar: Option<String>,
    baz: u64
}

#[construction(extend=A, omit=[foo])]
struct D {
    baz: u64
}

// generates:
struct D {
    bar: Option<String>,
    baz: u64
}
```