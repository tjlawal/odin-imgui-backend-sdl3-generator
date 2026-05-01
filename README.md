# Odin ImGui Bindings Generator

This is a fork of [L-4 Odin-Imgui Bindings](https://gitlab.com/L-4/odin-imgui).

This fork strips out all the other backends and uses the code to generate only the SDL3 GPU backend. 
This was tested to work on Odin Compiler Version `dev-2026-04-nightly:a896fb2`.

It also sets the minimum python version to 3.13.13 (not enforced, so it would still run but wont work as expected) as that provides improvements on how strings are handled in subprocess related functions.
It is recommended you do this in a virtualenv `python -m venv .venv` installing dependencies. 

### Dependencies
1. `git` must bin your path
2. `dear_bindings` depends on a library called `ply` [link](https://www.dabeaz.com/ply/), this can should be installed with `python -m pip install ply`
3. Platform specific:
		- On Windows, you need to run this command in the `Developer Command Prompt for VS $YEAR`. This script unlike the original it was forked from doesn't check for `vcvarsall.bat` in your path, it assumes you're running this inside a `Developer Command Prompt` to begin with.
		- OSX and Linux depend on `clang` and `ar`.

## Building
1. Satisfy all dependencies.
2. Clone this repository.
3. Run `python build.py`.
4. Copy generated static library to whereever you need it.


# Configuring
Backends can be configured at the top of the `build.py` file. 
