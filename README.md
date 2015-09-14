# Short-term planning of cogeneration systems via MINLP

This repository contains the instances used in the article "[Short-term planning of cogeneration energy systems via MINLP]()" by [Leonardo Taccari](), [Edoardo Amaldi](http://home.deib.polimi.it/amaldi/), [Aldo Bischi]() and [Emanuele Martelli](http://www.energia.polimi.it/dipartimento/scheda_persona.php?id=242), 
to be published as an invited chapter in "Advances and Trends in Optimization with Engineering Applications. MOS-SIAM series, SIAM, Philadelphia, 2015".


If you use these instances, please consider citing the following reference:

> L. Taccari, E. Amaldi, A. Bischi, E. Martelli, "Short-term planning of cogeneration energy systems via MINLP", in T. Terlaky, M. Anjos and S. Ahmed (Eds.), *Advances and Trends in Optimization with Engineering Applications*. MOS-SIAM Series on Optimization, SIAM, Philadelphia, 2015.


### Data format
In the folder `instances`, we include the instances used in the article in `.nl` (AMPL binary format) and GAMS format.   

We also provide the raw data as plain text files: the `data` directory contains two subfolders, corresponding to two scenarios. Each scenario includes a set of heat and/or power units, that can be combined in different configurations. 
Each unit corresponds to a different file.
To define an instance of the problem, additional parameters must be specified: in particular, power/heat demand profiles, market prices for electrical power, temperature, and storage-related parameters. 
For scenario 1, we provide one such example (instance `1a` in the article), while, for the scenario 2, we provide four files (corresponding to instances `2a`, `2b`, `2c` and `2d`) with different power/heat demand profiles.

##Description

### Scenario 1

The first scenario is a micro-cogeneration system designed to provide thermal power, refrigeration power and electricity to a 2,000 m<sup>2</sup> building. 
More in detail, the building has the following power requirements: high-temperature thermal power (hot water above 60°C) for domestic hot water; 
low temperature thermal power (hot water 35-45°C) for heating; 
refrigeration power for air conditioning during summer period; electric power.
The cogeneration system is made of the following units:
+  a Solid Oxide Fuel Cell (SOFC) using natural gas to cogenerate up to 30kW and 15kW of, respectively, electric and thermal power; 
+  a Heat Pump (HP) using electric power to generate low temperature heat by "pumping"  heat from ambient temperature up to 35-45°C. It generates about 130kW at nominal conditions, but it is very sensitive to ambient temperature.
+  an Auxiliary Boiler (AB) burning natural gas to generate up to 100kW of high-temperature heat;
+  a thermal storage system to store up to 100kWh of high-temperature heat energy.

The auxiliary boiler is included in the system mainly as a backup and it is capable to fulfill the requirement peaks of both high and low temperature heat. 

### Scenario 2
The second scenario is a large scale cogeneration system providing heat to a district heating network. 
The requirement is thermal power at one level of temperature, about 90°C, 
while the whole electricity production is sold to the electric grid.
The cogeneration system includes one or more of the following units (we report nominal values at an ambient temperature of 15°C):
+ Gas Turbines (GT) with heat recovery, burning natural gas to generate up to about 10MW of heat and 5.5MW of electricity; 
+ Gas Turbines (GT-2) with supplementary firing and heat recovery, burning natural gas to generate up to about 40MW of heat and 11MW of electricity;
+ Natural Gas Combined Cycles (NGCC) with a bottoming back-pressure steam turbine, burning natural gas to generate up to 30MW of heat and 45MW of electricity; 
+ Natural Gas Combined Cycles (NGCC-2) with a bottoming extraction-type steam turbine, burning natural gas to generate up to about 70MW of heat and 30MW of electricity; 
+ Auxiliary Boilers (AB) burning natural gas to generate up to about 40MW of heat; 
+ a thermal storage system to store up to 50MWh of high-temperature heat energy.

In this case, the thermal power requirements are fulfilled by well established CHP units, like gas turbines and combined cycles, with the help of auxiliary boilers.
This scenario includes cogeneration units with two degrees of freedom,
namely, gas turbines (GT-2) with post-firing injection, and combined cycles with extraction condensing steam turbine (NGCC-2).
In GT-2, it is possible to burn supplementary fuel to increase the amount of heat that can be recovered from the exhaust gases. 
In NGCC-2, the amount of cogenerated heat and electric power is a function of the consumed fuel and the opening of a steam extraction valve.
Opening the valve reduces the electric power efficiency and increases the amount of recovered heat, 
while closing the valve drives heat production to 0, but provides larger electric output.
