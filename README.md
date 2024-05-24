## Data Transformation with MS Excel Power Query
The goal of this data transformation is to standardize all water usage units to liters (a single unit) for analysis.

## Data Collection:
Data is collected from various factories, including information on their water usage from different sources.
Each factory used different units to measure their water usage, such as cubic meters (m³), gallons (gal), CCF (hundred cubic feet), and liters.

## Benefits:
Instead of MS Excel formulas, Power Query is used for data transformation.
Wth this data transformation:
- file size is reduced
- accidental edits to the code/formulas is avoided.

## Methodology
- A conversion table with all the water source unit is created
- Load both conversion table and factory raw data to Power Query
- New columns of water data in liters are created for each source

```bash
# Example:
    #"Added Custom" = Table.AddColumn(#"Changed Type", "watersource 1 (liters)", each ConversionRate{[#"Original Unit"=[watersourceunit1]]}?[Convert to Universal Unit]?*[watersource1]),
    #"Added Custom1" = Table.AddColumn(#"Added Custom", "watersource 2 (liters)", each ConversionRate{[#"Original Unit"=[watersourceunit2]]}?[Convert to Universal Unit]?*[watersource2]),
    #"Added Custom2" = Table.AddColumn(#"Added Custom1", "watersource 3 (liters)", each ConversionRate{[#"Original Unit"=[watersourceunit3]]}?[Convert to Universal Unit]?*[watersource3]),
    #"Added Custom3" = Table.AddColumn(#"Added Custom2", "watersource 4 (liters)", each ConversionRate{[#"Original Unit"=[watersourceunit4]]}?[Convert to Universal Unit]?*[watersource4]),
    #"Added Custom4" = Table.AddColumn(#"Added Custom3", "watersource 5 (liters)", each ConversionRate{[#"Original Unit"=[watersourceunit5]]}?[Convert to Universal Unit]?*[watersource5])

```



