# Experiment-1

**DC,Ac,Transient Analysis of Common Source Amplifier**

![Image](https://github.com/user-attachments/assets/d1eddf4d-5823-43fa-805d-59d048a61441)

This report presents the DC analysis, AC analysis, Transient analysis of a common-source NMOS amplifier. The circuit consists of an NMOS transistor with a resistive load, powered by a 1.8V supply. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC  analysis.The simulation results are obtained using LTspice, and theoretical calculations are verified against the observed values.

**Component Details**
    The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification
    
Model : CMOSN ;
MOSFET Length: 180nm ;
MOSFET Width: 0.209253um
Threshold Voltage: 0.366V
Resistor: 2.751891kohm
Supply Voltage: 1.8V
Signal Genertor:
   DC Voltage: 0.9V
   Amplitude: 50mV
   Frequency: 1kHz

**DC Analysis**
Assuming the Power dissipation is 100µW
