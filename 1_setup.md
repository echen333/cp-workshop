# Setup

*Prev: [README.md](./README.md)*

At GT Competitive Programming, we **strongly** encourage everyone to use C++. If you know Java or Python, that's great! These languages have similar constructs, and you should be able to pick up C++ quickly.

## Why C++

C++ is a widely-used systems programming language known for its fast coding and execution speed. Its syntax allows for concise expressions of complex algorithms, making it a favorite choice in competitive programming. It also has:

- **Fast Execution**: 10x faster than interpreted languages like Python.
- **Rich Library Support**: Includes the Standard Template Library (STL) with ready-to-use templates for common data structures and algorithms.
- **Systems Programming**: Offers low-level access to computer memory, somewhat useful for optimizations.

## Install C++

### On Mac with new silicon chips (M1, M2)

- Check if you have Homebrew installed by opening Terminal and running `brew --version`. If not installed, proceed to the next step.
- Install [Homebrew](https://brew.sh/), a package manager for macOS, by following the instructions on their website or running the provided installation script in Terminal.
- Open Terminal and run `brew install gcc` to install the GNU Compiler Collection, which includes C++.
- Verify the installation by running `g++ --version` in Terminal. You should see information about the installed version.

### On Older Macs

- Check if Xcode Command Line Tools are installed by opening Terminal and running `gcc --version`. If a version number is displayed, the tools are already installed. If not, proceed to the next step.
- Open Terminal and install Xcode Command Line Tools by running `xcode-select --install`. A popup window will appear; click "Install" to proceed.
- Follow the on-screen instructions to complete the installation.
- Verify the installation by running `g++ --version` in Terminal. You should see information about the installed version.

**Note**: Last time I did this, it was quite annoying and took a long time. Ask any of the officers for help if you need.

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

We recommend using Sublime Text for competitive programming (please make our life easier and use Sublime Text, if only for CP). Below are the instructions to get started with C++ development in Sublime Text.

- Download and install [Sublime Text](https://www.sublimetext.com/3).
- After installing Sublime Text, you'll need to configure it to work with your C++ compiler (e.g., MinGW).
- Go to "Tools" > "Build System" > "New Build System..." in Sublime Text.
- Delete the pre-filled content and paste the following code:
  ```json
  {
    "cmd": ["g++.exe", "-std=c++14", "-o", "$file_base_name", "$file", "&&", "start", "cmd", "/c", "$file_base_name & echo. & echo. & pause"],
    "shell": true,
    "selector": "source.c++"
  }
  ```
- Save the file to the default directory they provide with a meaningful name, like `cpp_build.sublime-build`.
- Now you can press Ctrl + B to compile and run C++ files directly within Sublime Text.

*Note*: Sublime may once in awhile ask for you to buy their premium version. Just ignore this, premium has no better features.

## Template Code

We provide a starting code template at [template.cpp](./appendix/template.cpp). This template includes essential libraries and fast Input/Ouput (fastIO). Feel free to modify it to suit your coding style.

## Run Hello World Locally

1. Create a new file in any directory in Sublime Text.

   ```cpp
   #include <bits/stdc++.h>
   
   int main() {
     cout << "Hello World" << '\n';
   }
   ```

2. Press `Ctrl-B` or `Cmd-B` on Mac. A black terminal window should popup with the output Hello World!.

Now let's [solve our first problem](./2_solve_your_first_problem.md)!
