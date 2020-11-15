---
title: To stutter, or not to stutter?
date: "2020-10-08T08:00:00Z"
description: "Naming can be hard."
---

The simplest way to explain code stutter is an example.

```go
// stutter
server := http.HTTPServer{}

// no stutter
server := http.Server{}
```

### Golang

In Go, [the answer](https://golang.org/doc/effective_go.html#package-names) is simple. Avoid stutter when possible. Instead of `notification.SendNotification()`, we can write `notification.Send()`. The decision is easy because Go's package imports are easy. You typically import and call upon a package by name, rather than polluting the current namespace with extra bloat. This pattern can be seen commonly across the Go standard library.

```go
t, err := time.Parse(time.Kitchen, "6:06PM")
ctx = context.WithTimeout(ctx, 10*time.Second)
```

### Rust

In Rust, it gets more complex. Rust allows you to import types directly, or access them through the module name.

```rust
// Import the type directly
use log::Level;
let level = Level::Error;

// Access through the log package
use log;
let level = log::Level::Error;
```

If I'm importing `log::Level` directly, it might make sense to name the enum `LogLevel`. Both cases can be seen in the Rust standard library.

```rust
// stutter
use std::sync::atomic::AtomicUsize;

// no stutter
use std::io::Result;
use std::thread::Result;
```

So which one should you be using?

### Readability

We write code for people, not computers. It's extremely important to remember that. So when we write code, we must consider how the code will be used and read before making naming decisions. This is why I don't think there is a single solution to this question. Instead the answer is "it depends".

For code that I intend to import by package/module name and expect others to do the same, I will avoid stuttering. For code that is typically imported fully, such as in a [prelude](https://stackoverflow.com/questions/36384840/what-is-the-prelude), I will opt for the more verbose name to avoid namespace clashes.