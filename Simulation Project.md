# Design and Analysis of Operational Trans-conductance Amplifier Using 180nm Technology  <br>
<b> Abstract </b> - <p>This project presents the design and simulation of a high-performance two-stage Operational Trans-conductance Amplifier (OTA) using 180nm CMOS technology in LT-spice. Unlike conventional operational amplifiers, OTAs generate an output current proportional to the differential input voltage, making them highly suitable for voltage-to-current conversion in analog signal processing. The design focuses on achieving high gain, low power dissipation, and improved frequency stability using Miller compensation. The OTA operates with a ±0.9V power supply, achieves an open-loop gain of 60 dB, a phase margin of 60°, and a slew rate of 10.5 V/μs, while consuming less than 3 mW of power. Key design considerations include optimized transistor sizing, consistent channel lengths, and accurate tail current estimation. Simulation results confirm that the OTA meets critical analog performance metrics and is ideal for applications such as analog filters, sensor interfaces, biomedical instrumentation, and low-power mixed-signal systems. Future extensions include scaling to advanced technology nodes and targeting ultra-low voltage operations for energy-constrained environments. </p>

<b> Keywords </b> —Operational Transconductance Amplifier, LTspice, Miller Compensation, CMOS, Analog Design <br>

I.<b>Introduction </b> 
 <p>Operational Trans-conductance Amplifiers (OTAs) are essential components in analog integrated circuits. This 
work focuses on the design and simulation of a two-stage OTA using LT-spice under 180nm CMOS 
technology. The main objective is to achieve high gain, enhanced phase margin, and reduced power 
dissipation through effective compensation techniques.</p>

II. <b>Miller Compensation for Stability in Op-Amp Circuits </b>
<p>Operational amplifiers (op-amps), particularly those implemented using multiple gain stages such as operational transconductance amplifiers (OTAs), require compensation to ensure closed-loop stability. One of the most widely adopted techniques for compensation is Miller compensation, which introduces a dominant pole to increase the phase margin of the system.</p>
<p>In a typical two-stage op-amp architecture, the first stage is a differential amplifier and the second stage provides additional gain. A compensation capacitor C_c is connected between the output of the second stage and the output of the first stage. This configuration leverages the Miller effect, wherein the capacitor is seen as a much larger effective capacitance due to the gain between its terminals. As a result, the dominant pole is shifted to a lower frequency, enhancing system stability.</p>
The loop gain of the system can be represented as: <br>
L(s) = A(s)F(s) <br><br>
<p>where A(s) is the open-loop gain and F(s) is the feedback transfer function. For a stable system, the phase of the loop gain ∠L(jω) at the frequency where |L(jω)| = 1 must be sufficiently greater than −180° to avoid sustained oscillations. The difference between the actual phase and −180° at this frequency is defined as the phase margin (PM): </p>
PM = 180° + ∠L(jω_0dB) <br><br>
where ω_0dB is the gain crossover frequency (i.e., the frequency at which the magnitude of the loop gain is unity or 0 dB). <br>
<p>A phase margin of at least 45° is generally considered acceptable, while a margin of 60° is preferred to reduce overshoot and ringing in the transient response. In systems where the uncompensated op-amp has a low phase margin (e.g., <45°), Miller compensation becomes essential.</p>
<p>Thus, Miller compensation ensures that the gain falls to 0 dB before the phase reaches −180°, thereby preventing positive feedback and guaranteeing stable closed-loop operation.</p>
<br>
 B. <i>Design Specification</i>

|Requirements	|Specifications|
|-------------|--------------|
|Gain	        |60dB          |
|VDD	        |0.9V          |
|VSS	        |-0.9V         |
|GB	          |5MHz          |
|CL	          |10pF          |
|SR	          |10V/μs        |
|VOUT Range	  |±5V           |
|ICMR	        |-0.1V to +0.5V|

---

Power Dissipation	 =< 3 mW <br>
Phase Margin	60° <br>
Bandwidth	1.25KHz <br><br>

C. <i>library and model details</i><br>
Library file used:   tsmc180nm.lib<br>

 NMOS_CUSTOM NMOS<br>
     VTO=0.7 V       ; Threshold voltage<br>
     KP=110u A/V-2       ; µnCox (transconductance parameter)<br>
     LAMBDA=0.04 V-1   ; Channel length modulation<br>

 PMOS_CUSTOM PMOS <br>
     VTO=-0.7 V      ; Threshold voltage<br>
     KP=50u A/V-2         ; µpCox (transconductance parameter)<br>
     LAMBDA=0.05V-1    ; Channel length modulation<br>

D.Schematic View

![Image](https://github.com/user-attachments/assets/3deaad4f-5a0c-44d3-b06c-133e020618e9) <br><br>

E.Components List

|Sl. No|	MOSFET   |	WIDTH	 |LENGTH |FUNCTION |
|------|-----------|---------|-------|---------|
|1     |	M1(NMOS) | 3µm	   |1µm	   |I/P Diff Pair|
|2     |	M2(NMOS) | 3µm	   |1µm	   |I/P Diff Pair|
|3     |	M3(PMOS) | 60µm	   |1µm	   |Active Load|
|4     |	M4(PMOS) | 60µm	   |1µm	   |Active Load|
|5     |	M5(NMOS) | 2.2µm   |1µm	   |Current Mirror, Tail Current Source|
|6     |	M8(NMOS) | 2.2µm   |1µm	   |Current Mirror|
|7     |	M7(NMOS) | 5.49µm  |1µm	   |SS Pull Down Transistor|
|8     |	M6(PMOS) | 118.5µm |1µm	   |SS Pull Up Transistor|

i.Input differential pair <br>
ii.Second stage driver pull down transistor <br>
iii.Second stage driver pull up transistor   <br><br>

a.Capacitors(Cc and Cl) <br>
i.Cc (Miller Capacitor) : 3pF<br>
ii.CL (Load capacitor) : 10pF<br><br>

b.Voltage Source (V)<br>
c.Current Source (A)<br>
d.Resistor(R1): 1Kohm<br><br>

IV. <i>Design Question </i> <br>

<p>To check if all the design specifications are met, we simulate the circuit of OTA. Here, the simulation is done using simulator software called Lt-spice. The schematic of OTA is designed in Lt-spice simulator with VDD= 0.9V and VSS= −0.9V. The bias current of the circuit is 30µA. 
The input voltage of ±5V is given to the circuit. The value of compensation capacitor, CC = 3pF and load capacitor. CL = 10pF . The schematic of OTA which is drawn in Lt-spice is represented in the figure below.</p>
 
i.To calculate the value of compensation capacitor Cc which is give as <br>
CC >  CL<br>
CC >  (10p)<br>
CC > 2.2 pF<br>
CC = 3pF<br><br>

ii.To calculate tail current IS based on Slew Rate <br>
IS = SR * CC<br>
= (10*106) * (3pF)<br>
= 30µA<br><br>

iii.Now, determine the aspect ratio of M3 <br>
 ![Image](https://github.com/user-attachments/assets/65531a1d-f987-43a5-9021-1adc5824af9a) <br>
Since M3 and M4 are identical, S3 will be equal to S4 <br>
![Image](https://github.com/user-attachments/assets/8c477afe-0702-4eae-9185-c549e7b05fb8) <br>
iv.The trans-conductance of the input transistor is determined from the equation that follows <br>
![Image](https://github.com/user-attachments/assets/b6badd73-8976-4d86-8249-3b79fc301b5f) <br>
v.From the above equation, the aspect ratio of  M1 and M2  can be directly obtained as<br>
![Image](https://github.com/user-attachments/assets/4f976b82-0d82-4218-97a4-5b0682b146ec) <br>
vi.The aspect ratio M1 and M2 is determined as<br>
![Image](https://github.com/user-attachments/assets/c92cb75e-4a24-4670-b60e-b7daad332be4) <br>
![Image](https://github.com/user-attachments/assets/d3a2bcba-b319-4772-adf7-9658cbfa4aab) <br>
vii.Then, determine the value of the current through M6 by the following equation<br>
![Image](https://github.com/user-attachments/assets/42da6c89-5986-4196-8914-3504239f8a95) <br>
viii.Design S7 to achieve the desired current ratios between I5  and I6 <br>
![Image](https://github.com/user-attachments/assets/0be2a9bc-3861-48c5-b937-c911ad06de45) <br>
ix.Finally determine the value of gain and power dissipation and check its specification.<br>
![Image](https://github.com/user-attachments/assets/b2b181ec-db5a-4353-aef8-bd29487b685f) <br>
![Image](https://github.com/user-attachments/assets/3494e303-baa8-4ada-8ba3-5bd393e93495) <br>
![Image](https://github.com/user-attachments/assets/648e50ef-07fd-4dc8-a47d-932ce0fb14c1) <br><br>
A.Hardware Required<br>
Simulation-based study, no external hardware required<br><br>

V. <b>Simulation Result</b> <br><br>
A. <b>DC Characteristics </b><br>
![Image](https://github.com/user-attachments/assets/6736786a-3bd7-4339-89c5-8550f1ca8237) <br>
![Image](https://github.com/user-attachments/assets/48ef72f1-cbf8-463e-9588-6a644843ad11) <br>

B. <b>Transfer Characteristics</b><br>
1)Common Mode Analysis <br>
![Image](https://github.com/user-attachments/assets/ba43edfb-e6ec-46e3-8a34-2d9d6be575b9) <br>
VOUT = 300mV <br><br>
2)Differential Mode Analysis <br>
![Image](https://github.com/user-attachments/assets/ad8402e9-683e-4693-aa24-4e03c3b8a712) <br>
VOUT = 412mV (peak-peak value)<br>
VIN = 100 μV (peak-peak value)<br><br>

C. <b>AC Characteristics</b><br>
1)Common Mode Analysis<br>
![Image](https://github.com/user-attachments/assets/bcd8d228-c2d7-43b2-ac28-534186ade74a) <br>
Gain = 4dB<br>
Phase = -30o<br><br>

2)Differential Mode Analysis<br>
![Image](https://github.com/user-attachments/assets/53f9bd3e-09ca-402b-9f22-5f80b9789558)<br>
Gain = 72dB<br>
Cut-off Frequency = 7.3KHz<br>
Phase = 60deg <br><br>

VI. <b>RESULT</b> <br>

|Parameters       |	Calculated    |	Obtained                       |
|-----------------|---------------|--------------------------------|
|Gain	            |60dB	          |72dB                            |
|VDD	            |0.9V	          |0.9V                            |
|VSS	            |-0.9V	        |-0.9V                           |
|GB	              |5MHz	          |26MHz                           |
|CL	              |10pF 	        |10pF                            |
|VOUT Range       |±5V	          |520mV to 120mV (for input 50 μV)|
|ICMR	            |-0.1V to +0.5V | -0.5V to +0.3V                 |
|Power Dissipation|	=< 3 mW       |	1.8mW                          |
|Phase Margin	    |60°	          |60°                             |
|Bandwidth	      |1.25KHz	      |6.53KHz                         |

---

VII. <b>Design Methodology</b> <br>

<p>The OTA is designed using standard analog design flow starting with length selection (L = 1um), 
compensation capacitor design, tail current estimation for slew rate, aspect ratio calculations for transistors, 
and gain-bandwidth tuning. Miller compensation is used to improve stability.</p>


VIII. <b>CONCLUSION</b><br>
<p>The objective of this work is to design and analyze an Operational Transconductance Amplifier (OTA) using LTspice software based on 180nm CMOS technology. The design incorporates Miller Compensation, a widely adopted frequency compensation technique that utilizes the Miller effect by introducing a compensation capacitor across the high-gain stage to ensure stability. The simulation results validate that the designed OTA meets all specified performance metrics, including desired gain and phase margin. The circuit demonstrates high gain, low power dissipation, and excellent stability, making it well-suited for low-power analog applications. This analysis highlights the effectiveness of Miller Compensation in achieving robust and power-efficient amplifier performance in deep-submicron CMOS processes.</p>

IX. <b>References</b> <br>
[1] Behzad Razavi, Design of Analog CMOS Integrated Circuits, McGraw-Hill. <br>
[2] R. Jacob Baker, CMOS: Circuit Design, Layout, and Simulation, Wiley.<br>
III. <b>TECHNICAL SPECIFICATIONS </b> <br>
A. <i>Software and Tools</i> <br>
1.LT-spice XVII (Simulation and waveform analysis) <br>
2.CMOS 180nm Technology Models <br>
3.Microsoft Word for Documentation <br>
4.180nm Technology Library File<br> <br>

