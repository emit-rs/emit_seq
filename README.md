> **Archived:** This project is based on the old `0.10.x` version of `emit` and isn't compatible with newer versions.

# emit_seq [![Join the chat at https://gitter.im/serilog/serilog](https://img.shields.io/gitter/room/emit/emit-rs.svg)](https://gitter.im/emit-rs/emit) [![Crates.io](https://img.shields.io/crates/v/emit_seq.svg)](https://crates.io/crates/emit_seq)

[Seq](https://getseq.net) collector for the [emit](https://github.com/emit-rs/emit) structured logger.

### Using the crate

In `Cargo.toml`:

```toml
[dependencies]
emit="*"
emit_seq="*"
```

In `main.rs`:

```rust
#[macro_use]
extern crate emit;
use emit::PipelineBuilder;
use emit_seq::SeqCollector;

fn main() {
    let _flush = PipelineBuilder::new()
        .send_to(SeqCollector::new("https://my-seq-server"))
        .init();

    info!("Hello, {}!", user: "World");
}
```
