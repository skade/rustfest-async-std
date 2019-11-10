# async/.await with async-std

This repository holds my slides for my talk given at RustFest Barcelona 2019.

## Benchmarks

The benchmarks quoted in the slides can be collected from the following sources:

File reading benchmarks:

```sh
git clone https://github.com/stjepang/async-file-benchmark.git
cd async-file-benchmark
head -c 256K </dev/urandom >file.dat
cargo run --release
```

Threadpool benchmarks:

```sh
git clone https://github.com/stjepang/tokio.git
cd tokio
cargo bench --bench thread_pool
cargo bench --bench async_std
```

Ring benchmark:
```sh
git clone https://github.com/stjepang/ring-benchmark.git
cd ring-benchmark
cargo run --release --bin tokio
cargo run --release --bin async-std
```

Actix ships with an `ring.rs` example.

## A notice about Benchmarks

Every time you measure, everyone will look at their performance and improve the results.

The were measured on Saturday Nov. 9th. The moment you read this, they will probably have changed.

