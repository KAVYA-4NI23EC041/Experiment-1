# Experiment-1

**DC,Ac,Transient Analysis of Common Source Amplifier**

![Image](https://github.com/user-attachments/assets/d1eddf4d-5823-43fa-805d-59d048a61441)

This report presents the DC analysis, AC analysis, Transient analysis of a common-source NMOS amplifier. The circuit consists of an NMOS transistor with a resistive load, powered by a 1.8V supply. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC  analysis.The simulation results are obtained using LTspice, and theoretical calculations are verified against the observed values.

**Component Details**
    The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification
    
**Model** : CMOSN <br>
**MOSFET Length** : 180nm <br>
**MOSFET Width** : 0.209253um <br>
**Threshold Voltage** : 0.366V <br>
**Resistor** : 2.751891kohm <br>
**Supply Voltage** : 1.8V <br>
**Signal Genertor**: <br>
   DC Voltage: 0.9V <br> 
   Amplitude: 50mV <br>
   Frequency: 1kHz <br> 

**DC Analysis**
From the Simulation:

If the Power dissipation is 100µW across the risistor, then the current through the resistor is gien by <br>
I<sub>d</sub> = Power/Voltage
              = 100µ / 1.8
              = 55.5µA 
              <br>
The output load line equation is given by <br>
 V<sub>out</sub> = V<sub>dd</sub> - (I<sub>d</sub> * R<sub>d</sub>) <br>
 R<sub>d</sub> = (V<sub>dd</sub> - V<sub>out</sub>) / I<sub>d</sub>  <br>
 R<sub>d</sub> = (1.8 - 1.647)/55.5µ <br>
 = 2.751kohms
