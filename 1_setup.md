# Setup

*Prev: [README.md](./README.md)*

At GT Competitive Programming, we **strongly** encourage everyone to use C++. If you know Java or Python, that's great! These languages have similar constructs, and you should be able to pick up C++ quickly.

## Why C++

C++ is commonly used for systems programming due to its speed and efficient coding. Its clear syntax helps in writing complex algorithms concisely, making it popular for competitive programming. It offers:

- Faster execution compared to languages like Python.
- A robust Standard Template Library (STL) for data structures and algorithms.
- Low-level memory access for optimization.

## Install C++

### On Macs (both silicon and pre-silicon)

- Check if you have Homebrew installed by opening Terminal and running `brew --version`. If not installed, proceed to the next step.
- Install [Homebrew](https://brew.sh/), a package manager for macOS, by following the instructions on their website or running the provided installation script in Terminal.
- Open Terminal and run `brew install gcc` to install the GNU Compiler Collection, which includes C++.
- Verify the installation by running `g++ --version` in Terminal. You should see information about the installed version.
- To include headers, open `Finder` and navigate to filepath `/usr/local/include/bits/`, creating directories as needed. Create a file in the `bits` folder named `stdc++.h` and paste the file contents from [including_bits.md](./appendix/including_bits.md) into it.
  - Now you should be all set to write `#include "bits/stdc++.h"` in your C++ programs. Think of this as `import` in Java and Python.
  - Note: do not use include with angle brackets for bits, use quotes.
  - `TODO`: include terminal commands since hard to find in `Finder`.

**Note**: Ask any of the officers for help if you need.

### On Windows

For Windows we will install TDM-GCC.

- Go to https://jmeubank.github.io/tdm-gcc/download/ and download `tdm64-gcc-10.3.0-2.exe`.
- Open the application and select "Create" to "Create a new TDM-GCC installation".
- For edition, select "MinGW-w64/TDM64 (32-bit and 64-bit)".
- For installation directory, you can leave it as the default one they choose, which is usually `C:\TDM-GCC-64`.
- For choosing components, leave the dropdown as the default "TDM-GCC Recommended, C/C++". Don't change any of the checkbox options. In particular, make sure "Add to PATH" is checked by default (it should be) so that you can compile with the terminal.
- Click "Install".
- Once that is done, run `g++ --version` in the terminal to verify it installed properly.

If for whatever reason your TDM-GCC installation got messed up, you can fix it by reopening the installer application and selecting "Manage" instead of "Create" to modify your old installation. This will bring you back to the "Choose Components" screen where you can make sure all the proper boxes are checked.

### On Linux

- Open a terminal and run `sudo apt install build-essential`
- Once that finishes, run `g++ --version` in the terminal to verify it installed properly.

## Create an Account on Codeforces and Join GT Group

1. Go to the [codeforces.com](https://codeforces.com/).
2. Click on "Register" in the top right and follow the prompts to create an account.
3. Verify your account through your email.
4. To join the GT Competitive Programming group, click [this link](https://codeforces.com/group/j7YsoIFtw4/contests) or navigate to the group page and request to join as a Participant on the right-side panel.

## IDE

We recommend VS Code for competitive programming. Refer to [our VS Code guide](./appendix/vscode.md) for setup instructions. Everything up to and including the section "Compiling and Executing a C++ Program" is necessary, while the sections after are for quality of life (but encouraged to follow after the workshop).

## Template Code

We provide a starting code template at [template.cpp](./appendix/template.cpp). This template includes essential libraries and fast Input/Ouput (fastIO).

## Run Hello World Locally

1. Create a new cpp file and paste the following code into it.

   ```cpp
   #include <bits/stdc++.h>
   using namespace std;

   int main() {
     cout << "Hello World" << '\n';
   }
   ```

2. Compile and run the code according to the instructions in the [VS Code setup guide](./appendix/vscode.md). You should see the output "Hello World" in your terminal.

Now let's [solve our first problem](./2_solve_your_first_problem.md)!
