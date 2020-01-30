SPIRAL
======

#### Installer for Windows (spiral-setup.exe)

This is the Readme file for SPIRAL as installed on Windows.  The setup software installs SPIRAL executables, libraries, and associated tools for the user.  There is no need to build the software from source.

### Windows Installation

Running SPIRAL frequently requires code to be compiled (e.g., to determine an optimal or near-optimal rule tree for a transform).  To do this SPIRAL uses the profiler (part of the standard SPIRAL install) to compile and link code.  The SPIRAL profiler assumes a compiler (Visual Studio by default) is installed on the target machine.  For a standard Visual Studio installation, the VS Installer places files at: **C:\Program Files (x86)\Microsoft Visual Studio\Installer**.  This is the case regardless of the version  (since VS 2017).  The default paths and environment variables for VS are set by the [VS provided] script **VsDevCmd.bat**.  The path to find this script is determined from the VS installation, so no configuration or setup to *find the compiler location* should be required by the end user, assuming a standard installation.

The installer will check for a prior installation and offer to remove it if desired (generally this is not necessary as the prior installation will be updated/overwritten).

There are some pre-requisites for Visual Studio to be able to correctly run the profiler from SPIRAL.  These may be checked/configured as follows:

1. Start Visual Studio Installer
2. Select **Modify** button
3. Select **Individual Components** (the components already installed are listed under *Installation Details* to the right)
4. Ensure the following components are present (add them if not):
 * Python language support
 * MSVC v142 - VS 2019 C++ x64/x86 build tools
 * Python 3 64-bit (3.7.X)
 * C++ CMake tools for Windows
 * Windows 10 SDK (10.0.NNNNN...)
5. If you add any components select the **Modify** button to download and install the required packages.

### Other Compilers

The SPIRAL profiler can use other compiler toolschains to compile and link generated code.  The following compilers are supported (assuming the user has installed the the tools):
* LLVM compiler infrastructure project
* GNU Compiler Collection (gcc)
* Intel icl compiler (Intel Parallel Studio XE)

The installer will try to determine the path to these compilers.  If the path is unknown the user can select the path so the compiler can be used.  The selected path is added to the command scripts (batch files) used to run the profiler and does not impact the user's working path settings.

### Other Packages

The SPIRAL Profiler requires **Python 3**, which you can get from [python.org](http://python.org/downloads/).

SPIRAL profiler invoked scripts for Windows rely on **nmake** (vs **make**) so no make package is required (when using the default Microsoft Visual Studio compiler).

### Starting SPIRAL

SPIRAL may be started as follows:
* Using the installer created desktop icon [optionally created during install process]
* Using the Start menu -> Spiral
* Run a **cmd** window and type **spiral**

### Uninstalling SPIRAL

Code generated by SPIRAL may be written to files as necessary.  By default, generated files are created in the default working directory (**\Users\\<user\>\AppData\Roaming\Spiral**).  These files, if any, will **not** be automatically removed on uninstall; the user may remove or keep them as desired.

SPIRAL may be uninstalled as follows:
* Using the Start menu -> Spiral -> Uninstall
* Using the Add/Remove program feature [from Settings or Control Panel], find *Spiral* and remove
