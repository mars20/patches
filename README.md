# RISC-V tool Patches

This repository contains patches for RISC-V tools

## Building spike to dump "histogram of executed instruction"

As a first set get a copy of RISC-V tools, we use a specific commit of the tools

```
git clone git@github.com:riscv/riscv-tools.git $RISCV_TOOLS
cd $RISCV_TOOLS
git reset --hard 8ad8d4839acf2cdac0129b8fed8fe12136e77307

```
Download the patch files from this repository

```
git clone https://github.com/mars20/patches.git $RISCV_PATCHES
cd $RISCV_TOOLS
git apply $RISCV_PATCHES/patches_spike/spike_insn_histogram.patch

```

Build the RISC-V toolchain

```
cd $RISCV_TOOLS
./build.sh

```

Now you can execute a binary with `spike -i <binary>` to get histogram of
dynamic instruction trace
