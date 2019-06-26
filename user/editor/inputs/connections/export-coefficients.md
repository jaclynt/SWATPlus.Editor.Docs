# Export Coefficients

{% hint style="warning" %}
Documentation for this section is not available yet. For now, please refer to the SWAT+ input/output documentation PDF for parameter definitions.
{% endhint %}

### Special note about using export coefficients with constant point source/inlet data

In SWAT+, constant values for point sources and inlets are stored in the export coefficients properties file, exco.exc, while time series data are stored entirely in the recall section.

However, in the editor, we keep both constant and time series point sources and inlets in the **recall section**. When you write input files, the editor will write to the exco.exc and exco\_om.exc files appropriately.

