---
title: "Chapter 0 Introduction / Getting Started"
date: 2026-07-29T13:44:23+01:00
draft: false
lesson: "0"            # e.g. "1.6" — the learncpp.com lesson number, leave blank if not applicable
tags: ["basics"]               # e.g. ["basics", "cherno"]
resources:             # what you were following along with
  - "learncpp.com §0"
---

## Setup

Here we go, arguably the most difficult part of the whole process is actually jumping in and getting started, I followed the setup recommendations in this chapter and
it took me a couple of hours to read through this chapter and get everything set up, I faced a few speed bumps along the way but that's very likely down to the fact that
I'm using Linux and CLion instead of the recommended Code::Blocks.

For those that are curious, here is my system information:

```
Software

OS = Fedora 44
DE = KDE Plasma Wayland
IDE = CLion
Notes = Obsidian

Hardware

Processor = AMD Ryzen 7 260 w/ Radeon 780M Graphics
Memory = 24 GiB RAM
GPU = NVIDIA GeForce RTX 5060 Laptop
```

Whilst following the setup steps in Lesson 0.10,0.11, and 0.12, I created the rules for CMake which will restrict the error messages and some of the more 'flexible' compilation error / warning outputs
to be more concise and practical for learning purposes and it looks to be working as expected so far, for me in CLion, my CMakeLists.txt looks like this.

```cmake
cmake_minimum_required(VERSION 4.3)
project(welcome)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

if (MSVC)
    add_compile_options(/permissive-)
else ()
    add_compile_options(-pedantic-errors)
endif ()

add_executable(welcome main.cpp)

if (MSVC)
    target_compile_options(welcome PRIVATE /W4 /WX)
else ()
    target_compile_options(welcome PRIVATE -Wall -Wextra -Wpedantic -Werror)
endif ()
```

## Compiler, Linker, and Libraries

This section I found particularly interesting, for the longest time I've been curious how the compiler goes about compiling source code files in to executable programs,
I was surprised to learn that the compiler creates an object file for each `.cpp` file in the project, these object files are the C++ code translated in to machine language
instructions.

But in my head that didn't explain how the program knows how and when to access the multiple different files in the project, enter the linker.

This is where it suddenly clicked to me that the compiler is simply that, it compiles the code... the linker is the one that combines all of the object files and produces
the output file, the executable. Mind blown, so simple but I'd never thought of it, I thought the compiler did all of the work.


## Summary

This chapter was really in-depth on how to setup your development environment, I would definitely recommend following it closely to get the best out of the following lessons.
