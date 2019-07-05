# Recall \(Point Source/Inlet\)

Recall objects are used for connecting point source or inlet data to your watershed. If you added point source in QSWAT+, when you import your project into SWAT+ Editor it will be connected via the recall section.

By default, constant data with all zero values during the default simulation period is added. To add your own recall data, click the recall item in the edit menu under connections. Click the item name under the rec column in the connection object table, or click the data item under recall in the edit menu on the left.

![The red boxes highlight where to click to access recall data](../../../../.gitbook/assets/recall_table_browse.png)

## Constant Data

By default, your recall data is imported as constant. To insert your values, you can edit each item individually by clicking the edit button and manually entering each value. Alternatively, you may upload a CSV of your data.

From the recall data section, click the import/export button in the top right corner.

![](../../../../.gitbook/assets/recall_constant1.PNG)

Export is selected by default. Choose a file name, and click the export CSV file button to get a template for your data.

![Example template file after exporting](../../../../.gitbook/assets/recall_constant_data.PNG)

Edit the CSV as needed, save, and then go back to the editor and click the import/output button again. This time toggle the import button. Choose your modified CSV file and click the import CSV data button. Your updated values will appear in the table.

## Time Series Data

By default recall data is imported as constant, however this can be changed by clicking the edit button next to a row in the recall data table. Select the new time step for your data: daily, monthly, or yearly. Click the save changes button. Next, click the import/export button that appears on the form.

Export is selected by default. Choose a file name, and click the export CSV file button.

![](../../../../.gitbook/assets/recall_export.PNG)

Open the file after it is exported to see the template for your data. Modify your data as needed matching the time step you selected previously. Be sure the years match your [simulation run time](../simulation.md). In a yearly time step, t\_step equals 1 through number of years. For monthly data, t\_step equals the number of the month, and for daily it is the number of the day of the year.

To import your data, click the import/export data button again and this time click to toggle import. Choose your file and click import CSV file. Your new data will appear in the table.

## Recall Table Definitions

| SWAT+ Input File | Database Table |
| :--- | :--- |
| recall.rec | recall\_rec |

| Field | Type | Description |
| :--- | :--- | :--- |
| id | int | Auto-assigned identifier |
| name | text | Name of recall object |
| rec\_typ | int | Time step for recall object \(1-daily, 2-monthly, 3-yearly\) |

Each record in recall\_rec will have a data file named {name}.rec. All of this data is stored in a single recall\_dat table in the database.

| SWAT+ Input File | Database Table |
| :--- | :--- |
| {name}.rec | recall\_dat |

| Field | Type | Description | Units |
| :--- | :--- | :--- | :--- |
| yr | int | Year |  |
| t\_step | int | Timestep |  |
| flo | real | Volume of water | m^3 |
| sed | real | Sediment | metric ton |
| ptl\_n | real | Organic nitrogen | kg N |
| ptl\_p | real | Organic phosphorus | kg P |
| no3\_n | real | Nitrate | kg N |
| sol\_p | real | Mineral \(soluble P\) | kg P |
| chla | real | Chlorophyll-a | kg |
| nh3\_n | real | Ammonia | kg N |
| no2\_n | real | Nitrogen dioxide | kg N |
| cbn\_bod | real | Carbonaceous biological oxygen demand | kg |
| oxy | real | Dissolved oxygen | kg |
| sand | real | Detached sand |  |
| silt | real | Detached silt |  |
| clay | real | Detached clay |  |
| sm\_agg | real | Detached small ag |  |
| lg\_agg | real | Detached large ag |  |
| gravel | real | Gravel |  |
| tmp | real | Temperature | deg c |

