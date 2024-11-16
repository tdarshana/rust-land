# Learning Rust

---

## Cargo

**Cargo Create a new project**

```bash
cargo new <project-name>
```

**Cargo Deploy**

```bash
cargo run
```

**Cargo Build Only**

```bash
cargo Build
```

**Cargo Check**

```bash
cargo Check
```

**Cargo Build Release**

```bash
cargo build --Release
```

**Cargo Tree**

View the dependency tree of the cargo project.

```bash
cargo Tree
```

Find a specific package in the dependency tree.

```bash
cargo tree -i -p <package-name>
```

## Rust References

The & indicates that this argument is a reference, which gives you a way to let multiple parts of your code access one piece of data without needing to copy that data into memory multiple times. References are a complex feature, and one of Rust’s major advantages is how safe and easy it is to use references. You don’t need to know a lot of those details to finish this program. For now, all you need to know is that, like variables, references are immutable by default. Hence, you need to write &mut guess rather than &guess to make it mutable. (Chapter 4 will explain references more thoroughly.)

### Rust Enums & Comparing Values

`std::cmp::Ordering` into scope from the standard library. The `Ordering` type is another enum and has the variants `Less`, `Greater`, and `Equal`. These are the three outcomes that are possible when you compare two values.

```rust
use rand::Rng;
use std::cmp::Ordering;
use std::io;

fn main() {
    // --snip--

    println!("You guessed: {guess}");

    match guess.cmp(&secret_number) {
        Ordering::Less => println!("Too small!"),
        Ordering::Greater => println!("Too big!"),
        Ordering::Equal => println!("You win!"),
    }
}
```
