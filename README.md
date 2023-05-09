# Vehicular-Throttle-Control
Abstract:
The aim of this project is to implement a Fuzzy Logic Controller (FLC) for the speed control of a vehicle. The system will take in two fuzzy inputs, speed difference (SD) and acceleration (A), and produce a fuzzy output, throttle control (TC).


Introduction:
Fuzzy Logic Controllers (FLCs) are a type of control system that uses fuzzy logic to control the output based on the input. FLCs have been successfully applied in various fields, such as automotive control, robotics, power systems, and aerospace. FLCs are particularly useful in situations where precise mathematical models are not available or difficult to obtain, or when human expertise is required to make decisions. In this context, we will explore a simple example of FLC for speed control of a vehicle. We will define the universe of discourse, the fuzzy sets, and the rules governing the system. We will then implement the FLC using Python, and test it with different input values. This will give us a better understanding of how FLCs work, and how they can be applied to real-world problems. 

Technology and Algorithm used:
The project uses Python programming language to implement the FLC. The Universe of discourse for the system is [0, 240]. The inputs are partitioned into seven fuzzy sets, namely NL, NM, NS, ZE, PS, PM, and PL. The partitioning is done using the triangular and open left-right membership functions.
The fuzzy sets are then used to determine the fuzzy values for all the inputs using the partitioning function. The fuzzy values of all the inputs for all the fuzzy sets are displayed to the user. The rules for the FLC are then implemented using the min-max composition method. There are eight rules in total.
The rules are implemented using the "rule" function. The function takes in the fuzzy values of all the inputs for all the fuzzy sets and applies the rules to determine the output. The "compare" function is used to determine the minimum value of the two fuzzy inputs for each rule. The minimum value is used to calculate the output for that rule. Finally, the output is defuzzified using the centroid method.


Parameters of Algorithm and its Representation:
FLC: Speed control of a vehicle
Let two fuzzy inputs (speed difference (SD) and acceleration (A)) and one fuzzy
output throttle control (TC) be there.
X: Universe of discourse [0,240]
Partitions: 
    NL: Open left MF (a = 30, b = 60) 
    NM: Traingular(a = 30, b = 60, c = 90)
    NS: Traingular(a = 60, b = 90, c = 120)
    ZE: Traingular(a = 90, b = 120, c = 150)
    PS: Traingular(a = 120, b = 150, c = 180)
    PM: Traingular(a = 150, b = 180, c = 210)
    PL: Open right (a = 180, b = 210) 
    
Rules
R1: if SD is NL and A is ZE then TC is PL
R2: if SD is ZE and A is NL then TC is PL
R3: if SD is NM and A is ZE then TC is PM
R4: if SD is NS and A is PS then TC is PS
R5: if SD is PS and A is NS then TC is NS
R6: if SD is PL and A is ZE then TC is NL
R7: if SD is ZE and A is NS then TC is PS
R8: if SD is ZE and A is NM then TC is PM
