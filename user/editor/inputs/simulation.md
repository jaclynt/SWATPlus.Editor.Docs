# Simulation

## Time

Configure the number or years to run the simulation and time step. If you have observed weather data, make sure your simulation time falls within these dates.

| SWAT+ Input File | Database Table |
| :--- | :--- |
| time.sim | time\_sim |

### time\_sim

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">id</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">Auto-assigned identifier</td>
    </tr>
    <tr>
      <td style="text-align:left">day_start</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p>Beginning Julian day of simulation</p>
        <p>If zero, the model starts the simulation on January 1</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">yrc_start</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">Beginning year of simulation (e.g., 1980)</td>
    </tr>
    <tr>
      <td style="text-align:left">day_end</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p>Ending Julian day of simulation</p>
        <p>If zero, the model ends the simulation on December 31</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">yrc_end</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">Ending year of simulation (e.g., 1980)</td>
    </tr>
    <tr>
      <td style="text-align:left">step</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">Time steps in a day for rainfall, runoff and routing</td>
    </tr>
  </tbody>
</table>## Print

Configure the output files to print.

| SWAT+ Input File | Database Tables |
| :--- | :--- |
| print.prt | print\_prt |
|  | print\_prt\_object |

### print\_prt

| Field | Type | Description |
| :--- | :--- | :--- |
| id | int |  Auto-assigned identifier |
| nyskip | int |  Number of years to _not_ print output |
| day\_start | int | Beginning Julian day of simulation to start printing output files for daily printing only |
| yrc\_start | int | Beginning year of simulation to start printing output files |
| day\_end | int | Ending Julian day of simulation to stop printing output files for daily printing only |
| yrc\_end | int | Ending year of simulation to stop printing output files |
| interval | int | Daily print within the period \(e.g., interval=2 will print every other day\) |
| csvout | bool | Print .csv files in addition to text files |
| dbout | bool | Print database \(not currently active\) |
| cdfout | bool | Print netcdf \(not currently active\) |
| soilout | bool | Print soil nutrients carbon output file |
| mgtout | bool | Print management output file |
| hydcon | bool | Print hydrograph connect output file |
| fdcout | bool | Print flow duration curve output file |

### print\_prt\_object

Each row in print\_prt\_object represents an output file that can be print daily, monthly, yearly, and average annual output for each.

| Field | Type | Description |
| :--- | :--- | :--- |
| id | int |  Auto-assigned identifier |
| print\_prt\_id | int | ID of print\_prt row |
| name | text | Name of print object |
| daily | bool | Print daily output |
| monthly | bool | Print monthly output |
| yearly | bool | Print yearly output |
| avann | bool | Print average annual output |

{% hint style="info" %}
Daily printing of all files could cause very large output \(exceeding hard drive space\)
{% endhint %}

#### Print Object Descriptions

| Object Name | Description |
| :--- | :--- |
| basin\_wb | Water balance basin output variables |
| basin\_nb | Nutrient balance basin output variables  |
| basin\_ls | Losses basin output variables |
| basin\_pw | Plant weather basin output variables |
| basin\_aqu | Aquifer basin output variables  |
| basin\_res | Reservoir basin output file variables |
| basin\_cha | Channel basin output file variables |
| basin\_sd\_cha | CHAN DEG basin output file variables |
| basin\_psc | Point source basin output file variables |
| region\_wb | Water balance region output variables |
| region\_nb | Nutrient balance region output variables |
| region\_ls | Losses region output variables |
| region\_pw | Plant weather region output variables |
| region\_aqu | Aquifer region output variables |
| region\_res | Reservoir region output variables |
| region\_cha | Channel region output variables |
| region\_sd\_cha | SWAT DEG Channel region output variables |
| region\_psc | Point source region output variables |
| lsunit\_wb | Water balance routing unit output variables |
| lsunit\_nb | Nutrient balance routing unit output variables |
| lsunit\_ls | Losses routing unit output variables |
| lsunit\_pw | Plant weather routing unit output variables |
| hru\_wb | Water balance hru output variables |
| hru\_nb | Nutrient balance hru output variables |
| hru\_ls | Losses hru output variables |
| hru\_pw | Plant weather hru output variables |
| hru-lte\_wb | Water balance HRU-LTE output variables |
| hru-lte\_nb | Nutrient balance HRU-LTE output variables |
| hru-lte\_ls | Losses HRU-LTE output variables |
| hru-lte\_pw | Plant weather HRU-LTE output variables |
| channel | Channel output variables |
| channel\_sd | SWAT DEG \(lte\) channel output variables |
| aquifer | Aquifer output variables |
| reservoir | Reservoir output variables |
| recall | Recall output variables |
| hyd | Hydin output and hydout\_output variables |
| ru | Routing unit output variables |
| pest | Pesticide constituents outputs |

