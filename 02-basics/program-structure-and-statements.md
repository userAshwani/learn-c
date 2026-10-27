---
title: "C Program Structure and Statements"
description: "Breaking down a basic C program line by line, and understanding what a statement actually is."
tags: ["basics", "syntax", "statements"]
difficulty: "beginner"
date: "2026-10-27"
---

## Breaking down a basic program, line by line

It helps to actually walk through a minimal C program one line at a time
instead of treating it as boilerplate to copy-paste:

```c
#include <stdio.h>

int main() {
    printf("Hello World!");
    return 0;
}
```

- **Line 1, `#include <stdio.h>`** — pulls in a header file so the program
  can use input/output functions like `printf()`. You don't need to fully
  understand how `#include` works under the hood yet; just treat it as
  something that's almost always present at the top of a C file.
- **Line 2** — a blank line. C completely ignores extra whitespace and
  blank lines; they exist purely to make the code easier for a human to
  read.
- **Line 3, `int main() {`** — this is where execution actually begins.
  Everything inside the curly braces `{}` is what runs. The `int` before
  `main()` means the function hands back a whole number when it finishes —
  that's the `0` in `return 0;` further down.
- **Line 4, `printf("Hello World!");`** — a function call that outputs text
  to the screen.
- **Line 5, `return 0;`** — ends `main()` and sends a value back to the
  operating system. Returning `0` conventionally means "everything worked."
- **Line 6, `}`** — closes out `main()`. Forgetting this closing brace is
  an easy mistake that breaks the whole program.

A small but useful thing to know: the body of `main` doesn't strictly have
to be spread across multiple lines — `int main(){printf("Hello World!");return 0;}`
is technically valid too. The compiler doesn't care about the extra spaces
and line breaks; they're there purely for readability, which is exactly
why we use them.

## What a "statement" actually is

A computer program is fundamentally just a list of instructions for the
computer to follow. In C, each individual instruction is called a
**statement**. `printf("Hello World!");` is itself one complete statement.

The rule that trips people up most often: **every statement in C must end
with a semicolon `;`**. This isn't a style preference — it's how the
compiler knows where one instruction ends and the next one begins. Forget
it, and the compiler throws an error and refuses to produce a program at
all:

```c
printf("Hello World!")
```

```
error: expected ';' before 'return'
```

That specific error message is worth recognizing on sight, because
"missing semicolon" is one of the most common beginner mistakes, and the
compiler's error can look more intimidating than the actual problem is.

## Multiple statements run in order

Most real programs contain more than one statement, and C runs them
strictly top to bottom, in the exact order they're written — there's no
reordering or parallel execution happening behind the scenes:

```c run
#include <stdio.h>

int main() {
    printf("Hello World!");
    printf("Have a good day!");
    return 0;
}
```

Here there are three statements: two `printf()` calls and a `return 0;`.
The first `printf` runs and prints `Hello World!`, then the second runs and
prints `Have a good day!`, and only then does `return 0;` run and end the
program. This "one instruction at a time, strictly in sequence" model is
the foundation everything else in C builds on — loops and conditionals
later on are really just ways of controlling *which* statements run and
*how many times*, not a departure from this basic rule.
