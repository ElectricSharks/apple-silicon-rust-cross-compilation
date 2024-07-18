# Apple Silicon Rust - Cross Compilation

This repo contains a dockerfile that can be used to cross compile rust code for an apple silicon target.

Apple silicon uses a custom build of the gcc linker/assembler for LLVM backended languages. This can lead to issues if, for example, you wish to build a binary in a docker container to be run locally (docker Apple silicon runs under a hypervisor).

Additionally, at time of writing rust uses a custom build of LLVM for its target IR, so you can't generate the target IR and then assemble locally.

This docker image uses zig as the assembler/linker in addition to cargo-zigbuild to resolve these issues. Note that there are simpler solutions (eg. just building rust locally on an apple silicon Mac), but this is naturally use-case dependent.

The shell scripts contain the relevant quickstart scripts for building/running the image and building the binary.
