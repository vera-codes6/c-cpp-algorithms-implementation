# Algorithms and Data Structures in C++ {#mainpage}

Modern, self-contained implementations of classic algorithms and data structures in C++17. Code is organized by topic and builds with CMake on Windows, macOS, and Linux. Licensed under the MIT License.

## Highlights

- C++17 throughout, using the Standard Library only (no third-party deps by default)
- One executable per example/source file for easy exploration
- Optional OpenMP for multithreading where applicable
- Optional OpenGL/GLUT for graphics samples (auto-downloads FreeGLUT if needed)
- Optional Doxygen docs generated directly from source

## Repository layout

Top-level folders group related algorithms. Examples include:

- `backtracking/` – N-Queens, Sudoku solver, graph coloring, subset sum, etc.
- `bit_manipulation/` – bit tricks, Gray code, Hamming distance, power of 2, etc.
- `ciphers/` – Caesar, Vigenère, Hill, Atbash, Base64, XOR, ECC key exchange
- `cpu_scheduling_algorithms/` – FCFS, SJF, and related scheduling examples
- `data_structures/` – BST, AVL, RB-tree, heaps, queues, stacks, skip lists, DSU, segment/sparse tables
- `divide_and_conquer/`, `dynamic_programming/`, `graph/`, `greedy_algorithms/`, `search/`, `sorting/`, `strings/`, and more
- `graphics/` – OpenGL/GLUT-based visual demos when OpenGL is available
- `doc/` – Doxygen configuration

Each subdirectory contains a `CMakeLists.txt` that turns every `*.cpp` into an executable target.

## Prerequisites

- CMake 3.22+
- A C++17 compiler
	- Windows: MSVC 2022 (preferred) or MinGW-w64
	- Linux: GCC or Clang
	- macOS: AppleClang
- Optional: OpenMP (set via `-DUSE_OPENMP=ON`, enabled by default)
- Optional: Doxygen 1.9+ to build documentation
- Optional: OpenGL + GLUT for `graphics/` (FreeGLUT will be auto-fetched if GLUT is not found)

## Quick start (Windows, PowerShell)

Build all executables with Visual Studio generator:

```powershell
mkdir build; cmake -S . -B build -G "Visual Studio 17 2022" -A x64 -DUSE_OPENMP=ON; cmake --build build --config Release
```

Install to a local prefix (puts executables under `out/bin/<category>`):

```powershell
cmake --install build --config Release --prefix .\out
```

Run an example (after install):

```powershell
.\out\bin\backtracking\generate_parentheses.exe
```

Tip: list available targets:

```powershell
cmake --build build --target help
```

Build a single target only:

```powershell
cmake --build build --target generate_parentheses --config Release
```

MinGW (alternative):

```powershell
cmake -S . -B build -G "MinGW Makefiles" -DUSE_OPENMP=ON; cmake --build build -j
```

## Documentation

If Doxygen is installed, you can build the docs target:

```powershell
cmake --build build --target doc
```

Open `build/doc/html/index.html` in your browser.

## Code style

This repository includes `.clang-format` and `.clang-tidy`. Please run formatting and address warnings before submitting changes.

## License

Distributed under the MIT License. See `LICENSE` for details.

## Acknowledgements

This project follows the structure of, and includes implementations inspired by, TheAlgorithms/C-Plus-Plus. Thanks to all contributors to the broader open-source algorithms community.
