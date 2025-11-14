<h1 style="color:#FF6500">RUST</h1>

# Hello World en consola

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

# CARGO

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


# PRIMEROS PROGRAMAS

## Recibir parametros

```rust
use std::env;
fn main(){
    let args: Vec<String> = env::args().collect();
    if args.len()>1{
        for arg in args.iter().skip(1){
            println!("- {}",arg);
        }
    }else{
        println!("No proporcionaste parametros");
    }

}
```
