# Source Code

## Repository Links

* [SWAT+ source code repository](https://bitbucket.org/blacklandgrasslandmodels/modular_swatplus)
* [SWAT+ Editor source code repository](https://bitbucket.org/swatplus/swatplus.editor)
* [QSWAT+ source code repository](https://bitbucket.org/ChrisWGeorge/qswatplus3)

## Run and Compile SWAT+ Editor

### Install Development Tools

* You may use any IDE of your choice, however [Visual Studio Code](https://code.visualstudio.com/) is used by the developer.
* Install [Python 3.7](https://www.python.org/)
* Install required Python packages. From command prompt, go to source code /api directory and run:

```text
pip install -r requirements.txt
```

* Install [Node.js](https://nodejs.org/en/)
* Install required Node.js packages. From command prompt, go to the root directory of the source code and run:

```text
npm install
```

### Run the Source Code

From a command prompt in the root directory \(terminal inside Visual Studio Code\)

```text
npm run dev
```

Open a second command prompt and run

```text
electron .
```

### Build the Source Code

First, use [PyInstaller](https://www.pyinstaller.org/) \(included in the Python packages during install\) to freeze the Python into executable files. This should be done from the /api directory in the source code. In Windows, run the supplied .bat file from a command prompt:

```text
pyinstaller_builds
```

The configurations for PyInstaller are in the swatplus\_api.spec and swatplus\_rest\_api.spec files. Modify these if compiling for Linux.

{% hint style="info" %}
Note: The Python will create 32 or 64-bit executables depending on the version of Python you have installed.
{% endhint %}

Next, build the Vue.js code. Open a command prompt and run:

```text
npm run build
```

Finally, package the code for distribution using [Electron Builder](https://www.electron.build/). Configuration is set in the package.json file. Results of the build will be placed in the /release/dist directory.

Create an installer:

```text
npm run dist
```

Or, build a portable executable:

```text
npm run dist-port
```

Or, pack the files into a directory:

```text
npm run pack
```

