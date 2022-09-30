# CMOS-NAND-Gate-Design-using-Cadence-Virtuoso
### 2-input CMOS NAND Gate Design and Analysis with Layout using Cadence Virtuoso
---
<!-- Cadence Project (Transient, DC & Noise Response With Layout) -->

I’m really glad to share that, this is my second project on __Cadence Virtuoso__. I am designing here a 2-input CMOS NAND Gate with its layout.

___Before I start explaining my project in details, you should know a few things !___

### What is CMOS?
Complementary Metal Oxide Semiconductor (CMOS) is a type of metal–oxide–semiconductor field-effect-transistor (MOSFET) fabrication process that uses complementary and symmetrical pairs of p-type and n-type MOSFETs for logic functions. CMOS technology is used for constructing integrated circuit (IC) chips, including microprocessors, microcontrollers, memory chips and other digital logic circuits.   

CMOS refers to the two different types of semiconductors each transistor contains — N-type and P-type. N-type semiconductors have a greater concentration of electrons than holes, or places where an electron could exist. P-type semiconductors have a greater concentration of holes than electrons. These two semiconductors work together and may form logic gates based on how the circuit is designed.    

### What is CMOS NAND Gate?  
NAND gate (NOT-AND) is a logic gate which produces an output which is false only if all its inputs are true; thus its output is complement to that of an AND gate. A LOW (0) output results only if all the inputs to the gate are HIGH (1); if any input is LOW (0), a HIGH (1) output results. A NAND gate is made using transistors and junction diodes. By De Morgan's laws, a two-input NAND gate's logic may be expressed as A • B = A+B, making a NAND gate equivalent to inverters followed by an OR gate.

The NAND gate is significant because any boolean function can be implemented by using a combination of NAND gates. This property is called functional completeness. It shares this property with the NOR gate. Digital systems employing certain logic circuits take advantage of NAND's functional completeness.

### The Project details of mine :
Here i have use __gpdk90n__ :-
1. Two pmos1v and Two nmos1v. The pmos are is in parallel and the nmos is in series.
2. For vdd i have use vdc (1v)
3. For input i have use two vpulse (1v)
4. Here I am doing three types of Analysis :  
    i ) Transient Response  
    ii ) DC Response  
    iii ) Noise Response & Noise Figure  
    N.B. I'm measuring here 2 inputs & output as Voltage and Current (I) in Vout & VDD node.
5. In Layout - Metals Used ( Metal1 ) and Poly Layer
6. The minimum width of metal utilized for routing is 0.12
7. DRC and LVS clean (there are no error)

So I designed a Schematic of the CMOS NAND Gate, where the whole thing is based on gpdk90n. I have use 2 pmos for 1v and 2 nmos for 1v. I also designed a symbol of it, so that i can utilise that for further schematic creation.  

The below figure shows a 2-input CMOS NAND Gate. It consists of two PMOS connected in parallel and two NMOS connected in series.

The equivalent switching circuit when both inputs are low. Here, the gates of both PMOS are negative with respect to their sources, since the sources are connected to VDD. Thus, PM0 and PM1 are both ON. Since the gate – to – source voltages of NM0 and NM1 (NMOS) are both 0V, those MOSFETs are OFF. The output is therefore connected to VDD (HIGH) through PM0 and PM1 and is disconnected from ground.

The equivalent switching circuit when Va = 0 and Vb = VDD. In this case, PM0 is on because VGS1 = −VDD and NM1 is ON because VGS4 = VDD. MOSFETs PM1 and NM0 are off because their gate-to-source voltages are 0 V. Since PM0 is ON and NM0 is OFF, the output is connected to VDD and it is disconnected from ground. When Va = VDD and Vb = 0V, the situation is similar ; the output is connected to VDD through PM1 and it is disconnected from ground because NM1 is OFF. Finally, when both inputs are high (Va = Vb = VDD), PMOS PM0 and PM1 are both OFF and NMOS NM0 and NM1 are both ON. Thus, the output is connected to the ground through NM0 and NM1 and it is disconnected from VDD.

![Scametic](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Scametic.PNG?raw=true) 
![Symbol](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Symbol.PNG?raw=true)
![Symbol_Scametic](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Scametic_Diagram.PNG?raw=true)

#### DC, Transient :
_Here I am doing three types of Analysis - DC, Transient and Noise_.  
In DC and Transient Analysis i have measured Va, Vb & Out as Voltage, and Current (I) in Vout & VDD node.  The plots of _Va_ , _Vb_ and _OUT_ shows the _voltages_, on the otherhand _VDD(I4)_ & _Vout(I4)_ shows the _current (I)_.  
![output](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Output.PNG?raw=true)
![output2](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Output_2.PNG?raw=true) 

#### Noise Figure and Noise Response :  
For measuring of Noise Figure and Noise Response i had to use PORTS instead of Vpulse. For Noise Analysis i have measured input & output noise. In Noise Response the plots shows the input and output noise.  
![noise_figure_scametic](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noice%20Figure_Scametic.PNG?raw=true)
![noise_figure](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noise%20Figure.PNG?raw=true)
![noise_output1](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noise(IN,OUT,GND).PNG?raw=true)
![noise_output2](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Noise(IN,OUT).PNG?raw=true) 

#### Layout :
In Layout i have use  Metal1 and Poly Layer. I have use here X & Y snap spacing is 0.01m and also the minimum width of metal utilized for routing is 0.12.  
![Layout](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/Layout.PNG?raw=true)  

#### Design Rule Check (DRC)  
DRC is clean. There are no error in DRC.
![DRC](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/DRC%20Check.PNG?raw=true)  

#### Layout Versus Schematic (LVS)  
LVS is clean. There are no error in LVS.  
![LVS](https://github.com/wreasin/CMOS-NAND-Gate-Design-using-Cadence-Virtuoso/blob/main/image/LVS%20Check.jpg?raw=true)
