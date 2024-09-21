# Setup

*Prev: [What is competitive programming?](./1_what_is_competitive_programming.md)*

At GT Competitive Programming, we **strongly** encourage everyone to use C++. If you know Java or Python, that's great! These languages have similar constructs, and you should be able to pick up C++ quickly.

## Why C++

C++ is commonly used for systems programming due to its speed and efficient coding. Its clear syntax helps in writing complex algorithms concisely, making it popular for competitive programming. It offers:

- Faster execution compared to languages like Python.
- A robust Standard Template Library (STL) for data structures and algorithms.
- Low-level memory access for optimization.

## Can you use Java or Python or {Other Language}?

Yes. It will be easier to pick up competitive programming if you aren't also learning a new language. Competitve programming as a whole can be hard to dive into, and foreign syntax can add to the frustration. However:

- There are lots more resources online that teach/share tricks for competitive programming in C++.
- The C++ standard library covers everything that you need. Python, for example, does not have a sorted set (used in many problems!) in its standard library.
- There are certain (rare) problems that you will not earn points for (even with the correct solution) simply because Python/Java is too slow.
- This beginner workshop will only cover C++ 🤡.

## Install C++

### On Macs (both silicon and pre-silicon)

- Check if you have Homebrew installed by opening Terminal and running `brew --version`. If not installed, proceed to the next step.
- Install [Homebrew](https://brew.sh/), a package manager for macOS, by following the instructions on their website or running the provided installation script in Terminal.
- Open Terminal and run `brew install gcc` to install the GNU Compiler Collection, which includes C++.
- Verify the installation by running `g++ --version` in Terminal. You should see information about the installed version.
  - Modern gcc compiler binaries typically ship with the version number attached to the name (e.g. the binary name will be `g++-14` instead of simply `g++`). You can still map it to `g++` by creating a symlink.
  - Find the path to the compiler binary that Homebrew installed. For example, mine was installed at `/opt/homebrew/Cellar/gcc/14.1.0_2/bin/g++-14`.
  - Create a symlink in your `/usr/local/bin/` directory (create it if it does not exist) with the command `ln -s <path to your Homebrew g++> /usr/local/bin/g++`. If you already have a symlink in that directory, do `-sf` instead of `-s` to overwrite it. You may need to prefix the command with `sudo` to gain permissions to write to that directory.
- **UPD: You should not need to do the following steps if you compile with g++ from Homebrew, as that should already ship with `bits/stdc++.h`.** To include headers, open `Finder` and navigate to filepath `/usr/local/include/bits/`, creating directories as needed. Create a file in the `bits` folder named `stdc++.h` and paste the file contents from [including_bits.md](./appendix/including_bits.md) into it.
  - Now you should be all set to write `#include "bits/stdc++.h"` in your C++ programs. Think of this as `import` in Java and Python.
  - Note: do not use include with angle brackets for bits, use quotes.
  <!-- - `TODO`: include terminal commands since hard to find in `Finder`. -->

**Note**: Ask any of the officers for help if you need.

### On Windows

- We will install Windows Subsystem for Linux (WSL). This is a virtual-machine-like Linux system that runs on Windows that gives you the pros of Linux without the configuration hassle.
  - We will install the Ubuntu distribution of Linux. You can read more about WSL [here](https://learn.microsoft.com/en-us/windows/wsl/install).
- Open PowerShell and type `wsl --install`.
  - If you see the WSL help text, WSL is already installed on your system. Proceed to the next step.
- The first time you launch a newly installed Linux distribution, a console window will open and you'll be asked to wait for files to de-compress and be stored on your machine. All future launches should take less than a second.
- You can now access WSL by typing `wsl` in PowerShell/CMD.
  - You will know you are in WSL when the last character of the current line is `$`.
  - Logout by pressing Ctrl+D or typing exit and pressing enter.
- In WSL, **proceed to the Linux installation instructions**.

**Note**: Ask any of the officers for help if you need.
**Note**: You can also [install C++ with TDM-GCC/MinGW](./appendix/windows_old_setup.md) (not recommended).

### On Linux

- Open a terminal and run `sudo apt install build-essential`
- Once that finishes, run `g++ --version` in the terminal to verify it installed properly.

**Note**: Ask any of the officers for help if you need.

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

**Congrats!**. You can write and run C++ on your system! We will move on to the *code along* lecture once everyone has reached this step.

Otherwise, you can move on to [solving your first problem](./3_solve_your_first_problem.md) while you wait.
