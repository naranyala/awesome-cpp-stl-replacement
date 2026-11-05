# Awesome C++ STL Replacements & Related Libraries

A curated catalog of C++ libraries that replace, extend, or complement containers, algorithms, strings, and utilities in the C++ Standard Library (often called the STL).

> **Note:** “STL replacement” can mean anything from a drop-in container to a complete standard-library implementation. Most projects here are selective alternatives, not universal substitutes. Check compatibility, supported C++ versions, licenses, and benchmarks for your use case.

## Contents

- [Complete standard-library implementations](#complete-standard-library-implementations)
- [Container and data-structure alternatives](#container-and-data-structure-alternatives)
- [Ranges, iterators, and algorithms](#ranges-iterators-and-algorithms)
- [Strings, formatting, and text](#strings-formatting-and-text)
- [Type utilities and safer interfaces](#type-utilities-and-safer-interfaces)
- [Numeric and data-oriented libraries](#numeric-and-data-oriented-libraries)
- [Memory and allocation](#memory-and-allocation)
- [Testing and benchmarking](#testing-and-benchmarking)
- [Related C++ libraries](#related-c-libraries)
- [Contributing](#contributing)

## Complete standard-library implementations

These implement the C++ standard library itself. They are usually selected through the compiler and toolchain rather than used as ordinary library dependencies.

- [LLVM libc++](https://libcxx.llvm.org/) — LLVM’s implementation of the C++ standard library.
- [GNU libstdc++](https://gcc.gnu.org/onlinedocs/libstdc++/) — The standard-library implementation commonly used with GCC.
- [Microsoft STL](https://github.com/microsoft/STL) — Microsoft’s open-source implementation of the C++ standard library for MSVC and other supported toolchains.

## Container and data-structure alternatives

### Broad container libraries

- [EASTL](https://github.com/electronicarts/EASTL) — Containers and algorithms designed for performance-sensitive applications, especially games and memory-constrained environments.
- [Boost.Container](https://www.boost.org/doc/libs/release/libs/container/) — Standard-like containers, including flat, node-based, and allocator-aware options.
- [Abseil Containers](https://abseil.io/docs/cpp/guides/container) — Google’s hash and ordered containers, including `flat_hash_map` and `flat_hash_set`.
- [Folly](https://github.com/facebook/folly) — Facebook’s collection of C++ infrastructure libraries, with high-performance containers such as F14 hash tables.
- [Qt Containers](https://doc.qt.io/qt-6/containers.html) — Containers integrated with the Qt framework; APIs and behavior differ from the standard library.
- [The Embedded Template Library (ETL)](https://github.com/ETLCPP/etl) — Containers and utilities designed for embedded systems, with static-capacity options and no required dynamic allocation for many components.

### Hash maps and sets

- [ankerl::unordered_dense](https://github.com/martinus/unordered_dense) — Densely stored hash maps and sets.
- [Tessil’s containers](https://github.com/Tessil) — A family of hash maps and sets, including [robin-map](https://github.com/Tessil/robin-map), [sparse-map](https://github.com/Tessil/sparse-map), and [ordered-map](https://github.com/Tessil/ordered-map).
- [F14](https://github.com/facebook/folly/tree/main/folly/container) — Folly’s hash-table family, with variants for different storage and performance trade-offs.
- [Boost.Unordered](https://www.boost.org/doc/libs/release/libs/unordered/) — Boost’s unordered associative containers, including open-addressing containers.
- [parallel-hashmap](https://github.com/greg7mdp/parallel-hashmap) — A family of fast, memory-friendly hash maps and sets based on Google’s SwissTable design, including parallel variants.

### Specialized containers

- [Boost.Container](https://www.boost.org/doc/libs/release/libs/container/) — Includes alternatives such as `flat_map`, `flat_set`, `static_vector`, and `small_vector`.
- [LLVM ADT](https://llvm.org/docs/ProgrammersManual.html#llvm-adt) — LLVM support types and data structures, including `SmallVector`, `DenseMap`, and `StringRef`; primarily intended for LLVM-related code.
- [Abseil B-tree containers](https://abseil.io/docs/cpp/guides/container) — B-tree ordered maps and sets that offer a different storage and locality trade-off from node-based `std::map` and `std::set`.
- [plf::colony](https://github.com/mattreecebentley/plf_colony) — An unordered container designed for fast insertion and erasure while preserving pointers and iterators to non-erased elements.
- [Boost.Intrusive](https://www.boost.org/doc/libs/release/doc/html/intrusive.html) — Intrusive containers, where hooks are embedded in user objects to avoid separate node allocations.

## Ranges, iterators, and algorithms

- [range-v3](https://github.com/ericniebler/range-v3) — Ranges library and algorithms that influenced the C++20 ranges design.
- [Boost.Range](https://www.boost.org/doc/libs/release/libs/range/) — Range concepts and algorithms that work with many iterator-based types.
- [Boost.Iterator](https://www.boost.org/doc/libs/release/libs/iterator/) — Iterator adaptors and utilities for building custom iterators.
- [Boost.Algorithm](https://www.boost.org/doc/libs/release/libs/algorithm/) — Additional generic algorithms that complement `<algorithm>`.
- [oneDPL](https://github.com/uxlfoundation/oneDPL) — Parallel algorithms and data-parallel facilities for CPU and accelerator environments.
- [Thrust](https://github.com/NVIDIA/thrust) — Parallel algorithms and containers modeled on the C++ standard library, supporting NVIDIA GPUs and other backends.
- [HPX](https://github.com/STEllAR-GROUP/hpx) — A parallelism and concurrency framework that includes parallel algorithm implementations and execution facilities.

## Strings, formatting, and text

- [fmt](https://github.com/fmtlib/fmt) — A fast, type-safe formatting library; its API inspired `std::format`.
- [Abseil Strings](https://abseil.io/docs/cpp/guides/strings) — String utilities, formatting, escaping, and text-processing helpers.
- [Boost String Algorithms](https://www.boost.org/doc/libs/release/libs/algorithm/) — String algorithms and utilities that complement standard string operations.
- [ICU](https://github.com/unicode-org/icu) — Unicode, internationalization, and globalization libraries for C/C++.
- [simdutf](https://github.com/simdutf/simdutf) — SIMD-accelerated Unicode validation and transcoding.
- [utf8cpp](https://github.com/nemtrif/utfcpp) — A portable, header-only library for working with UTF-8 encoded text.
- [Boost.StringView](https://www.boost.org/doc/libs/release/libs/utility/doc/html/string_view.html) — A non-owning string view for projects that need a string-view type across older language-standard versions.

## Type utilities and safer interfaces

- [Microsoft GSL](https://github.com/microsoft/GSL) — Guidelines Support Library types and utilities, including `span` and contract-related helpers.
- [tl::expected](https://github.com/TartanLlama/expected) — A standalone `expected` implementation for error handling when `std::expected` is unavailable or unsuitable.
- [Boost.Outcome](https://www.boost.org/libs/outcome/) — Result and error-handling types for representing success or failure.
- [Boost.Utility](https://www.boost.org/doc/libs/release/libs/utility/) — General-purpose utilities that complement standard-library facilities.
- [span-lite](https://github.com/martinmoene/span-lite) — A `span` implementation for projects that need compatibility with older C++ standards.
- [optional-lite](https://github.com/martinmoene/optional-lite) — An `optional` implementation for projects that need compatibility with older C++ standards.
- [variant-lite](https://github.com/martinmoene/variant-lite) — A `variant` implementation for projects that need compatibility with older C++ standards.
- [magic_enum](https://github.com/Neargye/magic_enum) — Header-only utilities for reflecting enum names and values at compile time, within documented compiler limitations.
- [nameof](https://github.com/Neargye/nameof) — Header-only utilities for obtaining names of C++ entities at compile time, within documented compiler limitations.

## Numeric and data-oriented libraries

These do not replace the standard library generally, but provide specialized facilities often needed alongside its containers and algorithms.

- [Eigen](https://gitlab.com/libeigen/eigen) — Template library for linear algebra, matrices, vectors, and related numerical operations.
- [xtensor](https://github.com/xtensor-stack/xtensor) — Multi-dimensional arrays and numerical expressions with an API inspired by NumPy.
- [Blaze](https://bitbucket.org/blaze-lib/blaze/src/master/) — High-performance dense and sparse arithmetic for vectors and matrices.
- [Boost.Multiprecision](https://www.boost.org/doc/libs/release/libs/multiprecision/) — Arbitrary-precision integer, rational, and floating-point types.
- [Boost.NumericConversion](https://www.boost.org/doc/libs/release/libs/numeric/conversion/) — Safer and more explicit numeric conversions.

## Memory and allocation

- [mimalloc](https://github.com/microsoft/mimalloc) — A general-purpose allocator designed for performance and efficient memory use.
- [jemalloc](https://github.com/jemalloc/jemalloc) — A general-purpose allocator with tuning and profiling options.
- [rpmalloc](https://github.com/mjansson/rpmalloc) — A thread-caching allocator for allocation-heavy workloads.
- [snmalloc](https://github.com/microsoft/snmalloc) — A scalable allocator designed for concurrent workloads.
- [Google TCMalloc](https://github.com/google/tcmalloc) — A thread-caching allocator and heap profiler.
- [Boost.Pool](https://www.boost.org/doc/libs/release/libs/pool/) — Pool-based allocation facilities for workloads with repeated allocations of similar sizes.
- [Boost.Container memory resources](https://www.boost.org/doc/libs/release/libs/container/) — Polymorphic allocators and memory resources for allocator-aware containers.

## Testing and benchmarking

- [Google Benchmark](https://github.com/google/benchmark) — A framework for writing and running C++ microbenchmarks.
- [Celero](https://github.com/DigitalInBlue/Celero) — A C++ benchmarking framework for comparing performance.
- [nanobench](https://github.com/martinus/nanobench) — A small, dependency-free microbenchmarking library for C++.

## Related C++ libraries

Useful parts of the wider C++ ecosystem that are often adopted alongside standard-library alternatives.

- [Boost](https://www.boost.org/) — A broad collection of portable C++ libraries; many are complementary extensions rather than replacements for the standard library.
- [Abseil](https://abseil.io/) — Google’s collection of C++ libraries designed to work well together and complement the standard library.
- [Folly](https://github.com/facebook/folly) — Production-oriented C++ components from Meta, including containers, utilities, and concurrency tools.
- [BDE](https://github.com/bloomberg/bde) — Bloomberg’s development environment and libraries, including components for containers, utilities, and foundational types.

## Contributing

Contributions are welcome! Please open a pull request to add a useful project or improve an entry. For additions, include:

- The project name and canonical link.
- A concise, factual description of what it replaces or complements.
- A clear category and any important scope or compatibility caveats.

Please keep the list focused on useful C++ libraries, distinguish true replacements from complementary tools, and avoid promotional claims or unsupported performance rankings. Check that project links are current before submitting.
