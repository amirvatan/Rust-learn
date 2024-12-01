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
also there is constant type that variable vaule is not allowed to change and there is a few different between constant and immutable variables.

- you are not allowed to use **mut** keyword with constant type.
- you declare constant variable wiht **const** keyword instead of **let**.
- a constant variable must set to a constant expression and not a runtime value.

### Data Types 

#### Scalar Types 
A scalar type represents a single value. Rust has four primary scalar types: integers, floating-point numbers, Booleans, and characters.
##### Integres And Floating-Points 
|Length | Signed | Unsigned | 
| --- | --- | --- |
| 8-Bit | i8 | u8 |
| 16-Bit | i16 | u16 |
| 32-Bit | i32 | u32 |
| 64-Bit | i64 | u64 |
| 128-Bit | i128 | u128 |
|arch  | isize | usize | 

default type of an integre is i32.
```rust
let x: u32 = 1000;
```

For floating points we have **f32** and **f64** types and the default one is **f64**. 

#### Compound Types
Compound types can group multiple values into one type. Rust has two primitive compound types: tuples and arrays.

##### Tuple Type
A tuple is a general way of grouping together a number of values with a variety of types into one compound type.

```rust
    let tup: (i32, f64, u8) = (500, 6.4, 1);
```
We can also access a tuple element directly by using a period (.) followed by the index of the value we want to access.

##### Array Type 
Collection of multiple values with same type called array.
```rust
let array = [9,3,4,1,7]; // array with type i32 and size of 5 
let array : [u32,5] = [1,2,3,4,5]; // array with specified type and size
let array = [3; 5]; // array with 5 element set to 3   
```

### Functions 
For declaring function in rust we use **fn** keyword followd by function name like below : 

```rust 
fn main(){
    // some code
}
```

**Rust code uses snake case as the conventional style for function and variable names, in which all letters are lowercase and underscores separate words.**

### Control Flow 
The ability to run some code depending on whether a condition has met.

##### If Expression
```rust 
if condition {
// code
} else {
// code
}
```

##### Using if in a let Statement
```rust 
let x = if condition {5} else {6}
```

##### Loop 
The loop keyword tells Rust to execute a block of code over and over again forever or until you explicitly tell it to stop.

```rust 
loop {
//code
}
```
##### Returning Values from Loops

```rust
let result = loop {
        counter += 1;

        if counter == 10 {
            break counter * 2;
        }
    };
```


