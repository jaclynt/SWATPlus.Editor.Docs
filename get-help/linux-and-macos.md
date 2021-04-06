---
description: >-
  The Linux release was tested on Ubuntu 20.04 LTS, and MacOS was tested on
  Catalina. Please let us know if you test on a different OS version or Linux
  distribution and have any issues.
---

# Linux and MacOS

## Installation

First install the latest LTR version of [QGIS](https://www.qgis.org/) from their downloads page. Please note that if you are using Ubuntu's software manager, it might have an old version, so please use the instructions from the QGIS website. 

After QGIS is installed, download the Linux or MacOS .tgz file from the [installation page](../installation.md) and extract it. From a terminal go to the extracted folder location and run either `./installforme.sh` or `./installforall.sh`.

Open QGIS and verify the SWAT+ plugin is installed. Visit our general troubleshooting page for help first.

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

