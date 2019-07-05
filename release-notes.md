---
description: SWAT+ Editor 1.2.0 with QSWAT+ 1.2.2 and SWAT+ revision 59.3
---

# Release Notes

## SWAT+ revision 59.3

Download the revision notes for the model below.

{% file src=".gitbook/assets/swatplus-rev-notes-55.1-59.3.pdf" caption="SWAT+ Revision Notes 55.1-59.3" %}

## QSWAT+ revision 1.2.2

* Environmental flows have been added.
* Revised treatment of ponds and reservoirs.

## SWAT+ Editor revision 1.2.0

* Compatible with SWAT+ rev. 59.3
* Fixes default routing in rout\_unit\_con for upland to floodplain surface runoff. Use fraction of area of upland routing unit surface runoff goes to channel/reservoir, the remaining goes to floodplain \(see Bieger et al. JAWRA 2019\). New projects only, existing projects should try re-import from GIS option. 
* Change aquifer creation. Previously created one aquifer per channel. Changed to two per subbasin \(upland/floodplain\), and add a deep aquifer for each outlet.
* Fixes default principal/emergency area and volume of reservoirs. Note: new projects / re-import GIS data only. Existing projects should update values manually as needed. New defaults are described below:
  * Principal spillway area \(`area_ps`\) is set from GIS data
  * Emergency spillway area is set to `area_ps * 1.15`
  * Principal spillway volume is set to `area_ps * 10`
  * Emergency spillway volume is set to `area_es * 10`
* Un-managed ponds are now retained as HRUs in QSWAT+. Imported to the editor as HRUs with wetlands inputs \(wetlands\_wet and hydrology\_wet\).
* Update output database tables to include revisions from model rev. 59.3: channel and channel morph, reservoir, and wetlands columns.
* Project update function available for the following data changes related to model rev. 59.1-3:
  * Update cal\_parm\_cal abs\_max=10 and units=m for flo\_min and revap\_min. Add dep\_bot.
  * Update aquifer\_aqu default values for gw\_flo=0.05, dep\_wt=10, flo\_min=5, revap\_min=3.
  * In plant\_ini\_item, yrs\_init changed to fraction \(change values to 1 where previously 15\), and biomass increased for some plants. Lc\_status changed to yes for past and barr plants.
  * Update codes\_bsn default values for pet=1, rtu\_wq=1, wq\_cha=1
* User interface improvements:
  * Add csv import for weather generator data.
  * All related table search boxes return all possible results underneath matches to typed text.
  * Add automatic database rollback when user gets an error importing GIS or updating project.
* Bug fixes:
  * Fixed bug when updating project from 1.0.0, a variable was not declared.
  * Fixed bug where weather stations were created but not always assigned weather data file if one exists.
  * Fixed bug when trying to import weather data located on another hard drive.
  * Fixed bug where swatplus\_rest\_api.exe wasn't terminating correctly when exiting the editor.

## SWAT+ Editor revision 1.1.1

* Fixes bug when importing GIS data into plant communities not in the datasets database
* Print section usability update
* Update automatic project database backups so multiple failed import/upgrade attempts don't overwrite the original

## SWAT+ Editor revision 1.1.0 changes from 1.0.0

The remainder of this page outlines what changed from the initial release of the editor in fall 2018 to version 1.1.0 released in spring 2019. If you never used version 1.0.0, you can skip the remainder of this page.

* Upgrade function available for projects made with version 1.0.0.
* Compatible with SWAT+ rev. 59.
* Re-designed project setup page. If importing GIS, allow SWAT+ lte option for projects without point source or reservoir data.
* Channels now default to using the channel-lte structure \(as per SWAT+ rev. 58\). **Please note** that this means your channel input files are different \(chandeg.con\) and the channel output will be in channel\_sd tables.
* New management schedule and decision table defaults determined by your HRU's plant type in plants.plt. It will use an automatic schedule based on corn \(warm\) or wheat \(cold\) plants. See the [land use management documentation](user/editor/inputs/land-use-management.md) for more information.
* New editor sections for: basin parameters, connections--export coefficients, recall, delivery ratio, landscape unit regions, land use management, calibration, initialization data, soils, databases, and structural.
* Added export/import to and from CSV files for most sections.
* Other miscellaneous usability improvements.
* Automatic updating for more rapid bug fixes and releases.

## Notable limitations

* Constituents \(pesticides, pathogens, heavy metals, salts\) are not fully available through the editor yet.

## Project database changes

* d\_table\_dtl - add column file\_name, repopulate table based on 4 new decision table files: lum.dtl, res\_rel.dtl, scen\_lu.dtl, flo\_con.dtl
* d\_table\_dtl\_act - add column const2
* d\_table\_dtl\_act - rename columns application-&gt;fp and type-&gt;option
* recall\_dat - drop columns sol\_pest, srb\_pest, p\_bact, lp\_bact, metl1, metl2, metl3
* exco\_om\_exc - drop columns sol\_pest, srb\_pest, p\_bact, lp\_bact, metl1, metl2, metl3
* exco\_om\_exc - rename columns ptl\_n-&gt;orgn, ptl\_p-&gt;sedp, no3\_n-&gt;no3, sol\_p-&gt;solp, nh3\_n-&gt;nh3, no2\_n-&gt;no2, bod-&gt;cbod, oxy-&gt;dox, sm\_agg-&gt;sag, lg\_agg-&gt;lg\_agg
* aquifer\_aqu - drop columns gw\_dp, gw\_ht, delay
* aquifer\_aqu - add columns dep\_bot \(default value 10\), dep\_wt \(default value 5\), bf\_max \(default 1\)
* aquifer\_aqu - change spec\_yld value from 0 to 0.05
* aquifer\_aqu - add column init\_id referencing initial\_aqu
* fertilizer\_frt - drop columns p\_bact, lp\_bact, sol\_bact
* fertilizer\_frt - add column pathogens
* hydrology\_hyd - drop column dp\_imp
* pesticide\_cha - rename column sed\_conc-&gt;pst\_solub
* channel\_lte\_cha - rename table to hyd\_sed\_lte\_cha
* hru\_data\_hru - drop column soil\_nut\_id
* hru\_data\_hru - add column soil\_plant\_init\_id
* cal\_parms\_cal - change column type of units from number to text
* initial\_cha - drop existing columns, add new columns: org\_min\_id, pest\_id, path\_id, hmet\_id, salt\_id \(foreign keys to new tables in init\)
* initial\_res - drop existing columns, add new columns: org\_min\_id, pest\_id, path\_id, hmet\_id, salt\_id \(foreign keys to new tables in init\)
* reservoir\_res - drop column pest\_id
* wetland\_wet - drop column pest\_id
* sediment\_res - add columns carbon and bd
* plants\_plt - drop column plnt\_hu and add column days\_mat
* plant\_ini - add column rot\_yr\_ini
* codes\_bsn - change column type of atmo\_dep from number to text
* rout\_unit\_ele - drop column hyd\_typ, change foreign key of rtu\_id from rout\_unit\_rtu to rout\_unit\_con
* constituents\_cs - drop and re-create table
* dr\_om\_del, dr\_pest\_del, dr\_path\_del, dr\_hmet\_del, dr\_salt\_del, delratio\_del - drop and re-create tables
* calibration\_cal - drop and re-create table
* pesticide\_pst - drop and re-create table
* codes\_cal - rename table codes\_sft, replace columns landscape and hyd with hyd\_hru and hyd\_hrulte
* ls\_parms\_cal - rename table wb\_parms\_sft
* ch\_parms\_cal - rename table ch\_sed\_parms\_sft
* pl\_parms\_cal - rename table plant\_parms\_sft

### Drop tables

* pest\_soil\_ini
* pest\_soil\_ini\_item
* path\_soil\_ini
* hmet\_soil\_ini
* salt\_soil\_ini

### Add new tables

* soil\_plant\_ini
* om\_water\_ini
* pest\_hru\_ini
* pest\_hru\_ini\_item
* pest\_water\_ini
* path\_hru\_ini
* path\_water\_ini
* hmet\_hru\_ini
* hmet\_water\_ini
* salt\_hru\_ini
* salt\_water\_ini
* channel\_lte\_cha \(new structure; not the same as old table renamed to hyd\_sed\_lte\_cha\)
* initial\_aqu \(same structure as initial\_cha\)
* calibration\_cal\_cond 
* calibration\_cal\_elem
* water\_balance\_sft and water\_balance\_sft\_item \(replace ls\_regions\_cal\)
* ch\_sed\_budget\_sft and ch\_sed\_budget\_sft\_item \(replace ch\_orders\_cal\)
* plant\_gro\_sft and plant\_gro\_sft\_item \(replace pl\_regions\_cal\)

## SWAT+ Datasets database changes

* d\_table\_dtl - add column file\_name, repopulate table based on 4 new decision table files: lum.dtl, res\_rel.dtl, scen\_lu.dtl, flo\_con.dtl
* d\_table\_dtl\_act - add column const2
* d\_table\_dtl\_act - rename columns application-&gt;fp and type-&gt;option
* plants\_plt - drop column plnt\_hu and add column days\_mat
* Replace all decision table data
* Replace all plants\_plt data
* Replace all fertilizer\_frt data
* Replace all pesticide\_pst data \(also new table structure\)
* Replace all var\_range data
* Add new tables: version, tropical\_bounds

## Output database changes

* New naming structure based on SWAT+ rev. 56

