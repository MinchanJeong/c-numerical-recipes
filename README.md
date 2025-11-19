# C Numerical Recipes: A Foundational Library from Scratch

[![Language](https://img.shields.io/badge/Language-C-blue.svg)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Build](https://img.shields.io/badge/Build-Makefile-lightgrey.svg)](https://www.gnu.org/software/make/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A fundamental numerical computation library for scientific applications, built entirely from scratch in C. This project was an exercise in implementing core computational tools from first principles, covering a wide range of numerical methods without relying on external libraries.

### Core Modules

- **Arbitrary-Precision Arithmetic:**
  - A custom `degree` struct to handle integers of arbitrary size, breaking the limits of standard data types.
  - Enables exact calculations for large numbers, such as high-order factorials and binomial coefficients.

- **Linear Algebra Engine:**
  - A complete matrix library with dynamic memory allocation.
  - Implements fundamental operations: matrix multiplication, addition, and inversion.
  - Features a robust **LU Decomposition** implementation for solving systems of linear equations and calculating determinants.

- **Numerical Calculus:**
  - A suite of functions for numerical integration, including Trapezoidal, Simpson's, and Boole's rules.
  - Implements numerical differentiation for single and multivariate functions, including the calculation of the **Jacobian matrix**.

- **Monte Carlo Methods:**
  - Includes implementations for high-dimensional integration using both standard Monte Carlo and the **Metropolis-Hastings** algorithm for importance sampling.

- **Custom Memory Management:**
  - A lightweight memory tracker (`allocd_list`) that hooks into `malloc` to keep a record of all dynamically allocated memory.
  - Ensures all allocated memory is properly freed upon program termination, preventing memory leaks.

### How to Build

The project is organized with a `Makefile` for easy compilation of different components.

```bash
# Compile all targets
make all
```

# Compile a specific target (e.g., for the final exam)
make ans1 ans2 ans3
