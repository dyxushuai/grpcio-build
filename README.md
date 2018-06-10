# A build script tool to generate grpc and protobuf files

## Required

- The v3 `protoc` command in `$PATH`

## Example code in `build.rs`:

```rust
extern crate protoc_grpc;

fn main() {
    protoc_grpc::run(protoc_grpc::Args {
        // --grpc_out=args
        out_dir: "src/",
        // List of .proto files to compile
        input: &["proto/a.proto"],
        // -I args
        includes: &["proto"],
        // include protobuf specifies and grpc specifies
        rust_protobuf: true,
    }).expect("protoc");
}
```

### In `Cargo.toml`
```
[build-dependencies]
protoc-rust = "x.x.x"
```