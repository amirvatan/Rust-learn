# Learning Rust  
table of contents : 
- Installation 
- Cargo 
- Common Programming Concepts

## Installation
You can install rust with just running the command below : 
```bash
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
confirm your rust installation with : 
```bash 
rustc --version
```
and you should get something like this : 
```bash
rustc 1.83.0 (90b35a623 2024-11-26)
```
you can compile and run rust program named main.rs with : 
```bash 
rustc main.rs
./main
```

## Cargo 
Cargo is Rust’s build system and package manager.
you can crate a new project using cargo : 
```bash 
cargo new myproject
```
this command will create a directory named myproject with structure like this : 
```bash 
.
├── Cargo.toml
└── src
    └── main.rs
```
there is cargo config in Cargo.toml and your source codes under src directory.

You can build your project in target/debug/project-name with : 
```bash 
cargo build 
```
or build and run with : 
```bash 
cargo run 
```
and you can use this command to check if there is no compile error in your project without compiling it : 
```bash 
cargo check
```
also you can use --release flag for compile with Optimization : 
```bash
cargo build --release
```
## Common Programming Concepts

### variables and mutability
you can define a variable with **let** keyword but you should be careful that you can not change a variable value when it's not mutable.if you try to change value of x variable you will get a compile error.

```rust
fn main(){
    let x = 5; // can't change x value
    let mut y = 5; // y is mutable so i can change it's value.
    println!("y value is : {y}");
    y = y + 1;
    println!("y value is : {y}");
}
```
