<h1 style="color:#FF6500">RUST</h1>

- [BASICO](#basico)
  - [Introducción](#introducción)
  - [Hello World en consola](#hello-world-en-consola)
  - [Crear Nuevo Proyecto con CARGO](#crear-nuevo-proyecto-con-cargo)
  - [Ejecutar Proyecto con CARGO](#ejecutar-proyecto-con-cargo)
  - [Construir Proyecto con CARGO](#construir-proyecto-con-cargo)
  - [Checar con Cargo](#checar-con-cargo)

# BASICO

## Introducción

- [x] Rust __NO__ es Orientado a Objetos ni tiene Herencia
- [x] Utiliza __struct__ para representar datos complejos
- [x] Utiliza __traits__ para describir cómo se comporta el struct
- [x] Las variables son __inmutables__ por default



## Hello World en consola

- [x] Instalar Rust

```bash
curl https://sh.rustup.rs -sSf | sh
```

- [x] Checar versión de Rust

```bash
rustup --version
```

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
- [x] Agregar extensión **rust-analyzer** para VSC

- [x] Checar CARGO ```cargo --version```

> Es un Framework YA incluido con la instalación de Rust

## Crear Nuevo Proyecto con CARGO

```bash
cargo new proyecto
```

## Ejecutar Proyecto con CARGO

- [x] Dentro de la carpeta del proyecto ejecutar:

```bash
cargo run
```

## Construir Proyecto con CARGO

```bash
cargo build --release
```

## Checar con Cargo

```bash
cargo check
```

- [x] No Compila Ni Ejecuta, solo REVISA

