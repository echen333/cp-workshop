# Setup

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
- Download [MinGW](https://mingw-w64.org/).
- Install MinGW by following the on-screen instructions.
- To add MinGW to your system PATH:
  1. Right-click on "This PC" or "My Computer" and select "Properties."
  2. Click on "Advanced system settings."
  3. Click on "Environment Variables."
  4. Under "System variables," find and select the "Path" variable, then click on "Edit."
  5. Click on "New" and paste the path to the `bin` directory inside your MinGW installation (usually `C:\MinGW\bin` or `C:\Program Files\mingw-w64\x86_64-8.1.0-posix-seh-rt_v6-rev0\mingw64\bin`).
  6. Click "OK" to close all the dialog boxes.
- Restart your computer or command prompt to apply the changes.

### On Linux

- Open a terminal and run `sudo apt install build-essential`
- Once that finishes, run `g++ --version` in the terminal to verify it installed properly.

## Create an Account on Codeforces and Join GT Group

1. Go to the [Codeforces website](https://codeforces.com/).
2. Click on "Enter" or "Register" and follow the prompts to create an account.
3. Verify your account through your email.
4. To join the GT Competitive Programming group, click [this link](YOUR_LINK_HERE) or navigate to the group page and request to join.
5. Follow any additional instructions on the group page to complete your membership.

**Note**: If you encounter any difficulties, please reach out to a club officer for assistance, or consult the specific resources provided by the club.

## IDE

We recommend using Sublime Text for competitive programming (please make our life easier and use Sublime Text, if only for CP). Below are the instructions to get started with C++ development in Sublime Text.

- Download and install [Sublime Text](https://www.sublimetext.com/3).
- After installing Sublime Text, you'll need to configure it to work with your C++ compiler (e.g., MinGW).
- Go to "Tools" > "Build System" > "New Build System..." in Sublime Text.
- Delete the pre-filled content and paste the following code:
  ```json
  {
    "cmd": ["g++", "${file}", "-o", "${file_path}/${file_base_name}", "&&", "${file_path}/${file_base_name}.exe"],
    "selector": "source.c++",
    "shell": true
  }
  ```
- Save the file with a meaningful name, like cpp_build.sublime-build.
- Now you can press Ctrl + B to compile and run C++ files directly within Sublime Text.

## Template Code

We provide a starting code template at [template.cpp](./template.cpp). This template includes essential libraries and a standard setup. Feel free to modify it to suit your coding style.

## Create an Account on Codeforces

[Codeforces](https://codeforces.com/) hosts regular programming contests. Creating an account will allow you to participate and track your progress.

1. Go to the [Codeforces website](https://codeforces.com/).
2. Click on "Enter" or "Register."
3. Fill in the required information and verify your account.

Now let's [solve our first problem](./2_solve_your_first_problem.md)!
