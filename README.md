# Cage: Hardware-Accelerated Safe WebAssembly

This repository contains the links to the different repositories developed for Cage.

- LLVM: https://github.com/TUM-DSE/llvm-memsafe-wasm
- wasmtime: https://github.com/TUM-DSE/wasmtime-mte
- wasm-tools: https://github.com/TUM-DSE/wasm-tools-mte
- wasi-libc: https://github.com/martin-fink/wasi-libc

The artifact is available at https://doi.org/10.5281/zenodo.13772996.

## Abstract

WebAssembly (WASM) is an immensely versatile and increasingly popular compilation target. It executes applications written in several languages (e.g., C/C++) with near-native performance in various domains (e.g., mobile, edge, cloud).
Despite WASM's sandboxing feature, which isolates applications from other instances and the host platform, WASM does not inherently provide any memory safety guarantees for applications written in low-level, unsafe languages.

To this end, we propose Cage, a hardware-accelerated toolchain for WASM that supports *unmodified* applications compiled to WASM
and utilizes diverse Arm hardware features aiming to enrich the memory safety properties of WASM.
Precisely, Cage leverages Arm's Memory Tagging Extension (MTE) to *(i)* provide spatial and temporal memory safety for heap and stack allocations and *(ii)* improve the performance of WASM's sandboxing mechanism.
Cage further employs Arm's Pointer Authentication (PAC) to prevent leaked pointers from being reused by other WASM instances, thus enhancing WASM's security properties.

We implement our system based on 64-bit WASM.
We provide a WASM compiler and runtime with support for Arm's MTE and PAC.
On top of that, Cage's LLVM-based compiler toolchain transforms unmodified applications to provide spatial and temporal memory safety for stack and heap allocations and prevent function pointer reuse.
Our evaluation on real hardware shows that Cage incurs minimal runtime (<5.8%) and memory (<5.3) overheads and can improve the performance of WASM's sandboxing mechanism, achieving a speedup of over 5.1%, while offering efficient memory safety guarantees.

## Citation

If you reference this project, please use the following citation information:

```bib
@inproceedings{Fink2025Cage,
  author = {Fink, Martin and Stavrakakis, Dimitrios and Sprokholt, Dennis and Chakraborty, Soham and Ekberg, Jan-Erik and Bhatotia, Pramod},
  title = {Cage: Hardware-Accelerated Safe WebAssembly},
  year = {2025},
  isbn = {9798400712753},
  publisher = {Association for Computing Machinery},
  address = {New York, NY, USA},
  url = {https://doi.org/10.1145/3696443.3708920},
  doi = {10.1145/3696443.3708920},
  abstract = {WebAssembly (WASM) is an immensely versatile and increasingly popular compilation target. It executes applications written in several languages (e.g., C/C++) with near-native performance in various domains (e.g., mobile, edge, cloud). Despite WASM's sandboxing feature, which isolates applications from other instances and the host platform, WASM does not inherently provide any memory safety guarantees for applications written in low-level, unsafe languages.
  To this end, we propose Cage, a hardware-accelerated toolchain for WASM that supports unmodified applications compiled to WASM and utilizes diverse Arm hardware features aiming to enrich the memory safety properties of WASM. Precisely, Cage leverages Arm's Memory Tagging Extension (MTE) to (i) provide spatial and temporal memory safety for heap and stack allocations and (ii) improve the performance of WASM's sandboxing mechanism. Cage further employs Arm's Pointer Authentication (PAC) to prevent leaked pointers from being reused by other WASM instances, thus enhancing WASM's security properties.
  We implement our system based on 64-bit WASM. We provide a WASM compiler and runtime with support for Arm's MTE and PAC. On top of that, Cage's LLVM-based compiler toolchain transforms unmodified applications to provide spatial and temporal memory safety for stack and heap allocations and prevent function pointer reuse. Our evaluation on real hardware shows that Cage incurs minimal runtime (<5.8\%) and memory (<3.7\%) overheads and can improve the performance of WASM's sandboxing mechanism, achieving a speedup of over 5.1\%, while offering efficient memory safety guarantees.},
  booktitle = {Proceedings of the 23rd ACM/IEEE International Symposium on Code Generation and Optimization},
  pages = {538--552},
  numpages = {15},
  keywords = {Memory Safety, WebAssembly},
  location = {Las Vegas, NV, USA},
  series = {CGO '25}
}
```

