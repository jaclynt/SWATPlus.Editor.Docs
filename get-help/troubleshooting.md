---
description: >-
  Before contacting support, please ensure you have the newest version of the
  tools installed. Check the common situations below, and if your error is not
  covered, consult the appropriate user group.
---

# Troubleshooting

## I received an error setting up my watershed in QSWAT+

Make sure you have [installed](../installation.md) the most recent version of QSWAT+ and followed the [manual's installation instructions](../user/qswat+.md) closely.

If you received an error during steps 1, 2, or 4 of the QSWAT+ interface, please consult the [QSWAT+ user group](https://groups.google.com/d/forum/qswatplus). Check existing questions to see if anyone else had the same problem. If not, please post your error and be as descriptive as possible about what you were doing when you received the error message.

## I received an error in SWAT+ Editor

SWAT+ Editor is most often accessed during step 3 of the QSWAT+ plugin. It may also be launched on its own. Make sure you have [installed](../installation.md) the most recent version of SWAT+ Editor.

If your error is not covered by the solutions below, please consult the [SWAT+ Editor user group](https://groups.google.com/d/forum/swatplus-editor).

### "Unable to get project information from database."

If you receive this message when you first launch your project in the editor, it is a sign the editor did not load its services correctly. 

Click the question mark icon in the lower left corner to open the help page. Scroll to the bottom and looking for the "Troubleshooting" section. If you see a message stating "Unable to connect to SWAT+ API", please try the following steps before contacting support:

Open a command prompt window. Make sure you are in the drive where you installed SWAT+. Browse to the location below, then run the swatplus\_rest\_api.exe file.

```text
> cd C:\SWAT\SWATPlus\SWATPlusEditor\resources\app.asar.unpacked\api_dist
> swatplus_rest_api.exe
```

If it is working properly, you should receive something similar to the following:

```text
* Serving Flask app "swatplus_rest_api" (lazy loading)
* Environment: production
WARNING: Do not use the development server in a production environment.
Use a production WSGI server instead.
* Debug mode: off
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

If this is what you received, please simply close SWAT+ Editor and try launching it again. 

If you get no message on the screen at all, it might be a permission or error related to your computer settings. Try installing to another location on your machine, such as another hard drive, or even install to a flash drive. If this still does not work, try another machine.

If you still cannot get it to open, you may need to try the Python version of the editor. You will need to install [Python version 3.x](https://www.python.org/) on your machine first. Make note of your Python PATH variable \(typically `python` on Windows or `python3` on Linux/MacOS\). [Contact the developer](mailto:eco.web@tamu.edu) for a custom Python installer of the editor.

After install, go to where you installed the editor and open the `appsettings.json` file located in the `resources/app.asar.unpacked` directory. Set your python PATH variable in the appropriate section of the file.

### I received an error importing GIS data or updating my project

Please post the error message to the [SWAT+ Editor user group](https://groups.google.com/d/forum/swatplus-editor) **AND include your project files**. This error is likely project specific and we cannot help you without seeing your project files.

### Other SWAT+ Editor errors

If you receive any other error messages from SWAT+ Editor, from its menu go to View -&gt; Toggle Developer Tools. In the windows that pops open, toggle the Console tab and take a screenshot or copy an errors received and post to the [SWAT+ Editor user group](https://groups.google.com/d/forum/swatplus-editor).

## I received an error running the SWAT+ model

If you received an error running the model, first make sure you have run it in debug mode and checked the detailed error received. If you are not able to make sense of the source of the model error, please post to the [SWAT+ model user group](https://groups.google.com/d/forum/swatplus) **AND include your project files**. This error is likely project specific and we cannot help you without seeing your project files.

