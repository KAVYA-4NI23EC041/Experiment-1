# Experiment-1

## **DC,AC,Transient Analysis of Common Source Amplifier** <br>
<p>The Common Source (CS) Amplifier is a fundamental building block in analog circuit design, widely used for voltage amplification. In this circuit, an NMOS transistor operates as the active device, with a passive resistor (R<sub>d</sub>) as the load. The circuit is biased using a DC voltage source (V<sub>d</sub>), and an AC input signal is applied to the gate.</p> 
<p> <ins>Key components and their roles:</ins> <br>
1. R<sub>d</sub> (Drain Resistor): Provides the required voltage drop to amplify the signal. <br>
2. W (Transistor Width): Affects the transconductance (gm), influencing gain and bandwidth.<br>
3. V<sub>d</sub> (Drain Supply Voltage): Provides DC biasing for the NMOS transistor. <br>
4. AC Input (SINE source): The test signal used to analyze circuit response. </p>

![Image](https://github.com/user-attachments/assets/d1eddf4d-5823-43fa-805d-59d048a61441)

<p>This report presents the DC analysis, AC analysis, Transient analysis of a common-source NMOS amplifier. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC analysis.</p>

### **<ins>Component Details</ins>**
  <p>  The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification </p>
    
**Model** : CMOSN <br> 
**MOSFET Length** : 180nm <br>
**MOSFET Width** : 0.209253µm <br>
**Threshold Voltage** : 0.366V <br>
**Resistor** : 2.751891kΩ  <br>
**Supply Voltage** : 1.8V <br>
**Signal Genertor**: <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. DC Voltage: 0.9V <br> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Amplitude: 50mV <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Frequency: 1kHz <br> 

## **<ins>DC Simulation</ins>**
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
<br>
The DC operating point analysis confirms that the NMOS transistor operates in the saturation region with 
I<sub>d</sub> ≈ 55.5μA. <br>
V<sub>ds</sub> = V<sub>out</sub> = 0.1647V <br>
V<sub>ov</sub> = V<sub>gs</sub> - V<sub>th</sub>  = 0.9 - 0.36  = 0.54V <br>
i.e V<sub>ds</sub> > ( V<sub>gs</sub> - V<sub>th</sub>) <br>
<br>

## **<ins>Transient Analysis</ins>** <br>
Transient analysis is a time-domain simulation technique used to observe the circuit's response to time-varying inputs.<br> For this experiment find the gain and output impedence of the circuit.
For the same circuit, perform the transient analysis keeping the sinusoidal voltage signal DC offset as 0.9V, and amplitude 50mV, and frequency = 1kHz <br>
And the AC amplitude as 1V. <br>
In the configure analysis select stop time as 5ms. <br><br>
![Image](https://github.com/user-attachments/assets/248274f7-e1f2-401a-ad52-6181a2053d9e) <br>
From the graph: <br>
 We can observe **180&deg;** phase shift in the amplified output voltage wave  <br>
&nbsp;&nbsp;&nbsp; gain = V<sub>out</sub> / V<sub>in</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 1.66/0.9  = 1.84 <br>
<br>
From calculations:
 gm = 2(I<sub>d</sub>)/(V<sub>ov</sub>)  &nbsp;&nbsp;&nbsp; i.e  V<sub>ov</sub> = V<sub>gs</sub> - V<sub>th</sub>  <br>
 &nbsp;&nbsp; = 2(55.5μ) / ( 0.9 - 0.3) <br>
 &nbsp;&nbsp; = 1.8 <br><br>
 R<sub>out</sub> = R<sub>d</sub> = 2.751KΩ <br> 
 Overall gain : A<sub>v</sub> = gm * R<sub>out</sub>  <br>
 &nbsp;&nbsp;&nbsp; = 1.84 * 2.751K = 4951.8 <br><br> 

## **<ins>AC Analysis</ins>**<br>
 <p>In this experiment, we will conduct an AC analysis to evaluate the frequency response of the circuit, including parameters such as gain, output impedance, and phase shift. By applying a small-signal AC input, we can assess how the circuit amplifies signals and how it behaves under varying frequencies.</p>
 For the same circuit, in the configure analysis select decade as type of sweep, with starting frequenciy o.1Hz and stop frequency as 1THz. <br> 
 <br>
 <br><br>
 
 
 
