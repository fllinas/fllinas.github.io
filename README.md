# Projects Portfolio
**Fabrizio Llinás Biava**
| Energy Expert and Consultant

fabriziollinas12@gmail.com

**Energy expert with experience as project manager, consultant and data analyst on industrial size projects. High focus on projects related to energy systems optimization, energy consultancy, CAPEX projects and data analysis with Python. Master’s degree in Energy Engineering from Politecnico di Milano with outstanding academic results and professional achievements. Energy transition and renewable energy enthusiast.**


| Language  | Proficiency |
| ------------- |:-------------:|
| Spanish      | 5/5     |
| English      | 5/5      |
| Italian      | 4/5      |


##### List of projects:

1. [Master Thesis: Optimization of integrated energy plant](#project-1)
2. [MILP Optimization of an industrial steam and electricity network](#project-2)
3. [Condensing capacity increase on an industrial refrigeration system](#project-3)
4. [Compressor sequencing algorithm for an industrial refrigeration system](#project-4)
5. [Savings estimation for instalation of a new coal boiler economizer](#project-5)
6. [Analysis of parameter influences on an absorption system](#project-6)
7. [Discharge pressure reduction on an industrial refrigeration system](#project-7)
8. [Machine learning algorithms for energy savings estimation](#project-8)

<br/><br/>


## Project 1
**Master Thesis: Optimization of the design of a and scheduling of a biomethane plant integrated with a reversible Solid Oxide Cell and a PV solar field.**

##### Objective:
The objective of this thesis is to model and numerically optimize the design and scheduling of an integrated biogas-based energy plant. Optimization is carried out by formulating and implementing a mixed integer linear program (MILP) in Python, in order to obtain the optimal plant configuration, components sizing and operational strategy under different scenarios, whilst targeting the solution with the minimum annualized costs. 

Problem statement and optimization formulation:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/a2bb6337-e691-42e1-81dc-61433e203bdc)


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

Integrated energy plant - components, energy streams and material streams: <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/23474321-872f-41ab-82ec-9ace319ff09e)


##### Selection of best input hourly profiles and forecasting scenarios:

Due to the high amount of data corresponding to years of simulation, a k-means clustering algorithm is used to reduce inputs into more manageable amount of information. In this work, the annual data corresponding to ambient temperature, solar irradiance, gas prices and electricity prices is reduced into 6 different clusters combining typical and extreme periods whilst considering different time frames in the form of days and weeks (typical days and/or typical weeks and extreme periods to evaluate plant performance).

Clustered hourly profiles for 6 typical days during the year: <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/f4fe3414-df8e-4b13-b342-6a1b33bb3022)

Furthermore, forecasted scenarios are inputed to evaluate results in different present and futuristic possiblities. This result in the combination of 12 different scenarios for the simulation: <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/8238d77f-55bc-4eee-b7a2-7fbc105871bd)


#### Simulation and Results

The python MILP algorithm was proven to being able to simulate the operation of the integrated energy plant and obtain the optimal results on selection of equipment, optimal sizing and hour by hour operation whilst maximizing the annual profits.

Results per Scenario:<br/><br/>

![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/233e6455-eee6-425f-b11f-a3b6a8d882b9)

Annualized and Normalized Energy and Material Balances:<br/><br/>

![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/48603e18-43da-44e6-921d-4bf4dbc5ab0b)


#### Conclusions:

The key results of this thesis are:
1. A MILP optimization model for the design and scheduling of an integrated multi-energy plant
is developed in PYTHON (Anaerobic Digester + Biogas Upgrading + rSOC + methanator +
PV + BESS).
2. The model is based on linearized on-design/off-design performances and costs starting from
detailed first principle models (Aspen Plus, Matlab, etc.) of the components.
3. Different "typical periods" are assessed in order to get a reasonable trade-off between
computational time and accuracy. The selected approach is with 6 typical days + 3 extreme
ones.
4. Twelve alternative scenarios are investigated, each one reflecting different capital costs (present
day vs 2050-time horizon) and constraints (e.g. no net energy import, 100%-renewable, and
carbon related incentives/restrictions). Results show that SOFC is installed in "no net energy
import" scenarios and in case of higher market penetration (i.e. year 2050).
5. Sensitivity is carried out for a number of parameters. The most interesting one is on the
"additional premium tariff" (i.e. incentives) the plant will receive for ancillary services on the
electricity market. Results show that in case the Ancillary Service Factor (i.e. additional
revenue for the plant for the energy storage service) is 50% on top of the electricity price then
the electrolysis cell mode is selected for this 2050 scenario. The system now acts as a “big
battery” enabling interactions between the fully decarbonized electricity grid and a “greener”
gas grid, by absorbing exceeding electric power coming from peak RES afternoon and
converting it into biomethane
Economic analysis on 3 interesting scenarios (1D, 3C and ASF=1.75) of the plant design show
that a retrofit option is of big interest for 2050 old anaerobic digesters that might be thought of
being dismantled; on the other hand, the full plant option (including AD) requires a gross
financing for the different plant designs with gate fees of over 90 €/ton.
7. The interactions amongst the different units in matter of energy and material streams are indeed
of interest as the system selects the multiple conversion and storage units whilst satisfying for
their multiple and variable demands of electricity and heat. The system can be optimized for
different power-to-gas, gas-to-power and power-to-power scenarios.

<br/><br/>

## Project 2
**MILP Optimization of an industrial steam and electricity network.**

##### Objective:
The objective of this project is to optimize the operational costs of a steam and electricity generation plant from a real industrial site. Real historic data is used to calculate mass and energy balances across the site; that accompanied with the minimazation of the objective function and the definition of the manipulable variables all inside of a Mixed Integer Linear Program in Python end up with results on the optimal operation of the industrial site. Potential savings of up to 20% in costs resulted to be achievable.

#### Actual state of the system:

4 Boilers and 3 steam turbines compose the steam network alongside steam demands on 3 different pressure levels. The electric power demanded by the site was satisfied by either turbine power production or imported power from the electricity grid. In the end, the plant has coal and electric power bills to be payed which indeed are the objective to minimize. 

Steam and Electricity Generation Industrial Plant:<br/><br/>
![Steam network](https://github.com/user-attachments/assets/6189f673-9e87-47a7-8cda-ab83243462ae)


#### Development of the MILP Python Algorithm:

Many plant restrictions were given as constraints to othe optimizer as well as real time sensors were given as inputs. A custom built cost function was given as objective to be minimized. A more complex modelling was done for each turbine were individual models were implemented to predict the expected power production depending on the manipulated inlet steam and/or extraction. 

Turbine Inlet Steam Flow rate (Y axis) vs Generated Power (X axis) - Different colors indicate different steam extraction ranges:<br/><br/>
![image](https://github.com/user-attachments/assets/89cd6f8d-97b8-4239-a677-496b2ee666d3)

#### Simulations and results:

Many scenarios were run under different electricity tariffs for the plant resulting in different results depending on the operating conditions. Overall, potential of cost reductions of 20% were found through a better managment of the electricity imports vs use of coal for the boilers in the plant.

Total plant costs (Y axis) vs Simulation time (X axis) - Colors indicate true costs or optimized costs resultant from simulation:<br/><br/>
![image](https://github.com/user-attachments/assets/7754eb17-f836-4598-afb1-d2ba0f789333)


<br/><br/>

## Project 3
**Condensing capacity increase on an industrial refrigeration system**

##### Objective:
The objective of this project is to detect the necessity of a condensation capacity increase for an compressed NH3 refrigeration system whilst estimating the potential savings that could be achieved on installing different sizes. An analysis and further simulation is done on Python to carry out the task.


##### Actual state of the system:

Through the analysis of 6 monhts of data on a 10 minute granularity an initial data analysis is done to detect the behaviour of the important parameters. These being: flow rates, discharge pressures, suction pressures, compressor consumptions all from both lower and high stage pressure levels. Anomalies are detected on the high variations on ranges of discharge pressures mainly when an increase in demand is observed (high flow rates)

High stage flow rate (Y axis) vs Low stage flow rate (X axis) - Ligher colors indicate higher discharge pressures:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/75675ff7-e693-4ec0-ad85-d048358989a0)


Discharge pressure (Y axis) vs Estimated plant demand (X axis):<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/00e8a339-9c56-4a76-93e8-813ace73236e)



##### Energy efficiency of the industrial site:

A calculation of the systems COP (Coefficient of Performance) is done using enthalpies of ammonia whilst considering the changes of state of the substance through the consumers. COP is further evaluated and is found to start reducing when plant starts to exceed a given value.

COP (y axis) vs Plant demand (TR): <br/><br/>

![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/f6eb6268-6ba9-4826-b888-88c2e42bd00a)



#### Simulations and results:

A simulation is done with the expected increase in condensation capacity and estimated reduction in discharge pressure for every point of data. Through a machine learning model the expected power consumption is calculated and estimated savings for the installation of new equipment is obtained. Results are not shown for disclosure but through them the industrial site could decide which equipment size was better for their needs.

<br/><br/>

## Project 4
**Compressor sequencing algorithm for an industrial refrigeration system**

##### Objective:

The objective of this project was to develop an optimized sequencing algorithm (Python) on the turn on/turn off from 9 compressors from an industrial ammonia vapour compression refrigeration site. 

##### Actual state of the system:

Initially, we analyze more than 8 months of data on a 5 minute granularity to obtain necessary information on improvement possibilities. We can observe through the demand flow rates that the nature of the plant is quite variable through time, and so the possibilities of sequencing start becoming realistic.

Demand distribution for all 3 main user groups (flow rate in gpm): <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/4957689d-808f-4c4c-a96c-410cdab90c6a)


As we manipulate the data in python in order to being able to analyze sequence by sequence of compressors, we detect different efficiencies for the vast combination of compressor sequences that occur on the system.

Flow rate (X axis) vs Efficiency (Y axis) - feature: sequences in colors:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/675d5923-18a1-435e-be98-fbec57bcec74)

Different efficiences for the different sequences conclude certainly on the possibility of improving performance through the use of more efficient sequences:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/a776c0b4-5d33-4341-8273-d75d67f74a01)


##### Algorithm Development:

Through the selection of the most optimal sequences and optimization of the load factor, we simulate the possible behaviour of the system on the possible implementation of the algorithm.

Current load factor (orange) vs Simulated load factor (blue):<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/587b9065-c288-43c6-8cf9-d24950b97133)


##### Results:

After implementation of the algorithm outputs on site, a considerable increase in the load factor was achieved with savings estimated at around 5% of total consumption. 

Load Factor Distribution - before (blue) and after implementation (red):<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/2d057b55-a32a-4c7a-9065-0e81504403c2)

<br/><br/>

## Project 5
**Savings estimation for instalation of a new coal boiler economizer**

##### Objective:
The objective of this project was to quantify the potential benefit of the installation of a new boiler economizer for a coal boiler. 

##### Actual state of the system:

Through live data for almost a year from a coal boiler, we are able to detect the necessity of taking advantage of the flue gas being released at over 250 °C to the atmosphere. An economizer would indeed increase the efficiency of the boiler and hence reduce the coal consumption (carbon emissions and savings). 

Real time measurements of important variables of the system (gas flow rate, water flow rate, outlet flue gas temperature and inlet water temperature): <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/b4ea00cb-afad-4f7f-86bb-39321a3fd6e3)


##### Solution and results:

Through the iterative solution of a system of equation resultant of the mass and energy balances we are able to estimate the outlet temperature of the system and hence the necessary area for the economizer to be installed. Client could in the end select the necessary equipment to match their needs.

New flew gas temperature vs inlet gas temperature vs Outlet water temperature (for a given size of economizer):<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/3a463241-bc56-4315-8191-d5116bc82f6f)


Economizer heat trasnfer area needed to satisfy an outlet temperature of 300°F during boxplot given percentile of time (Example 1225 m2 to reach that temperature 50% of the time):<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/55c83e36-5024-4dec-b47b-84fec968d802)



<br/><br/>

## Project 6
**Analysis of parameter influences on an absorption system**

##### Objective:
The objective of this project was to analize the effect of different process variables on the efficiency and performance of an industrial refrigeration site using NH3 absorption.

##### Sensibility Analyisis:

After the calculation of a the systems KPI (Coefficient of Performance) we evaluate the effects of the important variables on the performance using data over almost 1 year. A sensibility analysis is performed on the most important variables of the system consisting on finding which variables have a considerable effect on the COP.

Sensibility analysis of process variable#XX vs KPI of the system:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/7b8737a6-a7ed-45ee-b448-82acc7d2723f)


##### Periodic changes:
Besides the analysis on the effects of the variables on the KPI, an analyisis was made on the effect of operational changes in the system. Client defined the operational changes and their timeframes and an analyisis was ran on the effects of these changes on variables and KPIs, resulting on evaluations on good or bad effects on control variations. A huge simplification is done on this explanation as the system consisted on a considerable amount of variables as well as the functioning of 3 similar systems in paralell.

Box plot: Operational period (y axis) vs efficiency of the system (x axis): <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/bde2274b-bcab-4319-a9b0-4079793c8baf)


##### Results:
Through the use from a developed baseline (machine learning model) for gas consumption prediction and monitoring of the variable values plus operational changes, savings were achieved as a significant increase on the system performance was achieved.<br/><br/>

![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/ed282e78-72de-4322-94cf-816c848a8ea1)

<br/><br/>

## Project 7
**Discharge pressure reduction on an industrial refrigeration system**

##### Objective:
The objective of this project was to reduce the discharge pressure of an NH3 vapour compression industrial refrigeration site with the installation of a new evaporative condenser. Initially a prediction on potential savings is made, whilst after the installation of the equipment optimal point of operation is further evaluated.

##### Analysis and Results:
As it was observed initially, very high discharge pressure where increasing the system's electricity consumption and the installation of more condensing capacity was reccomended. Selection of the correct equipment was done through data, and after the excecution of the project an initial reduction on the pressure was indeed achieved. Furthermore, a post monitoring on the pressure reduction was vital to observe that the pressure's set point lower limit could be even reduced more. Backing up this initiative with a minimum pressure optimization algorithm, lower pressures for the system were achieved without compromising its safety and thus electrical consumption of the industrial site was reduced. 

Discharge pressure reduction through project energy efficiency measurements:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/b7ba6722-e349-4c20-b16d-13055989f64e)

Energy consumption baseline for energy savings considering production data: <br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/f58e2bfe-05df-4496-aaa4-501c4f2a8162)


<br/><br/>

## Project 8
**Machine learning algorithms for energy savings estimation**

##### Objective:
These project refers to multiple "baselines" developed in order to monitor and estimate energy savings on different industries (after an energy efficiency measurement is taken). 

##### Context:
In order to keep track of the performance of an energy system, a "baseline" is developed using the system's demand as feature with the objective of predicting the energy consumption (gas, electricity, coal, etc). This baseline could be based on one different types of machine learning models (linear regression, random forests, KNN, amongst others) and should obtain certain statistical parameters in order for it to be able to be used as a trustworthy measure of energy savings. I have developed many baselines (on python) for different perimeters in industries (boilers, turbines, compressors, full site electric consumption, amongst others) and they have been used as a reference to measure energy performance and energy optimization iniciatives.

Prediction vs Real measurement for a train vs test set of gas consumption (m3/h) on an industrial boiler:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/be59c9ad-54bc-42a7-8fde-8d51d468841c)

Prediction vs Real measurement for a train vs test set of an electricity consumption (kWh/d) on an industrial refrigeration system:<br/><br/>
![image](https://github.com/fllinas/fllinas.github.io/assets/55508521/ee9ebeac-3766-4587-95f9-ac65e240e61e)


<br/><br/>

