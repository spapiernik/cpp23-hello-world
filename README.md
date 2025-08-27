# C++23 Hello World

A minimal example of the new `std::println` function introduced in C++23,
available in `<print>`.

This repository uses Meson for the build system and contains only the essentials:

- `main.cpp` with `std::println("Hello, world!");`
- `meson.build` for building
- CI/CD via GitHub Actions

View the code in action here: [Godbolt link](https://godbolt.org/z/b5YYPx8aP)

The purpose of this repository is to showcase how C++23
simplifies printing compared to the traditional `std::cout << ...` approach.
