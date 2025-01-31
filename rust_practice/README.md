# Rust Installation
Extremely straightforward on linux: [Installation](https://www.rust-lang.org/tools/install)

# Rust tools for IDEs/Editors
https://www.rust-lang.org/tools

# Creating a rust script
The script must end with `.rs`. For instance the script in this dir `hello.rs` is a rust script, which obviously prints `hello world` and something else.

## Executing a rust script
There are two ways of executing a rust script:
1. Compile the script and execute it with `./{script name}`
2. Use `cargo` to build and execute
### Method 1
First `hello.rs` needs to be compiled before it can be run. To compile it use:
```sh
rustc hello.rs
```
This will generate a `hello` compiled file **without any extensions**.
Execute the compiled file with
```sh
./hello
```
This will execute it and print the results in the terminal(if there's something to print in the first place).

### Method 2
The faster way to execute a script is to build a cargo project.

#### Create a new cargo project
```sh
cargo new {project name}
```
This will create a new project with all the necessary files, one of them being `main.rs`, to execute rust scripts inside it.

#### Execute script with cargo
Navigate to the cargo project dir.
##### One script in the project dir
**IF ONE HAS A SINGLE RUST SCRIPT** in the project then it's as easy as:
```sh
cargo build
cargo run
```
This will compile and execute the rust script i.e. `main.rs`. 

##### Many scripts in the project dir
**IF ONE HAS MANY SCRIPTS** in the project then:
Declare the module in `main.rs` by 
```rust
mod {module/script name};
```
Call the entire module in the main function of `main.rs`:
```rust
fn main() {
	{module/script name}::{function name}();
}
```
Then: 
```sh
cargo build
cargo run
```
This will execute the script from within the `main.rs`.

There are other ways to do this as well for instance:
- Create a bin dir
```sh
mkdir src/bin
mv {some script.rs} {another script.rs} src/bin
```
Execute:
```sh
cargo run --bin  {some script.rs}
cargo run --bin  {another script.rs}
```




# What's cargo ???
Cargo is the Rust package manager and build system. It simplifies the process of managing Rust projects by handling tasks like building code, downloading dependencies, and running tests. Here’s a quick overview of what Cargo can do:

- Create New Projects: Initialize new Rust projects with `cargo new`.
- Build Projects: Compile your code with `cargo build`.
- Run Projects: Build and run your code with `cargo run`.
- Manage Dependencies: Add and update dependencies in your `Cargo.toml` file.
- Run Tests: Execute tests with `cargo test`.
- Documentation: Generate documentation for your project with `cargo doc`.