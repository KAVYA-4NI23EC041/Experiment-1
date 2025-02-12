# Experiment-1

**DC,AC,Transient Analysis of Common Source Amplifier**

![Image](https://github.com/user-attachments/assets/d1eddf4d-5823-43fa-805d-59d048a61441)

This report presents the DC analysis, AC analysis, Transient analysis of a common-source NMOS amplifier. The circuit consists of an NMOS transistor with a resistive load, powered by a 1.8V supply. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC  analysis.The simulation results are obtained using LTspice, and theoretical calculations are verified against the observed values.

**Component Details**
  <p>  The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification </p>
    
**Model** : CMOSN <br>
**MOSFET Length** : 180nm <br>
**MOSFET Width** : 0.209253um <br>
**Threshold Voltage** : 0.366V <br>
**Resistor** : 2.751891k &#8486 <br>
**Supply Voltage** : 1.8V <br>
**Signal Genertor**: <br>
   DC Voltage: 0.9V <br> 
   Amplitude: 50mV <br>
   Frequency: 1kHz <br> 

**DC Simulation**
 <br><br>
![Image](https://github.com/user-attachments/assets/506240ae-f9d3-4c51-b156-105e670a6af2) <br><br>
<p> From the simulation:
V<sub>out</sub> = 1.64727V, V<sub>in</sub> = 0.9V, I<sub>d</sub> = 0.00015A.
</p>
If the Power dissipation is 100µW across the resistor, then the current through the resistor is given by <br>
<p>I<sub>d</sub> = Power/Voltage
              = 100µ / 1.8 
              = 55.5µA </p>
              <br>
<p>The output load line equation is given by <br>
 V<sub>out</sub> = V<sub>dd</sub> - (I<sub>d</sub> * R<sub>d</sub>) <br>
 R<sub>d</sub> = (V<sub>dd</sub> - V<sub>out</sub>) / I<sub>d</sub>  <br>
 R<sub>d</sub> = (1.8 - 1.647)/55.5µ <br>
 = 2.751k&#8486 </p>
<br>
Now replace the resistor value by R<sub>d</sub> = 2.751891k&#8486 <br>
Since the calculated current does not match the simulated value, maintain the MOSFET length at 180nm and adjust the width to achieve the desired current value.<br><br>
<table> 
<tr>
 <th><b>Length</b></th>
 <th><b>Width</b></th>
 <th><b>I<sub>d</sub></b></th>
</tr>
<tr>
    <td>180nm</td>
    <td>1µm</td>
    <td>1.4*10<sup>-4</sup>A</td>
</tr>
<tr>
    <td>180nm</td>
    <td>0.1µm</td>
    <td>4.76*10<sup>-5</sup></td>
</tr>
<tr>
    <td>180nm</td>
    <td>0.2µm</td>
    <td>5.462*10<sup>-5</sup></td>
</tr>
<tr>
    <td>180nm</td>
    <td>0.209153µm</td>
    <td>5.555*10<sup>-5</sup></td>
</tr>
</table>
