# Awesome C++ STL Replacements & Related Libraries

A curated catalog of C++ libraries that replace, extend, or complement the containers, algorithms, strings, and utilities in the C++ Standard Library (often called the STL).

> **Note:** “STL replacement” can mean anything from a drop-in container to a complete standard-library implementation. Most projects here are selective alternatives, not universal substitutes. Check compatibility, supported C++ versions, licensing, and benchmarks for your use case before adopting one.

## Contents

- [Complete standard-library implementations](#complete-standard-library-implementations)
- [Container and data-structure alternatives](#container-and-data-structure-alternatives)
- [Ranges and algorithms](#ranges-and-algorithms)
- [Strings, formatting, and text](#strings-formatting-and-text)
- [Type utilities and safer interfaces](#type-utilities-and-safer-interfaces)
- [Memory and allocation](#memory-and-allocation)
- [Testing and benchmarking](#testing-and-benchmarking)
- [Contributing](#contributing)

## Complete standard-library implementations

These implement the C++ standard library itself. They are usually selected through the compiler and toolchain rather than used as an ordinary library dependency.

- [LLVM libc++](https://libcxx.llvm.org/) — LLVM’s implementation of the C++ standard library.
- [GNU libstdc++](https://gcc.gnu.org/onlinedocs/libstdc++/) — The standard-library implementation commonly used with GCC.
- [Microsoft STL](https://github.com/microsoft/STL) — Microsoft’s open-source implementation of the C++ standard library for MSVC and other supported toolchains.

## Container and data-structure alternatives

### Broad container libraries

- [EASTL](https://github.com/electronicarts/EASTL) — Containers and algorithms designed for performance-sensitive applications, especially games and other memory-constrained environments.
- [Boost.Container](https://www.boost.org/doc/libs/release/libs/container/) — Standard-like containers, including flat, node-based, and allocator-aware options.
- [Abseil Containers](https://abseil.io/docs/cpp/guides/container) — Google’s hash and ordered containers, including `flat_hash_map` and `flat_hash_set`.
- [Folly](https://github.com/facebook/folly) — Facebook’s collection of C++ infrastructure libraries, with high-performance containers such as F14 hash tables.
- [Qt Containers](https://doc.qt.io/qt-6/containers.html) — Containers integrated with the Qt framework; useful in Qt applications, with APIs and behavior that differ from the standard library.

### Hash maps and sets

- [ankerl::unordered_dense](https://github.com/martinus/unordered_dense) — Fast, densely stored hash maps and sets.
- [Tessil’s containers](https://github.com/Tessil) — A family of C++ hash maps and sets, including robin-map, sparse-map, and ordered-map.
- [F14](https://github.com/facebook/folly/tree/main/folly/container) — Folly’s SIMD-friendly hash-table family, with variants for different storage and performance trade-offs.
- [Boost.Unordered](https://www.boost.org/doc/libs/release/libs/unordered/) — Boost’s unordered associative containers, including newer open-addressing containers.

### Specialized containers

- [Boost.Container](https://www.boost.org/doc/libs/release/libs/container/) — Includes alternatives such as `flat_map`, `flat_set`, `static_vector`, and `small_vector`.
- [LLVM ADT](https://llvm.org/doxygen/dir_2f34f3ce2d2bff49d1b3ec74d60b84f5.html) — LLVM’s support types and data structures, including `SmallVector`, `DenseMap`, and `StringRef`; primarily intended for LLVM-related code.
- [C++ B-tree](https://github.com/abseil-cpp/btree) — Abseil’s B-tree ordered containers, available as a standalone project.

## Ranges and algorithms

- [range-v3](https://github.com/ericniebler/range-v3) — A ranges library and algorithms; it influenced the C++20 ranges design and remains useful for features beyond a particular standard-library implementation.
- [Boost.Range](https://www.boost.org/doc/libs/release/libs/range/) — Range concepts and algorithms that work with many iterator-based types.
- [Parallel STL (PSTL)](https://github.com/uxlfoundation/oneDPL) — oneDPL provides parallel algorithms and data-parallel facilities for CPU and accelerator environments.

## Strings, formatting, and text

- [fmt](https://github.com/fmtlib/fmt) — A fast, type-safe formatting library; its API inspired `std::format`.
- [Abseil Strings](https://abseil.io/docs/cpp/guides/strings) — String utilities, formatting, escaping, and text-processing helpers.
- [Boost.String](https://www.boost.org/doc/libs/release/libs/algorithm/) — String algorithms and utilities from Boost’s string-related libraries.
- [ICU](https://github.com/unicode-org/icu) — Unicode, internationalization, and globalization libraries for C/C++.

## Type utilities and safer interfaces

- [Microsoft GSL](https://github.com/microsoft/GSL) — Guidelines Support Library types and utilities, including `span` and contracts-related helpers.
- [tl::expected](https://github.com/TartanLlama/expected) — A standalone `expected` implementation for error handling, useful when `std::expected` is unavailable or unsuitable.
- [Boost.Outcome](https://www.boost.org/libs/outcome/) — Result and error-handling types for representing success or failure.
- [Boost.Utility](https://www.boost.org/doc/libs/release/libs/utility/) — General-purpose utilities that complement standard-library facilities.

## Memory and allocation

- [mimalloc](https://github.com/microsoft/mimalloc) — A general-purpose allocator designed for performance and efficient memory use.
- [jemalloc](https://github.com/jemalloc/jemalloc) — A general-purpose malloc implementation with extensive tuning and profiling options.
- [rpmalloc](https://github.com/mjansson/rpmalloc) — A thread-caching allocator for applications with allocation-heavy workloads.
- [snmalloc](https://github.com/microsoft/snmalloc) — A scalable allocator designed for concurrent workloads.
- [Google TCMalloc](https://github.com/google/tcmalloc) — A thread-caching malloc implementation and heap profiler.
- [Boost.Pool](https://www.boost.org/doc/libs/release/libs/pool/) — Pool-based memory-allocation facilities for workloads with repeated allocations of similar sizes.

## Testing and benchmarking

- [Google Benchmark](https://github.com/google/benchmark) — A framework for writing and running C++ microbenchmarks.
- [Celero](https://github.com/DigitalInBlue/Celero) — A C++ benchmarking framework for comparing performance.

## Contributing

Contributions are welcome! Please open a pull request to add a useful project or improve an entry. For additions, include:

- The project name and canonical link.
- A concise, factual description of what it replaces or complements.
- A clear category and any important scope or compatibility caveats.

Please keep the list focused on actively useful C++ libraries and avoid promotional claims or unsupported performance rankings.
