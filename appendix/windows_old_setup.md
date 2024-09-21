# (Old) Windows Setup.

## This method of setting up C++ on Windows is **NOT** recommended. Please see the [setup](/2_setup.md) to set up C++ with WSL (recommended)

For Windows we will install TDM-GCC.

- Go to https://jmeubank.github.io/tdm-gcc/download/ and download `tdm64-gcc-10.3.0-2.exe`.
- Open the application and select "Create" to "Create a new TDM-GCC installation".
- For edition, select "MinGW-w64/TDM64 (32-bit and 64-bit)".
- For installation directory, you can leave it as the default one they choose, which is usually `C:\TDM-GCC-64`.
- For choosing components, leave the dropdown as the default "TDM-GCC Recommended, C/C++". Don't change any of the checkbox options. In particular, make sure "Add to PATH" is checked by default (it should be) so that you can compile with the terminal.
- Click "Install".
- Once that is done, run `g++ --version` in the terminal to verify it installed properly.

If for whatever reason your TDM-GCC installation got messed up, you can fix it by reopening the installer application and selecting "Manage" instead of "Create" to modify your old installation. This will bring you back to the "Choose Components" screen where you can make sure all the proper boxes are checked.

