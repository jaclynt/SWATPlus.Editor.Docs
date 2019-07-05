# Basin

General watershed attributes are defined in the basin input files: codes and parameters. These attributes control a diversity of physical processes at the watershed level. The interfaces will automatically set these parameters to the default or recommended values listed in the variable documentation. Users can use the default values or change them to better reflect what is happening in a given watershed. Variables governing bacteria or pesticide transport need to be initialized only if these processes are being modeled in the watershed. Even if nutrients are not being studied in a watershed, some attention must be paid to these variables because nutrient cycling impacts plant growth which in turn affects the hydrologic cycle.

## Codes

| SWAT+ Input File | Database Table |
| :--- | :--- |
| codes.bsn | codes\_bsn |

### codes\_bsn

| Field | Type | Description |
| :--- | :--- | :--- |
| pet\_file | text | Potential ET filename |
| wq\_file | text | Watershed stream water quality filename |
| pet | int | Potential ET method code |
| event | int | Event code |
| crack | int | Crack flow code |
| rtu\_wq | int | Subbasin water quality code |
| sed\_det | int | Max half-hour rainfall frac calc |
| rte\_cha | int | Water routing method |
| deg\_cha | int | Channel degradation code |
| wq\_cha | int | Stream water quality code |
| rte\_pest | int | Redefined to the sequence number of pest in NPNO\(:\) to be routed through the watershed |
| cn | int | CN method flag |
| c\_fact | int | C-factor |
| carbon | int | Carbon code |
| baseflo | int | Baseflow distribution factor during the day for subdaily runs |
| uhyd | int | Unit hydrograph method |
| sed\_cha | int | Instream sediment model |
| tiledrain | int | Tile drainage EQ code |
| wtable | int | Water table depth algorithms code |
| soil\_p | int | Soil phosphorus model |
| abstr\_init | int | Initial abstraction on impervious cover |
| atmo\_dep | text | Atmospheric deposition code |
| stor\_max | int | Max depressional storage selection code |
| headwater | int | Headwater code |

## Parameters

| SWAT+ Input File | Database Table |
| :--- | :--- |
| parameters.bsn | parameters\_bsn |

### parameters\_bsn

| Field | Type | Description | Units | Default | Range |
| :--- | :--- | :--- | :--- | :--- | :--- |
| lai\_noevap | real | Leaf area index at which no evaporation occurs from water surface |  | 3 | 0-10 |
| sw\_init | real | Initial soil water storage expressed as a fraction of field capacity water content |  | 0 | 0-1 |
| surq\_lag | real | Surface runoff lag coefficient |  | 4 | 1-24 |
| adj\_pkrt | real | Peak rate adjustment factor for sediment routing in the subbasin \(tributary channels\) |  | 1 | 0.5-2 |
| adj\_pkrt\_sed | real | Peak rate adjustment factor for sediment routing in the main channel |  | 1 | 0-2 |
| lin\_sed | real | Linear parameter for calculating the maximum amount of sediment that can be reentrained during channel sediment routing |  | 0.0001 | 0.0001-0.01 |
| exp\_sed | real | Exponent parameter for calculating sediment reentrained in channel sediment routing |  | 1 | 1-1.5 |
| orgn\_min | real | Rate factor for humus mineralization of active organic nutrients \(N and P\) |  | 0.0003 | 0.001-0.003 |
| n\_uptake | real | Nitrogen uptake distribution parameter |  | 20 | 0-100 |
| p\_uptake | real | Phosphorus uptake distribution parameter |  | 20 | 0-100 |
| n\_perc | real | Nitrate percolation coefficient |  | 0.2 | 0-1 |
| p\_perc | real | Phosphorus percolation coefficient | 10 m^3/M | 10 | 10-17.5 |
| p\_soil | real | Phosphorus soil partitioning coefficient | m^3/Mg | 175 | 100-200 |
| p\_avail | real | Phosphorus availability index |  | 0.4 | 0.01-0.7 |
| rsd\_decomp | real | Residue decomposition coefficient |  | 0.05 | 0.02-0.1 |
| pest\_perc | real | Pesticide percolation coefficient |  | 0.5 | 0-1 |
| msk\_co1 | real | Calibration coefficient to control impact of the storage time constant for the reach at bankfull depth |  | 0.75 | 0-10 |
| msk\_co2 | real | Calibration coefficient used to control impact of the storage time constant for low flow \(where low flow is when river is at 0.1 bankfull depth\) upon the km value calculated for the reach |  | 0.25 | 0-10 |
| msk\_x | real | Weighting factor control relative importance of inflow rate and outflow rate in determining storage on reach |  | 0.2 | 0-0.3 |
| trans\_loss | real | Fraction of transmission losses from main channel that enter deep aquifer |  | 0 | 0-1 |
| evap\_adj | real | Reach evaporation adjustment factor |  | 0.6 | 0.5-1 |
| cn\_co | real | Currently not being used |  |  |  |
| denit\_exp | real | Denitrification exponential rate coefficient |  | 1.4 | 0-3 |
| denit\_frac | real | Denitrification threshold water content |  | 1.3 | 0-1 |
| man\_bact | real | Fraction of manure applied to land areas that has active colony forming units |  | 0.15 | 0-1 |
| adj\_uhyd | real | Adjustment factor for subdaily unit hydrograph basetime |  | 0 | 0-1 |
| cn\_froz | real | Parameter for frozen soil adjustment on infiltration/runoff |  | 0.000862 | 0-0 |
| dorm\_hr | real | Time threshold used to define dormancy | hrs | 0 | 0-24 |
| s\_max | real | Currently not being used |  |  |  |
| n\_fix | real | Nitrogen fixation coefficient |  | 0.5 | 0-1 |
| n\_fix\_max | real | Maximum daily-n fixation | kg/ha | 20 | 1-20 |
| rsd\_decay | real | Minimum daily residue decay |  | 0.01 | 0-0.05 |
| rsd\_cover | real | Residue cover factor for computing fraction of cover |  | 0.3 | 0.1-0.5 |
| vel\_crit | real | Critical velocity |  | 5 | 0-10 |
| res\_sed | real | Reservoir sediment settling coefficient |  | 0.184 | 0.09-0.27 |
| uhyd\_alpha | real | Alpha coefficient for gamma function unit hydrograph |  | 5 | 0.5-10 |
| splash | real | Splash erosion coefficient |  | 1 | 0.9-3.1 |
| rill | real | Rill erosion coefficient |  | 0.7 | 0.5-2 |
| surq\_exp | real | Exponential coefficient for overland flow |  | 1.2 | 1-3 |
| cov\_mgt | real | Scaling parameter for cover and management factor for overland flow erosion |  | 0.03 | 0.001-0.45 |
| cha\_d50 | real | Median particle diameter of main channel | mm | 50 | 10-100 |
| cha\_part\_sd | real | Geometric standard deviation of particle size |  | 1.57 | 1-5 |
| adj\_cn | real | Currently not being used |  |  |  |
| igen | int | Random generator code 0 = use default number; 1 = generate new numbers in every simulation |  | 0 | 0-1 |

