# emit_seq

[Seq](https://getseq.net) collector for the emit structured logger.

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
