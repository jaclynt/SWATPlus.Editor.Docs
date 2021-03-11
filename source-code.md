# Source Code

## Repository Links

* [SWAT+ source code repository](https://bitbucket.org/blacklandgrasslandmodels/modular_swatplus)
* [SWAT+ Editor source code repository](https://bitbucket.org/swatplus/swatplus.editor)
* [QSWAT+ source code repository](https://bitbucket.org/ChrisWGeorge/qswatplus3)

## SWAT+ Model Compile Help

The model is written in Fortran and the distributions on this website were compiled using the [Intel Fortran compiler](https://software.intel.com/content/www/us/en/develop/tools/oneapi/components/fortran-compiler.html). This is now freely available for Windows, Linux, and MacOS. First, download and install the [Intel oneAPI Base Toolkit](https://software.intel.com/content/www/us/en/develop/tools/oneapi/base-toolkit/download.html). Then download and install the [Intel oneAPI HPC Toolkit](https://software.intel.com/content/www/us/en/develop/tools/oneapi/hpc-toolkit/download.html).

For Windows, we also use Visual Studio. Download the file below for settings configuration.

{% file src=".gitbook/assets/intel\_fortran\_newest\_settings.doc" caption="Intel Fortran Visual Studio Settings" %}

For Linux and MacOS, we currently just use the command line. First, you need to set your Intel environment. Find your installation directory and source `setvars.sh`. 

Linux example:

```text
. ~/intel/oneapi/setvars.sh
```

MacOS example:

```text
. /opt/intel/oneapi/setvars.sh
```

Next, we use the following script to compile the model. Please note: occasionally some extra files get included in the source code repository. If you notice this, it is safe to remove them.

```text
ifort -c hru_module.f90
ifort -c time_module.f90
ifort -c constituent_mass_module.f90
ifort -c *_module.f90
ifort -c allocate_parms.f90
ifort -c *.f90
ifort -o swatplus_exe_file_name *.o -static
```

The `-static` flag in the last line is NOT available on MacOS.

We are new to compiling in Linux and MacOS, so suggestions are more than welcome.

## SWAT+ Editor Compile Help

First set up your development environment as described in the README in the [source code repository](https://bitbucket.org/swatplus/swatplus.editor).

Next, build the Vue.js files. From a terminal, run:

```text
npm run build
```

Then, build the python APIs using `pyinstaller`. A different script is provided for each platform:

```text
python-build-windows
```

```text
sh python-build-mac.sh
```

On Linux, we want to provide static libraries, so first please install the Python `staticx` package.

```text
pip install staticx
sh python-build-linux.sh
```

Finally, build an installer for your platform.

```text
npm run dist
```

For MacOS, it is `npm run dist-mac` and for Linux it is `npm run dist-linux`. See the `package.json` file for build configuration. It uses the [Electron Builder package](https://www.electron.build/).

