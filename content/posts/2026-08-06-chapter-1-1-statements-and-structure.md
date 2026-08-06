---
title: "Chapter 1.1 Statements and Structure of a Program"
date: 2026-08-06T20:56:31+01:00
draft: false
lesson: "1.1"            # e.g. "1.6" — the learncpp.com lesson number, leave blank if not applicable
tags: ["basics"]               # e.g. ["basics", "cherno"]
resources:             # what you were following along with
  - "learncpp.com §1.1"
---

## Statements

The concept of statements makes sense when explained as an instruction that causes the program to perform an action.

`std::cout << "Hello World" << '\n';`

This statement causes the program to print "Hello World" to the terminal. This section didn't explain everything that makes
up the statement but just covered the basics.

I decided to have a bit of a tinker and see what happens if I try to break this statement so it doesn't print at all.

If I were to remove the `;` from the end it turns out the program refuses to compile at all, I got this compilation error.

```cpp
FAILED: [code=1] CMakeFiles/playground.dir/main.cpp.o 
/usr/lib64/ccache/c++   -g -std=c++23 -fdiagnostics-color=always -pedantic-errors -Wall -Wextra -Wpedantic -Werror -MD -MT CMakeFiles/playground.dir/main.cpp.o -MF CMakeFiles/playground.dir/main.cpp.o.d -fmodules-ts -fmodule-mapper=CMakeFiles/playground.dir/main.cpp.o.modmap -MD -fdeps-format=p1689r5 -x c++ -o CMakeFiles/playground.dir/main.cpp.o -c /home/dan/CLionProjects/playground/main.cpp
/home/dan/CLionProjects/playground/main.cpp: In function ‘int main()’:
/home/dan/CLionProjects/playground/main.cpp:4:46: error: expected ‘;’ before ‘return’
    4 |     std::cout << "Hello, World!" << std::endl
      |                                              ^
      |                                              ;
    5 |     return 0;
      |     ~~~~~~                                    
ninja: build stopped: subcommand failed.
```

That's a pretty useful error, tells me where I've gone wrong and gives me a way to fix it `error: expected ';' before 'return'`

I'm sure compilation errors get way more complex than this one but it's good to see what I'll be working with during these
first few chapters until I get to the more advanced stuff.

That got me thinking, what if I removed one of the `:` from after `std`?

```cpp
FAILED: [code=1] CMakeFiles/playground.dir/main.cpp.o 
/usr/lib64/ccache/c++   -g -std=c++23 -fdiagnostics-color=always -pedantic-errors -Wall -Wextra -Wpedantic -Werror -MD -MT CMakeFiles/playground.dir/main.cpp.o -MF CMakeFiles/playground.dir/main.cpp.o.d -fmodules-ts -fmodule-mapper=CMakeFiles/playground.dir/main.cpp.o.modmap -MD -fdeps-format=p1689r5 -x c++ -o CMakeFiles/playground.dir/main.cpp.o -c /home/dan/CLionProjects/playground/main.cpp
/home/dan/CLionProjects/playground/main.cpp: In function ‘int main()’:
/home/dan/CLionProjects/playground/main.cpp:4:9: error: ‘cout’ was not declared in this scope; did you mean ‘std::cout’?
    4 |     std:cout << "Hello, World!" << std::endl;
      |         ^~~~
      |         std::cout
In file included from /home/dan/CLionProjects/playground/main.cpp:1:
/usr/include/c++/16/iostream:65:18: note: ‘std::cout’ declared here
   65 |   extern ostream cout;          ///< Linked to standard output
      |                  ^~~~
/home/dan/CLionProjects/playground/main.cpp:4:5: error: label ‘std’ defined but not used [-Werror=unused-label]
    4 |     std:cout << "Hello, World!" << std::endl;
      |     ^~~
cc1plus: all warnings being treated as errors
ninja: build stopped: subcommand failed.
```

This one's got a bit more information, something about the label 'std' being defined and not used, I assume it's recognising
`std` but producing an error where there's supposed to be two `::` and not one, it looks like it gives the recommendation of
what should be there as well just under the `^~~~` which is `std::cout`, that's pretty handy!

I think this is covered more in depth in Chapter 3 since it's about debugging programs.

Another thing that's a bit confusing though is that in this section it says

>Most (but not all) statements in C++ end in a semicolon. If you see a line that ends in a semicolon, it's probably a statement.

I'm not sure I understand why some statements end with a `;` and some don't, hopefully this will be covered in later sections.


## Functions and the `main` function

Ok, a function is a collection of statements that get executed from top to bottom. That's simple enough. It looks like every
C++ program has to have a function named `main` which is the starting and finishing point of a program.

When talking about functions it's become common for people to use `()` at the end of a name to help others identify that it's
a function and not other things.

I have read some documentation for my job that mentions things such as `lighting()` for example, good to know that it's referring
to a function.

>In programming, the name of a function (or object, type, template, etc...) is called it's **identifier**

Makes sense.


## Characters and text

Characters are a single written symbol (`a`,`2`,`£`,`=`). Reminds me of using Character Map on Windows whilst growing up.

A sequence of characters becomes a string, I wonder if behind the scenes it's literally just doing `H`+`e`+`l`+`l`+`o` to make a string.
I'll have to see if a later chapter answers that question.

## "Hello world" Dissected

```cpp
#include <iostream>

int main()
{
  std::cout << "Hello world!";
  return 0;
}
```
|Line |&nbsp; &nbsp; | Purpose                                                                             |
:-----|--------------|:------------------------------------------------------------------------------------|
|1    |              | Preprocessor directive, gives access to the iostream library needed for `std::cout` |
|2    |	             | Blank line, improves readability                                                    |
|3    |	             | Declares the `main` function that returns an `int`                                  |
|4,7  |	             | Curly braces `{ }` mark the start and end of the function body                      |
|5    |	             | Statement that prints "Hello world" to the terminal                                 |
|6    |              | Return statement that sends `0` back to the OS, which means success                 |


## Summary

This section covered a good amount on the basics, I enjoyed purposely breaking the statements and seeing what would happen,
I suppose that does me well in my QA role, I'll make sure to do it more often when writing projects for each chapter!

It ended in a quiz where I got all of the answers right which is a good confidence boost that the information is going in, I
can't promise it will stay there but I'll do my best.

I feel like a lot of people will see how simple this first section is and lose interest, there's still a lot of good information
in there though, highly recommended to get a solid foundation.
