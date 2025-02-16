# Experiment-1

## **DC,AC,Transient Analysis of Common Source Amplifier** <br>
<p>The Common Source (CS) Amplifier is a fundamental building block in analog circuit design, widely used for voltage amplification. In this circuit, an NMOS transistor operates as the active device, with a passive resistor (R<sub>d</sub>) as the load. The circuit is biased using a DC voltage source (V<sub>d</sub>), and an AC input signal is applied to the gate.</p> 
<p> <ins>Key components and their roles:</ins> <br><br>
1. R<sub>d</sub> (Drain Resistor): Provides the required voltage drop to amplify the signal. <br>
2. W (Transistor Width): Affects the transconductance (gm), influencing gain and bandwidth.<br>
3. V<sub>dd</sub> (Drain Supply Voltage): Provides DC biasing for the NMOS transistor. <br>
4. AC Input (SINE source): The test signal used to analyze circuit response. </p>

<ins>**Circuit diagram:** </ins> <br>

![Image](https://github.com/user-attachments/assets/d1eddf4d-5823-43fa-805d-59d048a61441)

<p>This report presents the DC analysis, AC analysis, Transient analysis of a common-source NMOS amplifier. The objective of this analysis is to determine the DC biasing conditions, gain and output impedence using Transient analysis, and to find frequency response using AC analysis.</p>

### **<ins>Component Details</ins>**
  <p>  The circuit consists of a TSMC 180nm NMOS transistor (CMOSN), a drain resistor and two voltage sources. The drain resistor limits the current through the transistor and affects the small-signal gain. The NMOS transistor operates in saturation region, making it suitable for amplification </p>
  
  <table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>Value</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>180nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>0.209513µm</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> 0.366V</td>
</tr>
    <tr>
      <td>Resistor</td>
      <td> 2.751kΩ</td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
    </tr>
</table> 
<br>

**Signal Genertor**&nbsp;&nbsp;&nbsp;&nbsp;: <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1. DC Voltage: 0.9V <br> 
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2. Amplitude: 50mV <br>
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3. Frequency: 1kHz <br> 

## **<ins>DC Simulation</ins>**
 <br>
 
<ins> **Circuit diagram:** </ins> <br>
![Image](https://github.com/user-attachments/assets/506240ae-f9d3-4c51-b156-105e670a6af2) <br>
<p> From the simulation: <br>
V<sub>out</sub> = 1.64727V, V<sub>in</sub> = 0.9V, I<sub>d</sub> = 0.00015A.
</p>
If the Power dissipation is 100µW across the resistor, then the current through the resistor is given by: <br>
<p>I<sub>d</sub> = Power/Voltage
              = 100µ / 1.8 
              = 55.5µA </p>
              <br>
<p>The output load line equation is given by <br>
 V<sub>out</sub> = V<sub>dd</sub> - (I<sub>d</sub> * R<sub>d</sub>) <br>
 R<sub>d</sub> = (V<sub>dd</sub> - V<sub>out</sub>) / I<sub>d</sub>  <br>
&nbsp;&nbsp;&nbsp; = (1.8 - 1.647)/55.5µ <br>
&nbsp;&nbsp;&nbsp;= 2.751k&#8486 </p>
<br>
Now replace the resistor value by R<sub>d</sub> = 2.751891k&#8486 <br><br>
Since the calculated current does not match the simulated value, maintain the MOSFET length at 180nm and adjust the width to achieve the desired current value.<br><br>

<ins> **Observation Table:** </ins>  <br>
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
<br><br>
The DC operating point analysis confirms that the NMOS transistor operates in the saturation region with I<sub>d</sub> ≈ 55.5μA. <br>
V<sub>ds</sub> = V<sub>out</sub> = 0.1647V <br>
V<sub>ov</sub> = V<sub>gs</sub> - V<sub>th</sub>  = 0.9 - 0.36  = 0.54V <br>
i.e V<sub>ds</sub> > ( V<sub>gs</sub> - V<sub>th</sub>) <br>
<br>

## **<ins>Transient Analysis</ins>** <br>
Transient analysis is a time-domain simulation technique used to observe the circuit's response to time-varying inputs.<br> For this experiment find the gain and output impedence of the circuit.<br>
For the same circuit, perform the transient analysis keeping the sinusoidal voltage signal DC offset as 0.9V, and amplitude 50mV, and frequency = 1kHz <br>
And the AC amplitude as 1V. <br>
In the configure analysis select stop time as 5ms. <br><br>

<ins> **Circuit diagram:** </ins> <br>
![Image](https://github.com/user-attachments/assets/248274f7-e1f2-401a-ad52-6181a2053d9e) <br>
From the graph: <br>
 We can observe **180&deg;** phase shift in the amplified output voltage wave  <br>
&nbsp;&nbsp;&nbsp; Overall gain (A<sub>v</sub>) = V<sub>out</sub> / V<sub>in</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 1.66/0.9  = 1.84 <br>
<br>
From calculations: <br>
 gm = 2(I<sub>d</sub>)/(V<sub>ov</sub>)  &nbsp;&nbsp;&nbsp; i.e  V<sub>ov</sub> = V<sub>gs</sub> - V<sub>th</sub>  <br>
 &nbsp;&nbsp; = 2(55.5μ) / ( 0.9 - 0.3) <br>
 &nbsp;&nbsp; = 1.83*10<sup>-4</sup> <br><br>
 R<sub>out</sub> = R<sub>d</sub> = 2.751KΩ <br> 
 Overall gain : A<sub>v</sub> = gm * R<sub>out</sub>  <br>
 &nbsp;&nbsp;&nbsp; = (1.83*10<sup>-4</sup>) * 2.751K = 4.9 <br><br> 

## **<ins>AC Analysis</ins>**<br>
 <p>In this experiment, we will conduct an AC analysis to evaluate the frequency response of the circuit, including parameters such as gain, output impedance, and phase shift. By applying a small-signal AC input, we can assess how the circuit amplifies signals and how it behaves under varying frequencies.</p>
 For the same circuit, in the configure analysis select decade as type of sweep, with starting frequenciy o.1Hz and stop frequency as 1THz. <br> <br>

<ins> **Circuit diagram** </ins> <br>
![Image](https://github.com/user-attachments/assets/6e4d68c5-bf91-482c-b0d7-9e39a4925489)
<br> 
Voltage gain = V<sub>out</sub> / V<sub>in</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp; = 1.6 / 0.9 = 1.84 <br>
in d<sub>B</sub> = 20*log<sub>10</sub>(V<sub>out</sub> / V<sub>in</sub>) <br>
&nbsp;&nbsp;&nbsp;&nbsp; = 20*log<sub>10</sub>(1.84) <br>
&nbsp;&nbsp;&nbsp;&nbsp; = 5.1d<sub>B</sub> - 3d<sub>B</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp; = 2.1d<sub>B</sub> <br><br>
 
<ins> **Inference:** </ins> <br>
<p>1) <ins> DC Analysis: </ins> <br>
-> The transistor is working correctly in the saturation region, which is needed for amplification. <br>
-> The current flowing through the circuit is 55.5µA, and the resistor value 2.751kΩ is verified. <br>
-> The output voltage is around 1.647V, and the input voltage is 0.9V. <br>
-> The transistor is properly biased for amplification. <br></p>
<p>2) <ns> Transient Analysis: </ns> <br>
-> The output signal is amplified and flipped by 180° (inverted), which is expected in a Common Source amplifier. <br>
-> The gain of the circuit is around 1.84, meaning the output is almost twice the input.<br>
-> The circuit has an output resistance of 2.751kΩ, affecting how it drives the next stage in a system.<br> </p>
 <p>3) <ins> AC Analysis: </ins> <br>
-> The circuit maintains a stable gain over different frequencies, proving it works well for amplification. <br>
-> The voltage gain is 1.84 (or 5.1 dB), and the -3 dB point (where gain drops) confirms its frequency limits.<br>
-> Simulation and theoretical results are in close agreement, with minor variations due to parasitic effects.<br>
 </p>
 
