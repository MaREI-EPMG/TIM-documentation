Industry sector 
=======================

Overview
--------

The industry sector in the TIMES Ireland Model (TIM) represents the energy consumption and associated emissions from Ireland's industrial activities. The sector is structured based on data from the National Heat Study by SEAI, which provides detailed breakdowns of industrial energy demand by subsector and end-use.

.. figure:: figures/industry.drawio.svg
    :scale: 80%
    :align: center
    :alt: Structure of the industry sector

Subsectors
----------

The industry sector in TIM is disaggregated into the following key subsectors:

- **Food, Beverages and Tobacco**: One of Ireland's largest industrial energy consumers, including dairy processing, meat processing, brewing, and food manufacturing.
- **Chemicals and Pharmaceuticals**: A significant contributor to industrial output and energy demand, including pharmaceutical manufacturing and chemical production.
- **Cement and Lime**: Energy-intensive processes requiring high-temperature heat for clinker production.
- **Non-metallic Minerals**: Includes glass, ceramics, and other mineral product manufacturing.
- **Basic metals**: Covers metal production, fabrication, and machinery manufacturing.
- **Paper, Print and Wood**: Includes pulp and paper production, printing, and wood processing industries.
- **Other Industry**: Residual industrial activities not captured in the above categories.

Energy Demands
--------------

Industrial energy demands in TIM are categorized by temperature level and end-use:

- **Low-temperature heat (<100°C)**: Used for processes such as drying, washing, and space heating.
- **Medium-temperature heat (100-400°C)**: Applied in processes like distillation, pasteurization, and some chemical reactions.
- **High-temperature heat (>400°C)**: Required for processes such as cement kilns, glass melting, and metal smelting.
- **Electricity for motors, drives and for other uses**: All electricity use currently reported here.

Decarbonization Technologies
----------------------------

TIM includes a range of technology options for decarbonizing the industry sector:

- **Electrification**: Electric boilers, heat pumps (for low and medium temperature applications), and electric furnaces.
- **Hydrogen**: Green hydrogen for high-temperature processes. Possibility to use as a feedstock in chemical production are not included yet.
- **Biomass**: Biomass boilers and combined heat and power (CHP) systems using sustainable biomass resources.
- **Carbon Capture and Storage (CCS)**: Applied to process related emissions in cement production.


Calibration
-----------

The following table shows the sectoral calibration of the industry sector, aligning model outputs with historical energy consumption data.

.. csv-table::
   :file: tables/industry.csv
   :widths: 50, 45, 45
   :header-rows: 1

Data Sources
------------

The primary data sources for the industry sector include:

- SEAI National Heat Study
- CSO Energy Balance statistics
- EPA emissions data
- Industry-specific studies and reports
