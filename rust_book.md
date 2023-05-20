# Rust Lang Book

### The Rust main function
The function `main` is special because it is always the first that runs in every executable Rust program.

```rust
fn main() {

}
```

### Compiling and Running

Compiling a rust code are different step than running.
You need to pass the rust compiler the name of the source file like:

```bash
rustc main.rs
```

After that you can run the executable file in linux like:
```bash
./main
```

### Cargo

Cargo is the tool that can do a lot of tasks, such as building your code, downloading the external libraries that your code depends on, and also building those libraries.

To create a new cargo project just run:
```bash
cargo new hello_cargo
```

And to build your project, run:
```bash
cargo build
```
That will generate a executable file in `./target/debug/hello_cargo`.

You can also use the command to build and run your code with:

```bash
cargo run
```

And the command to verify if your program compiles but without generating a executable:
```bash
cargo check
```

Once your code is finally ready for a release, you can run this code to compile for release with some additional compiler optimization for production:

```bash
cargo build --release
```

### Rust

To accept the user input, we can load the io input/output library, using the use statement:

```rust
use std::io;
```

The we can create a variable to store the user input like this:

```rust
let mut guess = String::new();
```

In rust the variables area immutable by default, but we can use the `mut` to create a mutable variable.

String is a string type that is growable, UTF-8 encoded bit of text. 

The `::new` line indicates that new is an associated function of the String type. An associated function is a function that is implemented on a type, in this case a String.

We can print variables with print placeholders:
```rust
println!("You guessed: {guess}");
```

Unless specified, rust number is defaulted to a i32 32-bit number.
