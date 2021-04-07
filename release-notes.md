---
description: SWAT+ Editor 2.0 with QSWAT+ 2.0 and SWAT+ revision 60.5.2
---

# Release Notes

## SWAT+ revision 60.5.2

Download the revision notes for the model below.

{% file src=".gitbook/assets/swatplus-rev-notes-60-60.5.2 \(1\).pdf" %}

## QSWAT+ revision 2.0

### Revision 2.0.6

* Lake shapefiles can be used to define reservoirs, ponds, wetlands and playas.
* Landuse WETW has been added. Existing projects will need to load `plantWithWETW.csv` using the plant pull-down menu on the CreateHRUs form. The file is located in your `SWATPlus/Databases` directory.

## SWAT+ Editor revision 2.0

### Revision 2.0.3

* Minor update to add WETW and WETM land uses to swatplus\_datasets.sqlite. WETW is for playas and WETM is not currently active. This requires you to update to QSWAT+ version 2.0.6.
* Improved write time for .con \(connect\) files. This mostly affects larger projects or grid models.
* Fix default location of WGN database for Linux/Mac.

### Revision 2.0.1

* Minor update to fix write time of `rout_unit.def` and `ls_unit.def` for larger projects with many HRUs.

### Revision 2.0.0

We recommend using new projects created in the new QSWAT+ 2.0.x with version 2 of the editor. However, if this is not feasible, an upgrade function is available when you load your older projects in the editor. If you are using the land use management \(lum.dtl\) default decision tables provided in previous versions of the editor, we recommend manually updating them. The old ones have an error causing crops not to be planted. Download instructions below:

{% file src=".gitbook/assets/swatplus-editor-2.0.0-dtable-update-instructions.txt" caption="Decision Table Update Instructions" %}

#### Editor feature updates:

* New feature: save and load scenarios. After running the model, make a copy of your inputs and outputs. Any changes made after saving will not affect the saved scenario. Load the scenario back to the editor anytime from the project setup screen.
* New feature: SWAT+ Check. Features from SWAT Check have been brought in for SWAT+ and built in directly to the editor. This is still a work in progress.
* New feature: constituents section available under initialization data editing section. Pesticides and pathogens are available to be configured.
* User interface redesigned and enhanced:
  * Project setup screen simplified and project information shown here after project is loaded.
  * SWAT+ lte \(simplified model with just channels and HRUs\) option now available for all projects when importing GIS.
  * Connections editing screens simplified to combine connect file inputs and properties into one.
  * Bulk editing mode now available when clicking edit on any item and using the pull down arrow on the right of the Save Changes button. Filtering available by subbasin, landuse, and HRU if applicable.
  * Table views may now be filtered.
  * Copy feature added to most sections \(click on edit to an item\). Does not apply to connection objects.
* Import from GIS functionality updated. Aquifers now read from QSWAT+ routing tables, speeding up import. Users are recommended to install the most recent QSWAT+ 2.0.x for this feature.
* Default project data updated:
  * Set values for hydrology.hyd variables perco, cn3\_swf, and latq\_co based on soil hyd. group and HRU slope
* Project database structure and dataset updates to match revisions in SWAT+ rev. 60.5.x \(see model revision notes linked in section above\).

