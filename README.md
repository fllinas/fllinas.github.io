# Energy Analyst Portfolio
**Fabrizio Llinás Biava**

## Project 1: 
Master Thesis: Optimization of the design of a and scheduling of a biomethane plant integrated with a reversible Solid Oxide Cell and a PV solar field.

##### Objective:
The objective of this thesis is to model and numerically optimize the design and scheduling of an integrated biogas-based energy plant. Optimization is carried out by formulating and implementing a mixed integer linear program (MILP) in Python, in order to obtain the optimal plant configuration, components sizing and operational strategy under different scenarios, whilst targeting the solution with the minimum annualized costs. 

##### Components of Energy System:
The energy system modelled and optimized in this thesis comprises the following six sections:
1. A biomethane production section, featuring the anaerobic digestion of organic fraction of municipal
solid waste (OFMSW) and biogas upgrading. Upgrading is based on amine-scrubbing and produces
two streams: biomethane in specification for natural gas grid injection and nearly pure CO2;
2. A photovoltaic solar field (PV);
3. An electro-chemical section including a reversible SOEC/SOFC cell (rSOC) and a Sabatier
methanation process, which can work in two modes: (i) as Power-to-Gas system that produces CH4
via methanation from H2 (from water electrolysis in SOEC mode) and CO2 from biogas upgrading;
(ii) as Gas-to-Power system that converts biogas into electricity (SOFC mode);
4. A battery energy storage system (BESS);
5. Gas and heat storage units aimed at decoupling the continuous biomethane production process from
the alternate, discontinuous, electro-chemical processes;
6. A boiler, working as a hot utility to satisfy peak thermal duties.

![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/23474321-872f-41ab-82ec-9ace319ff09e)