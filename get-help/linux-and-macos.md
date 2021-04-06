---
description: >-
  The Linux release was tested on Ubuntu 20.04 LTS, and MacOS was tested on
  Catalina. Please let us know if you test on a different OS version or Linux
  distribution and have any issues.
---

# Linux and MacOS

## Installation

First install the latest LTR version of [QGIS](https://www.qgis.org/) from their downloads page. Please note that if you are using Ubuntu's software manager, it might have an old version, so please use the instructions from the QGIS website. 

Next, install openmpi using brew. From a terminal, run: `brew install openmpi`

After QGIS and openmpi are installed, download the Linux or MacOS .tgz file from the [installation page](../installation.md) and extract it. From a terminal go to the extracted folder location and run either `sudo ./installforme.sh` or `./installforall.sh`. Please note that if using the install "for all", the plugin may not show up in QGIS for standard users due to QGIS requiring third-party plugins in the user's home directory. In this case, please use install "for me" instead.

For Linux and MacOS, the optional SSURGO/STATSGO soils and WGN databases should be downloaded from the [SWAT+ SQLite Datasets](../installation.md#swat-sqlite-datasets) section of the installation page, as they are not included in the installers.

Open QGIS and verify the SWAT+ plugin is installed. If it is not, visit our general [troubleshooting page](troubleshooting.md) for help first.

## Known Issues

### SWAT+ Editor on Debian 10: SUID Sandbox

You may receive an error trying to launch SWAT+ Editor on Debian or other non-Ubuntu Linux distributions:

> The SUID sandbox helper binary was found, but it is not configured correctly.

 If so, please try the following.

Find your installation location. If you did install for me, it is:

```text
cd ~/.local/share/SWATPlus/SWATPlusEditor
```

If you selected install for all, it is:

```text
cd /usr/local/share/SWATPlus/SWATPlusEditor
```

From the install directory, type the following commands:

```text
sudo chown root chrome-sandbox
sudo chmod 4755 chrome-sandbox
```

You should now be able to launch the editor without error.

