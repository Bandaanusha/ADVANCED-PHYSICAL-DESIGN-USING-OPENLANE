# ADVANCED-PHYSICAL-DESIGN-USING-OPENLANE
## Table of Contents
<br>[1.SOC design and Openlane]()<br>

## 1.SOC design and Openlan
RTL to GDSII Flow
- Synthesis
- Floor/Power planning
- Placement 
- Clock Tree Synthesis
- Routing
- Sign Off

<br>1.Synthesis
<br>Design is converted to circuits which contains components of standard cell library. The resultant of synthesis is netlist.
<br>2.Floor Planning/Power planning
<br>Chip die is partitioned between different chip components.In macro floor planning macro dimensions,pin locations.rows and routing tracks are defined ,used during placement and routing steps.
<br>In Power planning power network is constructed. Chip is powered by multiple VDD and GND pins.Power pins are connected to all components by horizantal and vertical rails of metal strapes. This structure reduce resistance.
<br>3.Placement
Macros will place gate level netlist cells on vertical rows,reduce interconnect delay and enable routing.It is done in two steps, 1. Global placement finds the optimal position for all cells.As it is not legal there is a possibility that cells overlap. 2. In detailed placement the positions obtained by global placement are minimally altered to be legal.
<br>4.Clock tree  Synthesis
Before routing the signals we need to route the clock,creating a clock distribution network to deliver clock to all sequential elements with minimum skew. Clock distribution network usually is a tree with clock source is a root and clock elements are leafs. Some clock trees are X,H,hyperloop trees.
<br>5.Routing
Given placement and fixed number of metal layers it is required to find the valid pattern of horizantal and vertical to implement nets that connects the cell together . Router uses the available metal layers as defined by pdk. For each metal layer the pdk defines the thickness,pitch,tracks,minimum width,ways to connect the wire segments on different metal layers together.Sky 130 define pdklocal interconnect layer
