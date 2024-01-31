# SeL4 Rust Playground

## Build

We use a docker image as a builder to ease the building process.
The first image should only build the `kernel.elf` using a specified kernel config
and a predefined commit ref of the seL4 source.
