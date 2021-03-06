Creating an ink! Project
===

We are going to use the ink! CLI to generate the files we need for a Substrate smart contract project.

Make sure you are in your working directory, and then run:

```bash
cargo contract new flipper
```

This command will create a new project folder named `flipper` which we will explore:

```bash
cd flipper/
```

**ink! Contract Project**

```
flipper
  └─ lib.rs                <-- Contract Source Code
  └─ Cargo.toml            <-- Rust Dependencies and ink! Configuration
  └─ .gitignore
```

## Contract Source Code

The ink CLI automatically generates the source code for the "Flipper" contract, which is about the simplest "smart" contract you can build. You can take a sneak peak as to what will come by looking at the source code here:

<a href='https://github.com/paritytech/ink/blob/v3.0.0-rc4/examples/flipper/lib.rs' target='_blank'>Flipper Example Source Code</a>

The Flipper contract is nothing more than a `bool` which gets flipped from true to false through the `flip()` function. We won't go deep into the details of this source code because we will be walking you through the steps of building a more advanced contract!

## Testing Your Contract

You will see at the bottom of the source code there are simple test cases which verify the functionality of the contract. We can quickly test this code is functioning as expected using the **off-chain test environment** that ink! provides.

In your project folder run:

```bash
cargo +nightly test
```

To which you should see a successful test completion:

```bash
$ cargo +nightly test
    running 2 tests
    test flipper::tests::it_works ... ok
    test flipper::tests::default_works ... ok

    test result: ok. 2 passed; 0 failed; 0 ignored; 0 measured; 0 filtered out
```

Now that we are feeling confident things are working, we can actually compile this contract to Wasm.
