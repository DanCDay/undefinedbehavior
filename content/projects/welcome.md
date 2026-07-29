---
title: "Welcome"
date: 2026-07-29T13:20:51+01:00
draft: false
status: "shipped"     # e.g. "planning", "in development", "on hold", "shipped"
tags: ["C++"]               # e.g. ["C++", "SDL2"]
repo: "https://github.com/DanCDay/learncpp/tree/main/welcome"                # GitHub repo URL — leave blank to hide the link
demo: ""                # live demo URL — leave blank to hide the link
summary: "My first project using everything learned in Chapter 1 of learncpp.com"
---

This is my first project using the information learned in Chapter 1 of learncpp.com, I did end up doing some further research on how to use `std::string` to declare a string
variable since I wanted to create a welcome project that can be customised to the person running it using their name.

```cpp
#include <iostream>
#include <string>

int main() {
    // std::cout prints the text / data on the right of the '<<' to the console
    std::cout << "Welcome to my portfolio! What is your name?" << '\n';

    // 'std::' is required when declaring a string variable since it's not a
    // fundamental type, it's built in using the standard library
    std::string name {};
    std::cin >> name;

    // Using multiple '<<' operators concatenates data to be able to combine text and data
    std::cout << "Hello " << name << ", You'll find all of the projects I've created"
                                  " through my time learning C++ in this Github "
                                  "repository." << '\n';

    std::cout << "My main resources used for learning C++ have been learncpp.com"
                 " and 'The Cherno' on YouTube, as a passive learning experience"
                 " I can't forget to add 'tokyospliff' livestreams as well!" << '\n';

    return 0;
}
```
