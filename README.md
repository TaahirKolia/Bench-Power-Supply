# Bench-Power-Supply

For this project one was tasked to implement an affordable design solution for a variable bench PSU. This was to be achieved by repurposing a PC PSU into a bench PSU that has the capacity of powering simple circuits in addition to more complex electronics and microcontrollers. The final design included a 3D printed casing/enclosure that housed multiple fixed outputs terminals in addition to a variable voltage output.
The first step taken on this involved understanding the capabilities of a PC PSU and how it operates. It has a multitude of pre-existing wires and connections such as ground, voltage, and signals wires, that are colour coordinated based on their rating or usage. Certain connections needed to be made using some signal wires to turn the PSU on and allow it to operate without a load. A diagram showing how certain wires were connected can be found in the project report.

To get the fixed voltage outputs operational, a straightforward process was carried out that involved organizing the voltage wires according to their ratings and thereafter connecting it to their respective terminals on the 3D model. Three different voltage ratings were used, 3.3V, 5V, and 12V. As an additional feature, a USB hub powered by a 5V wires was added to power electronics such as microcontrollers.
The variable output, however, was not as straightforward as the fixed output terminals as two different solutions to needed to be explored to try to achieve this. The first potential solution involved building a voltage regulator circuit, using an LM317 regulator, with the variable output voltage being controlled by a 10kΩ high precision potentiometer. Thereafter an LM324 op-amp was connected at the output terminal of the regulator to act as a buffer, that isolates the load from the regulator, thus preventing loading. The second potential solution used an LM2596 DC-DC step down buck booster to vary the output. A brief comparison between the two solutions is relayed in the table below:

Table 1: Comparison between the two variable voltage solutions.
Voltage Regulator	            | DC-DC Step Down Buck Converter
------------------------------|-------------------------------
Capable of achieving the desired voltages of 1-12V. |	Capable of achieving the desired voltages of 1-12V.
Outputs small currents of approximately 10mA.	| Can achieve large output currents of 2-3A
Inexpensive solution since small, individual components are required.	| Marginally expensive but comes as a modular solution.


Due to the high impedance of the op-amp in the regulator circuit, very little current could be supplied to the load and therefore the buck converter was deemed to be the more viable option for the variable output as it could output larger currents.

Furthermore, a digital voltmeter and ammeter were connected to the variable output to provide an indication of the ratings of voltage and current ratings of the terminal once it is in use. The accuracy of this was determined by using an external ammeter and voltmeter with a test load attached to it. The digital ammeter and voltmeter both had an offset error and needed to be recalibrated by adjusting components on the board. This solved the offset error for the voltmeter, however, the problem persisted for the ammeter and the offset was deemed as a manufacturing fault. 
