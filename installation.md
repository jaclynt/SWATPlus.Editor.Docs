# Installation

## 1. Install QGIS 3

If you plan to use QSWAT+ to set up your watershed, please install QGIS 3 before installing SWAT+. It can be downloaded from the [QGIS download page](https://www.qgis.org/en/site/forusers/download.html), where you should select the **Long term release repository**, and the **64 bit standalone installer**. Version 3.16 is recommended. Use the default folder `C:\Program Files\QGIS 3.16` as the installation folder. See the [QSWAT+ manual](user/qswat+.md) for further instructions.

**Please note you must use QGIS version 3, not version 2.**

## 2. SWAT+ 2.0.3 Installer

This release includes **SWAT+ rev. 60.5.2**, **QSWAT+ 2.0.6**, and **SWAT+ Editor 2.0.3**. To install the SWAT+ model and interface components, please use an installer linked below for your operating system. The installer is for 64-bit machines. Administrator privileges are not required.

| Operating System | Link | Release Date | Version |
| :--- | :--- | :--- | :--- |
| Windows 64-bit | [Download \(111 MB\)](https://plus.swat.tamu.edu/downloads/swatplustools-installer-2.0.3.zip) | 6 Apr 2021 | 2.0.3 |
| \*Linux 64-bit | [Download \(194 MB\)](https://plus.swat.tamu.edu/downloads/swatplus-linux-installer-2.0.3.tgz) | 6 Apr 2021 | 2.0.3 |
| \*MacOS 64-bit | [Download \(262 MB\)](https://plus.swat.tamu.edu/downloads/swatplus-mac-installer-2.0.1.tgz) | 11 Mar 2021 | \*\*2.0.1 |

_\*For Linux and MacOS, the optional SSURGO/STATSGO soils and WGN databases should be downloaded from the_ [_SWAT+ SQLite Datasets_](installation.md#swat-sqlite-datasets) _section below as they are not included in the installers._

_\*\*Version 2.0.3 for MacOS is still being tested. Expected release this week._ 

{% page-ref page="release-notes.md" %}

Trouble loading the software after installation? Read through our troubleshooting guide.

{% page-ref page="get-help/troubleshooting.md" %}

## Individual Component Installation

If you need to install QSWAT+ or SWAT+ Editor individually, grab the latest release of their respective installers from their source code repository downloads page.

* [QSWAT+ Installers](https://bitbucket.org/ChrisWGeorge/qswatplus3/downloads/)
* [SWAT+ Editor Installers](https://bitbucket.org/swatplus/swatplus.editor/downloads/)

### SWAT+ Model \(Command Line Executable\)

The model itself is packaged with SWAT+ Editor and we recommend using the editor to modify your inputs and run the model. However, if you would like to download just the command line executable file, it is available below.

{% file src=".gitbook/assets/rev60.5.2\_64\_windows.zip" caption="Windows 64bit - SWAT+ rev. 60.5.2" %}

{% file src=".gitbook/assets/rev60.5.2\_64rel\_linux.zip" caption="Linux 64bit - SWAT+ rev. 60.5.2" %}

{% file src=".gitbook/assets/rev60.5.2\_64rel\_mac.zip" caption="MacOS 64bit - SWAT+ rev. 60.5.2" %}

## SWAT+ SQLite Datasets

On Windows we recommend using the SWAT+ Tools installer above for installing the SWAT+ datasets databases to their proper locations. However, for Linux and MacOS, or if you need to access these components individually, they are linked below:

* [SWAT+ datasets](https://bitbucket.org/swatplus/swatplus.editor/downloads/swatplus_datasets.sqlite)
* [SWAT+ global weather generator data](https://bitbucket.org/swatplus/swatplus.editor/downloads/swatplus_wgn.sqlite)
* [SWAT+ US SSURGO/STATSGO soil data](https://bitbucket.org/swatplus/swatplus.editor/downloads/swatplus_soils.sqlite)

These files should be placed in `SWATPlus/Databases`

