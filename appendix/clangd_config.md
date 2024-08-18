# Configuring clangd for VS Code

clangd is a C++ language server which provides a plethora of features such as syntax highlighting, compiler errors, and code completion as you edit your code. This guide will explain how to configure it for optimal use in competitive programming.

## clangd VS Code Extension

You will need the clangd VS Code extension, you can install it [here](https://marketplace.visualstudio.com/items?itemName=llvm-vs-code-extensions.vscode-clangd).

## .clangd

The way you configure clangd is by adding a `.clangd` file to the root directory of your competitive programming repo (so in the same or parent directory of where you write your code). You can read the full details of how to configure `.clangd` from the [docs](https://clangd.llvm.org/config), but the main thing we are interested in configuring is the `CompilerFlags` section. Specifically, `Add` allows us to add compiler flags which we want to compile with and `Compiler` allows us to specify the compiler we use. If you're not sure what configs to use, here is what I have:

```
CompileFlags:
  Add: [
    -std=c++20,
    -Wall,
    -Wextra,
    -Wshadow,
    -Wfloat-equal,
    -Wconversion,
    -Wno-sign-conversion,
    -ferror-limit=0,
  ]
  Compiler: <path to your compiler>
```

Where `<path to your compiler>` should be replaced with the path to your local GNU compiler installation (e.g. mine is `/usr/local/bin/g++`).

To explain each of the flags:
- `-std=c++20`: This compiles your program using the C++ 2020 standard. At the time of writing, the C++ 2023 standard can only be enabled experimentally with `-std=c++2b`.
- `-Wall`: This enables all common compiler warnings.
- `-Wextra`: This enables additional compiler warnings that are not covered by `-Wall`.
- `-Wshadow`: This warns when your program has two variables with the same name and one of them is within the scope of another. An example is something like this:
```c++
int x = 1;

int func() {
    int x = 2;  // this variable shadows the global x
}
```
- `-Wfloat-equal`: This warns when you attempt to compare equality of two floating point values. If you have two floating point variables `double x;` and `double y;`, comparing them directly with `x == y` is risky due to possible precision loss when computing either `x` or `y`. You should instead check if their difference is less than some epsilon: `abs(x - y) < 1e-9`.
- `-Wconversion`: This warns when you do implicit conversions that may alter a value. An example is if you have variables `std::int32_t x;` and `std::int64_t y;` and you assign `x = y;`. This is undefined behavior if `y` exceeds the maximum possible value of a signed 32-bit integer.
- `-Wno-sign-conversion`: Enabling `-Wconversion` also enables `-Wsign-conversion` which specifically checks for conversion from signed to unsigned (e.g. `unsigned int x;` and `int y = x;`). This would be nice to enable, but unfortunately it is very common in competitive programming to access indices of `std::vector` with signed integers, so we should disable this warning with `-Wno-sign-conversion`.
```c++
std::vector<int> v(n);
for (int i = 0; i < n; i++) {
    v[i];   // this will emit a warning under -Wsign-conversion
}
```
- `-ferror-limit=0`: This removes the limit on the number of errors clangd can emit. Without this clangd will sometimes stop emitting errors in a file if there are too many.

You can refer to the full list of compiler warning flags [here](https://gcc.gnu.org/onlinedocs/gcc/Warning-Options.html).

## Compile with GCC

You may have noticed that I specified `/usr/local/bin/g++` as the compiler in my `.clangd` file. As the name may imply, clangd uses clang instead of gcc as its default compiler. For competitive programming we prefer gcc as there are some GNU extensions we would like to use, such as `bits/stdc++.h` and [policy-based data structures](https://codeforces.com/blog/entry/11080). You should of course use the path to your gcc installation instead of the example path I put.

It is possible that clangd still does not use the GNU standard library even after adding this. If this happens, we need to point clangd to the correct system headers with one of the methods mentioned [in the docs](https://clangd.llvm.org/guides/system-headers). The most surefire way I have gotten this to work is by specifying `--query-driver`. In your VS Code `settings.json`, add the following stanza:
```
"clangd.arguments": [
    "--query-driver=**",
],
```
`clangd.arguments` are the command line arguments that VS Code will pass to the clangd binary. clangd is capable of finding the system headers by explicitly querying the compiler specified in our `.clangd` file. To enable this, the `--query-driver` option provides clangd with a list of globs for which clangd is allowed to execute the compiler binary if they match. Putting `**` allows clangd to execute any compiler we ever specify. If you are concerned about executing arbitrary binaries for security reasons, you could of course explicitly specify `--query-driver=<path to your compiler>` instead.

## Quirk with MacOS

Because MacOS loves to shove Apple down our throat, the default Apple clangd simply does not respect the `--query-driver` option and will always attempt to use Apple clang standard libraries [(reference)](https://github.com/clangd/clangd/issues/487). To get around this, use clangd from Homebrew instead. So install it with `brew install llvm`, then either add the Homebrew llvm bin directory as first in your `PATH` environment variable or explicitly point the VS Code clangd extension to it with the `clangd.path` option in `settings.json`.

## Fallback Flags

In [my old VS Code guide](vscode.md), I suggested adding compiler flags with VS Code's fallback flags option (`clangd.fallbackFlags` in `settings.json`). It is more idiomatically correct to specify the compiler flags you want for each particular C++ project with a `.clangd` or `compile_flags.txt` file.

## What is compile_commands.json?

If you look up anything about clangd, most sources will say you need a `compile_commands.json` file. This is bait because `compile_commands.json` is a file automatically generated by your C++ build tool (e.g. CMake). For competitive programming you are probably not using any build tool because you are writing one-off source files to be compiled into individual binaries. Frankly this is why I procrastinated on finding a proper solution to configuring clangd for so long, because the majority of online resources tell you to generate a `compile_commands.json` file.

## Remove Header Auto Include

The clangd autocomplete feature will automatically insert the standard library header for whatever std function you type, even if it is already transitively included through another header. The most relevant scenario in competitive programming is that you already included `bits/stdc++.h`, but clangd will still add a line `#include <vector>` when you autocomplete `std::vector`. To disable this, add `-header-insertion=never` to `clangd.arguments`.

## Code Formatting

clangd is also capable of formatting your code when you hit ctrl+shift+F. You can customize how the formatter works by adding a `.clang-format` file to the root directory of your repo. The docs for that are [here](https://clang.llvm.org/docs/ClangFormatStyleOptions.html).

## Linting

clangd provides linting with clang-tidy. You can customize what checks it performs with a `.clang-tidy` file in the root directory of your repo. The docs are [here](https://clang.llvm.org/extra/clang-tidy/).
