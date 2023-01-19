# rust-new-project-template

All Rust projects can follow this pattern:

1.  Create a new repo using Rust New Project Template:  https://github.com/noahgift/rust-new-project-template
2.  Create a new Codespaces and use it
3.  Use `main.rs` to call handle CLI and use `lib.rs` to handle logic and import `clap` in `Cargo.toml` as shown in this project.
4.  Use `cargo init --name 'hello' or whatever you want to call your project.
5.  Put your "ideas" in as comments in rust to seed GitHub Copilot, i.e //build add function
6.  Run `make format` i.e. `cargo format`
7.  Run `make lint` i.e. `cargo clippy --quiet`
8.  Run project:  `cargo run -- --help`
9.  Push your changes to allow GitHub Actions to: `format` check, `lint` check, and other actions like binary deploy.


This pattern is a new emerging pattern and is ideal for systems programming in Rust.

![1 1-prompt-engineering](https://user-images.githubusercontent.com/58792/213335664-f459e6ac-018a-4ccf-9563-bbe6d49d72d1.png)


### Reproduce
A good starting point for a new Rust project

To run: `cargo run -- marco --name "Marco"`
Be careful to use the NAME of the project in the `Cargo.toml` to call `lib.rs` as in:

```
[package]
name = "hello"
```

For example, see the name `hello` is invoked alongside `marco_polo` which is in `lib.rs`.

```rust
fn main() {
    let args = Cli::parse();
    match args.command {
        Some(Commands::Marco { name }) => {
            println!("{}", hello::marco_polo(&name));
        }
        None => println!("No command was used"),
    }
}
```







## References

* [rust-cli-template](https://github.com/kbknapp/rust-cli-template)
