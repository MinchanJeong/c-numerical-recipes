# C Numerical Recipes: Zero-Dependency Computational Library

[![Language](https://img.shields.io/badge/Language-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Build](https://img.shields.io/badge/Build-Makefile-lightgrey.svg)](https://www.gnu.org/software/make/)
[![Dependencies](https://img.shields.io/badge/dependencies-none-brightgreen.svg)]()
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A robust, **zero-dependency** numerical computation library built entirely from scratch in C. This project implements core mathematical engines—from arbitrary-precision arithmetic to Monte Carlo simulations—demonstrating a deep understanding of low-level memory management, data structures, and numerical algorithms without relying on external libraries like BLAS or LAPACK.

---

### 🚀 Key Engineering Highlights

#### 1. Custom Memory Lifecycle Management
To prevent memory leaks in a complex C environment, I implemented a **lightweight memory tracker** (`allocd_list`).
- **Mechanism:** Hooks into dynamic allocation to maintain a linked list of all active pointers.
- **Benefit:** Ensures **automatic garbage collection**-like behavior, guaranteeing that all allocated resources are cleanly freed upon program termination.
```c
// common.h
struct allocd_list_struct {
    void *ptr;
    struct allocd_list_struct *prev;
};
// Automatically tracks and frees memory chains
extern int write_allocdlist(void*); 
extern int free_allocdlist();
```

#### 2. Arbitrary-Precision Arithmetic Engine
Implemented a custom **Big Integer** structure (`struct degree`) to handle calculations exceeding standard data type limits (e.g., `1000!`).
- **Design:** Uses a linked-list based approach where each node stores a segment of the large number.
- **Capabilities:** Supports exact addition, subtraction, multiplication, and division for high-order factorials and Bernoulli numbers.

#### 3. Robust Linear Algebra & Calculus
Built a complete mathematical engine from first principles:
- **Linear Algebra:** Dynamic matrix operations including **LU Decomposition (Dolittle Algorithm)**, determinant calculation, and matrix inversion.
- **Calculus:** Numerical integration (Trapezoidal, Simpson's, Boole's rules) and differentiation (Jacobian matrix calculation).
- **Monte Carlo:** Implemented **Metropolis-Hastings algorithm** for high-dimensional integration and sampling.

---

### 📂 Project Structure

The library is organized into modular components:

- **`linalgb.C`**: Core matrix operations and linear solvers.
- **`calculus.C`**: Numerical integration and differentiation engines.
- **`monte.C`**: Monte Carlo and Metropolis sampling algorithms.
- **`degcore.C`**: Arbitrary-precision arithmetic logic.
- **`common.C`**: Custom memory management utilities.

### 🛠️ How to Build

The project utilizes a `Makefile` for streamlined compilation.

```bash
# Compile all modules and test executables
make all

# Run specific numerical experiments (e.g., Midterm/Final exam solutions)
./ans1
./ans2
```

### 📜 Context
Developed as part of the *Computational Physics* curriculum at Seoul National University (2019). The goal was to understand the "black box" of scientific computing libraries by re-implementing them from the ground up.
