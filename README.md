# Awesome C++ STL Replacements & Related Libraries

A curated catalog of C++ libraries that replace, extend, or complement containers, algorithms, strings, and utilities in the C++ Standard Library (often called the STL).

> **Note:** “STL replacement” can mean anything from a drop-in container to a complete standard-library implementation. Most projects here are selective alternatives, not universal substitutes. Check compatibility, supported C++ versions, licenses, and benchmarks for your use case.

## Contents

- [Complete standard-library implementations](#complete-standard-library-implementations)
- [Container and data-structure alternatives](#container-and-data-structure-alternatives)
- [Ranges, iterators, and algorithms](#ranges-iterators-and-algorithms)
- [Strings, formatting, and text](#strings-formatting-and-text)
- [Type utilities and safer interfaces](#type-utilities-and-safer-interfaces)
- [Small, focused libraries](#small-focused-libraries)
- [Performance-focused libraries](#performance-focused-libraries)
- [Numeric and data-oriented libraries](#numeric-and-data-oriented-libraries)
- [Memory and allocation](#memory-and-allocation)
- [Testing and benchmarking](#testing-and-benchmarking)
- [Complementary C++ libraries and tools](#complementary-c-libraries-and-tools)
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
- [Folly](https://github.com/facebook/folly) — Meta’s collection of C++ infrastructure libraries, with high-performance containers such as F14 hash tables.
- [Qt Containers](https://doc.qt.io/qt-6/containers.html) — Containers integrated with the Qt framework; APIs and behavior differ from the standard library.
- [The Embedded Template Library (ETL)](https://github.com/ETLCPP/etl) — Containers and utilities designed for embedded systems, with static-capacity options and no required dynamic allocation for many components.

### Hash maps and sets

- [ankerl::unordered_dense](https://github.com/martinus/unordered_dense) — Densely stored hash maps and sets.
- [Tessil's robin-map](https://github.com/Tessil/robin-map) — Robin Hood hash map and set; the same author also maintains [sparse-map](https://github.com/Tessil/sparse-map) and [ordered-map](https://github.com/Tessil/ordered-map).
- [F14](https://github.com/facebook/folly/tree/main/folly/container) — Folly’s hash-table family, with variants for different storage and performance trade-offs.
- [Boost.Unordered](https://www.boost.org/doc/libs/release/libs/unordered/) — Boost’s unordered associative containers, including open-addressing containers.
- [parallel-hashmap](https://github.com/greg7mdp/parallel-hashmap) — A family of hash maps and sets based on Google's SwissTable design, including parallel variants.
- [emhash](https://github.com/ktprime/emhash) — Fast and memory-efficient flat hash tables (map, set, multimap) intended as replacement candidates for `std::unordered_map`.
- [libcuckoo](https://github.com/efficient/libcuckoo) — A high-performance concurrent cuckoo hash table for multi-threaded workloads.

### Specialized containers

- [Boost.Container](https://www.boost.org/doc/libs/release/libs/container/) — Includes alternatives such as `flat_map`, `flat_set`, `static_vector`, and `small_vector`.
- [LLVM ADT](https://llvm.org/docs/ProgrammersManual.html#llvm-adt) — LLVM support types and data structures, including `SmallVector`, `DenseMap`, and `StringRef`; primarily intended for LLVM-related code.
- [Abseil B-tree containers](https://abseil.io/docs/cpp/guides/container) — B-tree ordered maps and sets that offer different storage and locality trade-offs from node-based `std::map` and `std::set`.
- [plf::colony](https://github.com/mattreecebentley/plf_colony) — An unordered container designed for fast insertion and erasure while preserving pointers and iterators to non-erased elements.
- [Boost.Intrusive](https://www.boost.org/doc/libs/release/doc/html/intrusive.html) — Intrusive containers, where hooks are embedded in user objects to avoid separate node allocations.
- [Boost.MultiIndex](https://www.boost.org/doc/libs/release/libs/multi_index/) — Containers that maintain several different index types (ordered, hashed, sequenced) over the same elements.
- [immer](https://github.com/arximboldi/immer) — Immutable and persistent data structures with structural sharing and cheap value semantics.
- [Boost.CircularBuffer](https://www.boost.org/doc/libs/release/libs/circular_buffer/) — A fixed-capacity circular buffer with STL-compatible interfaces for streaming and rolling-window data.
- [dynamic_bitset](https://github.com/pinam45/dynamic_bitset) — A header-only `std::bitset`-like container with a runtime-configurable size, inspired by Boost's `dynamic_bitset`.

## Ranges, iterators, and algorithms

- [range-v3](https://github.com/ericniebler/range-v3) — Ranges library and algorithms that influenced the C++20 ranges design.
- [Boost.Range](https://www.boost.org/doc/libs/release/libs/range/) — Range concepts and algorithms that work with many iterator-based types.
- [Boost.Iterator](https://www.boost.org/doc/libs/release/libs/iterator/) — Iterator adaptors and utilities for building custom iterators.
- [Boost.Algorithm](https://www.boost.org/doc/libs/release/libs/algorithm/) — Additional generic algorithms that complement `<algorithm>`.
- [oneDPL](https://github.com/uxlfoundation/oneDPL) — Parallel algorithms and data-parallel facilities for CPU and accelerator environments.
- [Thrust](https://github.com/NVIDIA/thrust) — Parallel algorithms and containers modeled on the C++ standard library, supporting NVIDIA GPUs and other backends.
- [HPX](https://github.com/STEllAR-GROUP/hpx) — A parallelism and concurrency framework that includes parallel algorithm implementations and execution facilities.
- [Flux](https://github.com/tcbrindle/flux) — A C++20 library for sequence-oriented programming; a ranges-style approach built around a simpler iteration model.
- [cppitertools](https://github.com/ryanhaining/cppitertools) — Python-itertools-style iterator adapters (`zip`, `enumerate`, `chunk`, `compress`, and more) for C++17.

## Strings, formatting, and text

- [fmt](https://github.com/fmtlib/fmt) — A fast, type-safe formatting library; its API inspired `std::format`.
- [Abseil Strings](https://abseil.io/docs/cpp/guides/strings) — String utilities, formatting, escaping, and text-processing helpers.
- [Boost String Algorithms](https://www.boost.org/doc/libs/release/libs/algorithm/) — String algorithms and utilities that complement standard string operations.
- [ICU](https://github.com/unicode-org/icu) — Unicode, internationalization, and globalization libraries for C/C++.
- [simdutf](https://github.com/simdutf/simdutf) — SIMD-accelerated Unicode validation and transcoding.
- [utf8cpp](https://github.com/nemtrif/utfcpp) — A portable, header-only library for working with UTF-8 encoded text.
- [Boost.StringView](https://www.boost.org/doc/libs/release/libs/utility/doc/html/utility/utilities/string_view.html) — A non-owning string view for projects that need a string-view type across older language-standard versions.
- [fast_float](https://github.com/fastfloat/fast_float) — Fast, exact number parsing using the `from_chars` design for C++17 and libraries supporting older standards.
- [uni-algo](https://github.com/uni-algo/uni-algo) — Unicode algorithms: normalization, case conversion, segmentation, and related text-processing operations.
- [CTRE (compile-time regular expressions)](https://github.com/hanickadot/compile-time-regular-expressions) — A regular-expression engine evaluated at compile time, usable in constexpr contexts; a lighter alternative to runtime `<regex>`.
- [RE2](https://github.com/google/re2) — Google's regular-expression engine designed for guaranteed linear-time matching; a safe alternative to backtracking engines.

## Type utilities and safer interfaces

### Standard vocabulary types and backports

Implementations of types that are now standard (or close to it), useful when working with older toolchains.

- [tl::expected](https://github.com/TartanLlama/expected) — A standalone `expected` implementation for error handling when `std::expected` is unavailable or unsuitable.
- [expected-lite](https://github.com/martinmoene/expected-lite) — Lightweight `expected` implementation for error handling, including support for older C++ standards.
- [Boost.Outcome](https://www.boost.org/doc/libs/release/libs/outcome/) — Result and error-handling types for representing success or failure.
- [span-lite](https://github.com/nonstd-lite/span-lite) — A `span` implementation for projects that need compatibility with older C++ standards.
- [optional-lite](https://github.com/martinmoene/optional-lite) — An `optional` implementation for projects that need compatibility with older C++ standards.
- [variant-lite](https://github.com/nonstd-lite/variant-lite) — A `variant` implementation for projects that need compatibility with older C++ standards.
- [string-view-lite](https://github.com/nonstd-lite/string-view-lite) — A `string_view` implementation for projects targeting older C++ standards.

### Other type utilities

- [Microsoft GSL](https://github.com/microsoft/GSL) — Guidelines Support Library types and utilities, including `span` and contract-related helpers.
- [gsl-lite](https://github.com/gsl-lite/gsl-lite) — A Core Guidelines support library implementation backported to older C++ standards; an alternative to Microsoft GSL for pre-C++14 compilers.
- [Boost.Utility](https://www.boost.org/doc/libs/release/libs/utility/) — General-purpose utilities that complement standard-library facilities.
- [type_safe](https://github.com/foonathan/type_safe) — Zero-overhead wrappers (`boolean`, `floating_point`, tagged types, and more) that prevent invalid conversions and misuse at compile time.
- [magic_enum](https://github.com/Neargye/magic_enum) — Header-only utilities for reflecting enum names and values at compile time, within documented compiler limitations.
- [nameof](https://github.com/Neargye/nameof) — Header-only utilities for obtaining names of C++ entities at compile time, within documented compiler limitations.
- [Boost.PFR](https://www.boost.org/doc/libs/release/libs/pfr/) — Reflection for aggregate types without macros or code generation, using compiler-generated structured bindings.
- [stduuid](https://github.com/mariusbancila/stduuid) — A C++17 cross-platform UUID library; a candidate facility for a future standard UUID type.

## Small, focused libraries

Small, single-purpose libraries can be useful when you only need one missing facility instead of adopting a larger framework. “Small” can refer to scope, dependencies, or integration style; check each project’s requirements and maintenance status.

- [scope-lite](https://github.com/martinmoene/scope-lite) — Scope guards and scope-based resource cleanup utilities.
- [function2](https://github.com/Naios/Function2) — A configurable polymorphic function wrapper intended as an alternative to `std::function` and related callable wrappers.
- [frozen](https://github.com/serge-sans-paille/frozen) — Header-only compile-time maps, sets, and other immutable containers.
- [nanorange](https://github.com/tcbrindle/NanoRange) — A compact ranges library for projects that need ranges support on older C++ standards.
- [bitsery](https://github.com/fraillt/bitsery) — A compact, header-only C++ serialization library with configurable serialization formats.
- [ghc::filesystem](https://github.com/gulrak/filesystem) — An implementation of C++17 `std::filesystem` for projects targeting C++11/C++14 toolchains.

## Performance-focused libraries

These projects target specific performance needs such as SIMD, concurrent data structures, or task scheduling. They are not blanket replacements for the standard library: measure with representative workloads, and consider portability, memory use, and API trade-offs.

### SIMD and data-parallel computing

- [Google Highway](https://github.com/google/highway) — Portable SIMD; write vectorized code that can target multiple CPU architectures.
- [xsimd](https://github.com/xtensor-stack/xsimd) — C++ wrappers for SIMD intrinsics across supported architectures.
- [libsimdpp](https://github.com/p12tic/libsimdpp) — Header-only SIMD abstraction for writing portable vectorized code.
- [NVIDIA CCCL](https://github.com/NVIDIA/cccl) — The CUDA C++ Core Libraries: Thrust, CUB, and libcu++ for GPU data-parallel programming.

### Coroutines and asynchronous task models

- [cppcoro](https://github.com/andreasbuhr/cppcoro) — Coroutine support library offering tasks, generators, asynchronous generators, and coroutine-based I/O abstractions; maintained continuation of Lewis Baker's original.
- [stdexec](https://github.com/NVIDIA/stdexec) — Reference implementation of `std::execution` (senders and receivers), the standard C++ framework for asynchronous and parallel programming.

### Concurrent queues and task scheduling

- [moodycamel::ConcurrentQueue](https://github.com/cameron314/concurrentqueue) — A concurrent queue for producer/consumer workloads; review its documented ordering and memory-model guarantees when choosing it.
- [oneTBB](https://github.com/oneapi-src/oneTBB) — Threading Building Blocks with task scheduling, parallel algorithms, and concurrent containers.
- [Taskflow](https://github.com/taskflow/taskflow) — A task-based parallel programming framework for building and executing task graphs.
- [BS::thread_pool](https://github.com/bshoshany/thread-pool) — A lightweight C++ thread-pool library for submitting tasks to worker threads.
- [MPMCQueue](https://github.com/rigtorp/MPMCQueue) — A bounded, lock-free multi-producer multi-consumer queue written in C++11.
- [atomic_queue](https://github.com/max0x7ba/atomic_queue) — Lock-free, low-latency queues for high-throughput inter-thread message passing.

### Profiling and tracing

- [Tracy](https://github.com/wolfpld/tracy) — A real-time profiler for CPU, GPU, memory allocation, and application tracing.
- [Perfetto](https://github.com/google/perfetto) — A suite for collecting and viewing system-wide and application-level traces.
- [easy_profiler](https://github.com/yse/easy_profiler) — A lightweight profiler library for instrumented code blocks, with a GUI viewer for captured traces.
- [gperftools](https://github.com/gperftools/gperftools) — CPU and heap profiling tools, including the TCMalloc allocator listed above.
- [heaptrack](https://github.com/KDE/heaptrack) — A heap-memory profiler for Linux that tracks allocations and reports peak usage with allocation call stacks.

## Numeric and data-oriented libraries

These do not replace the standard library generally, but provide specialized facilities often needed alongside its containers and algorithms.

- [Eigen](https://gitlab.com/libeigen/eigen) — Template library for linear algebra, matrices, vectors, and related numerical operations.
- [xtensor](https://github.com/xtensor-stack/xtensor) — Multi-dimensional arrays and numerical expressions with an API inspired by NumPy.
- [Blaze](https://bitbucket.org/blaze-lib/blaze/src/master/) — Dense and sparse arithmetic for vectors and matrices.
- [Boost.Multiprecision](https://www.boost.org/doc/libs/release/libs/multiprecision/) — Arbitrary-precision integer, rational, and floating-point types.
- [Boost.NumericConversion](https://www.boost.org/doc/libs/release/libs/numeric/conversion/) — Safer and more explicit numeric conversions.
- [NumCpp](https://github.com/dpilger26/NumCpp) — A NumPy-style C++ library for N-dimensional arrays and numerical functions.
- [mp-units](https://github.com/mpusz/mp-units) — A quantities-and-units library providing compile-time dimensional correctness for physical computations.

## Memory and allocation

- [mimalloc](https://github.com/microsoft/mimalloc) — A general-purpose allocator designed for performance and efficient memory use.
- [jemalloc](https://github.com/jemalloc/jemalloc) — A general-purpose allocator with tuning and profiling options.
- [rpmalloc](https://github.com/mjansson/rpmalloc) — A thread-caching allocator for allocation-heavy workloads.
- [snmalloc](https://github.com/microsoft/snmalloc) — A scalable allocator designed for concurrent workloads.
- [Google TCMalloc](https://github.com/google/tcmalloc) — A thread-caching allocator and heap profiler.
- [Boost.Pool](https://www.boost.org/doc/libs/release/libs/pool/) — Pool-based allocation facilities for workloads with repeated allocations of similar sizes.
- [Boost.Container memory resources](https://www.boost.org/doc/libs/release/libs/container/) — Polymorphic allocators and memory resources for allocator-aware containers.
- [foonathan/memory](https://github.com/foonathan/memory) — Allocator and memory-resource building blocks (pool, stack, arena) that work with STL containers and `pmr` interfaces.

## Testing and benchmarking

- [Google Benchmark](https://github.com/google/benchmark) — A framework for writing and running C++ microbenchmarks.
- [Celero](https://github.com/DigitalInBlue/Celero) — A C++ benchmarking framework for comparing performance.
- [nanobench](https://github.com/martinus/nanobench) — A small, dependency-free microbenchmarking library for C++.
- [GoogleTest](https://github.com/google/googletest) — Google's C++ testing and mocking framework (gTest and gMock).
- [Catch2](https://github.com/catchorg/Catch2) — C++ testing framework with a test runner and assertion library.
- [doctest](https://github.com/doctest/doctest) — Lightweight, fast, single-header testing framework.
- [Boost.Test](https://www.boost.org/doc/libs/release/libs/test/) — Unit-testing framework for C++ projects using Boost or other libraries.
- [trompeloeil](https://github.com/rollbear/trompeloeil) — A header-only mocking framework that pairs with Catch2, doctest, GoogleTest, and other test frameworks.

## Complementary C++ libraries and tools

These are not primarily STL replacements. They provide common capabilities that work alongside the containers, algorithms, and utilities listed above.

### More components from ecosystems already listed

- [Boost.Asio](https://www.boost.org/doc/libs/release/doc/html/boost_asio.html) — Asynchronous I/O and networking; complements Boost.Container and Boost.Utility in networked applications.
- [Boost.Serialization](https://www.boost.org/doc/libs/release/libs/serialization/) — Object serialization for archiving and data exchange.
- [Boost.Log](https://www.boost.org/doc/libs/release/libs/log/) — Logging framework with filtering, sinks, and formatting.
- [Abseil Status and StatusOr](https://abseil.io/docs/cpp/guides/status) — Error/status reporting types that complement Abseil Containers and other components.
- [Abseil Flags](https://abseil.io/docs/cpp/guides/flags) — Command-line flag handling for applications using Abseil.
- [Abseil Time](https://abseil.io/docs/cpp/guides/time) — Time, duration, and timezone facilities that complement standard chrono utilities.
- [oneTBB](https://github.com/oneapi-src/oneTBB) — Its task scheduler and concurrent containers complement the parallel-algorithm libraries listed above.

### Logging

- [spdlog](https://github.com/gabime/spdlog) — Logging library with formatting support; can use `fmt` or `std::format` depending on configuration.
- [Quill](https://github.com/odygrd/quill) — Asynchronous logging library for C++ applications.

### Serialization and data formats

- [cereal](https://github.com/USCiLab/cereal) — Header-only serialization library for C++ data structures.
- [Protocol Buffers](https://github.com/protocolbuffers/protobuf) — Schema-based serialization and code generation for interoperable data formats.
- [FlatBuffers](https://github.com/google/flatbuffers) — Schema-based serialization designed for direct access to serialized data.
- [nlohmann/json](https://github.com/nlohmann/json) — "JSON for Modern C++": an intuitive, STL-like API for JSON parsing and serialization.
- [Boost.JSON](https://www.boost.org/doc/libs/release/libs/json/) — JSON parsing, serialization, and a JSON value type integrated with Boost allocators and containers.
- [simdjson](https://github.com/simdjson/simdjson) — Extremely fast SIMD-based JSON parsing at gigabytes per second.
- [RapidJSON](https://github.com/Tencent/rapidjson) — A fast JSON parser and generator with SAX and DOM interfaces.
- [Glaze](https://github.com/stephenberry/glaze) — High-performance serialization and reflection for JSON and binary formats using compile-time metadata.
- [jsoncons](https://github.com/danielaparker/jsoncons) — JSON and JSON-like formats (CBOR, MessagePack, BSON, and more) with JSON Pointer, JSON Patch, and JSON Schema support.
- [toml++](https://github.com/marzer/tomlplusplus) — Header-only TOML parser and serializer for C++.
- [yaml-cpp](https://github.com/jbeder/yaml-cpp) — YAML parser and emitter for C++.

### Command-line parsing

- [CLI11](https://github.com/CLIUtils/CLI11) — Command-line parser for C++ applications.
- [cxxopts](https://github.com/jarro2783/cxxopts) — A lightweight, header-only command-line option parser.
- [argparse](https://github.com/p-ranav/argparse) — An argparse-style command-line argument parser for C++17.

### Time and hashing utilities

- [date](https://github.com/HowardHinnant/date) — Date and time library from the author of `<chrono>`; implements the standard time-zone facilities for older toolchains.
- [xxHash](https://github.com/Cyan4973/xxHash) — An extremely fast, non-cryptographic hash algorithm (C with a C++ header); complements `std::hash` for hashing at scale.

## Contributing

Contributions are welcome! Please open a pull request to add a useful project or improve an entry. For additions, include:

- The project name and canonical link.
- A concise, factual description of what it replaces or complements.
- A clear category and any important scope or compatibility caveats.

Please keep the list focused on useful C++ libraries, distinguish true replacements from complementary tools, and avoid promotional claims or unsupported performance rankings. Check that project links are current before submitting.
