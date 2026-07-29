---
title: "Example Project"
date: 2026-07-29
draft: true
status: "in development"
tags: ["C++", "SDL2"]
repo: "https://github.com/DanCDay/example-project"
demo: ""
summary: "A placeholder entry showing how the projects page renders — swap this out for a real one."
---

This is a placeholder to show the format — delete or overwrite it once you've got a real project to add.

A few things to notice:

- `status`, `stack`, and the date show up as compile-flag chips under the title, same treatment as post metadata.
- `repo` and `demo` (leave `demo` blank to hide that link entirely) render as buttons under the header.
- The body supports the same Markdown as posts, including fenced code blocks:

```cpp
#include <iostream>

int main()
{
    std::cout << "hello, world\n";
    return 0;
}
```

- This file has `draft: true`, so it won't appear on the live site or in `hugo --minify` builds — only in `hugo server -D`. Flip it to `false` (or delete the line) once you're ready to publish a real one.
