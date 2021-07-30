
This repo is similar to
[nucli-reed](https://github.com/stormasm/nucli-reed)
in the fact that it keys off a versioned nushell
instead of having al of the crates built in.


[rustyline version 8.1.0](https://github.com/nushell/nushell/blob/main/crates/nu-cli/Cargo.toml#L29) is the crate currently used by the nu-cli crate.

The following crates are included so one can modify them...

* nu-cli
* nu-completion

Also in the nu-cli crate
[rustyline version ](https://github.com/stormasm/rustyline81)
is available as its own crate in
which one can modify it to see how things work locally...

```rust
rustyline = { git = "https://github.com/stormasm/rustyline81", branch = "main", optional=true }
```

This crate can not be included along with the other crates because of the
cyclical dependency issue of cargo with the interior rustyline-derive crate.
