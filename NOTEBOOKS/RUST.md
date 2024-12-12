# RUST

- [RUST](#rust)
  - [Hello World en consola](#hello-world-en-consola)
  - [CARGO](#cargo)
    - [Crear Nuevo Proyecto con CARGO](#crear-nuevo-proyecto-con-cargo)
    - [Ejecutar Proyecto con CARGO](#ejecutar-proyecto-con-cargo)
    - [Construir Proyecto con CARGO](#construir-proyecto-con-cargo)


## Hello World en consola

- [x] Instalar Rust

```bash
curl https://sh.rustup.rs -sSf | sh
```

- [x] Checar versión de Rust

```bash
rustup --version
```

- [x] Agregar extensión **rust-analyzer** para VSC

```rust
fn main(){
  print!("Hello World");
}
```
- [x] Compilar

```bash
rustc hello.rs
```
- [x] Ejecutar

```bash
./hello
```

## CARGO

> Es un Framework YA incluido con la instalación de Rust

### Crear Nuevo Proyecto con CARGO

```bash
cargo new proyecto
```

### Ejecutar Proyecto con CARGO

- [x] Dentro de la carpeta del proyecto ejecutar:

```bash
cargo run
```

### Construir Proyecto con CARGO

```bash
cargo build --release
```



