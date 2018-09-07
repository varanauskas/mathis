# Mathis

An incredibly simple C input/output tester with a build tool

version 1.0.0

## Installation

You have a few couple of choices on how to install:

1. Install for a single project:
```
curl https://raw.githubusercontent.com/varanauskas/mathis/master/mathis > mathis && chmod +x mathis
```

2. (Requires sudo) Install globally for all users:
```
sudo curl https://raw.githubusercontent.com/varanauskas/mathis/master/mathis > /usr/local/bin/mathis && chmod +x /usr/local/bin/mathis
```

## Usage

```
(project folder)/
├── tests/
│   └── (test name or number)/
│       ├── in
│       └── out
└── (project name).c
```

1. Open the folder of your `*.c` file in terminal
2. Create a `tests` folder
3. Create a named (or numbered) test folder for each test with `in` and `out` files representing the expected input and output of your program.
4. Run `./mathis` if it's installed for a single project only or `mathis` if it's installed globally and see the test resuts

## Example

```
// greeter.c - the file to test
#include <stdio.h>

int main(int argc, char const *argv[])
{
    char name[8]; // Array size is too small to fit a full name
    scanf("%s", name);
    printf("Hello, %s!\n", name);
    return 0;
}

// tests/john/in - input for the first test
John

// tests/john/out - expected output of the first test
Hello, John!

// tests/judge-mathis/in - input for the second test
Judge Mathis

// tests/judge-mathis/out - expected output of the second test
Hello, Judge Mathis!
```
**output**
```
tests/john
tests/judge-mathis
1c1
< Hello, Judge Mathis!
---
> Hello, Judge!
```
Difference between the expected and actual output is only shown when they do not match

## Notes

* Whitespace is also checked in the output, be sure to keep that in mind when adding (or not adding) newlines (`\n`)
* `.mathis` folder is created on each execution, make sure it is added to the ignore settings of your version control system
* Mathis is almost an anagram of Themis

## Licence

see `LICENCE`
