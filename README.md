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
 &nbsp;&nbsp;&nbsp; = (1.83*10<sup>-4</sup>) * 2.751K = 4.9V/V <br><br> 

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
&nbsp;&nbsp;&nbsp;&nbsp; = 4.1d<sub>B</sub> - 3d<sub>B</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp; = 1.1d<sub>B</sub> <br><br>

## **What if the resistor is replaced by a PMOS?** <br>
 <p>The circuit consists of a PMOS and an NMOS transistor connected in a complementary configuration, operating at a supply voltage of 1.8V. The purpose of this design is to analyze its DC, transient, and AC responses to evaluate its frequency response.</p>

 ### <ins> Design Specifications </ins>
<table>
  <tr>
  <th> Parameters </th>
  <th> Description </th>
  </tr>
  <tr> 
  <td>Model</td>
    <td> CMOSN, CMOSP</td>
  </tr>
  <tr>
    <td>Supply Voltage</td>
    <td> 1.8V</td>
  </tr>
  <tr>
    <td> PMOS</td>
    <td> Acts as the pull up  network</td>
  </tr>
  <tr>
    <td> NMOS</td>
    <td> Acts as the pull down network</td>
  </tr>
  <tr>
    <td>V<sub>tp</sub></td>
    <td>-0.39V</td>
  </tr>
  <tr>
    <td>V<sub>tn</sub></td>
    <td>0.36V</td>
  </tr>
  <tr>
    <td> PMOS Length</td>
    <td> 180µm</td>
  </tr>
  <tr>
    <td> NMOS Length</td>
    <td> 180nm</td>
  </tr>
  <tr>
    <td> PMOS Width</td>
    <td> 0.209513mm</td>
  </tr>
  <tr>
    <td> NMOS Width</td>
    <td> 0.209µm</td>
  </tr>
  <tr>
    <td> 𝜇<sub>n</sub></td>
    <td> 273.809 m<sup>2</sup>/V</td>
  </tr>
  <tr>
    <td>𝜇<sub>p</sub></td>
    <td> 115.689 m<sup>2</sup>/V</td>
  </tr>
  <tr>
    <td> T<sub>oxn</sub>, T<sub>oxp</sub></td>
    <td> 4.1*10<sup>-9</sup>m</td>
  </tr>
  <tr>
    <td>𝜀<sub>ox</sub></td>
    <td> 3.45*10<sup>-11</sup> F/m</td>
  </tr>
</table> <br>

<ins> **Circuit Diagram** </ins> <br>

![Image](https://github.com/user-attachments/assets/2b65b9d3-ce13-47b6-a735-0a1275f93a65) <br>
The body terminal of both NMOS and PMOS is connect to drain terminal. <br><br>
To find the value of biased voltage: <br>
  We know that current flowing through the NMOS and PMOS is the equal; i.e I<sub>dn</sub> = I<sub>dp</sub> <br><br>
  <ins> Calculation: </ins> <br>
  <p> (1/2 * k<sub>n</sub> * (V<sub>gs</sub> - V<sub>tn</sub>)<sup>2</sup> ) = (1/2 *  k<sub>p</sub> * (V<sub>dd</sub> - V<sub>bias</sub> - |V<sub>tp</sub>|)<sup>2</sup> ) <br>
  C<sub>oxn</sub> =  C<sub>oxp</sub> = 3.45*10<sup>-11</sup> /  4.1*10<sup>-9</sup> = 8.41*10<sup>-3</sup> F/m <br>
    k<sub>n</sub> = 273.809 *  8.41*10<sup>-3</sup> = 2.303 A/V<sup>2</sup> <br>
    k<sub>p</sub> = 115.689 *  8.41*10<sup>-3</sup> = 0.973 A/V<sup>2</sup> <br>
  (0.5 * 2.303 * (0.209153µ / 180n) * (0.9 -0.366)<sup>2</sup> )= (0.5 * 0.973 * (0.209µ / 180n) * ( 1.8 - V<sub>dd</sub> - 0.39)<sup>2</sup> ) <br>
  0.373 = 0.54 * ( 1.8 - V<sub>dd</sub> - 0.39)<sup>2</sup> ) <br>
  $\sqrt{0.69}$; = 1.8 - 0.39 - V<sub>bias</sub> <br>
  0.83 = 1.41 - V<sub>bias</sub> <br>
  V<sub>bias</sub> = 0.58V 
</p> 

## <ins> **DC Analysis** </ins> <br><br>
<ins> **Circuit Diagram** </ins> <br>
![Image](https://github.com/user-attachments/assets/67ce6ef4-b3d3-4a7b-9860-db4d82e19c26) <br>

From the simulation : <br>
V<sub>out</sub> = 1.42V, I<sub>d</sub> = 8.9µA <br>
we should check whether both transistor are in saturation region:<br><br>
PMOS: V<sub>sd</sub> = V<sub>s</sub> - V<sub>d<sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 1.8 - 0.69 = 1.11V <br> 
V<sub>sg</sub> = V<sub>s</sub> - V<sub>g<sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 1.8 - 0.58 = 1.22V <br>
 V<sub>sd</sub> >= V<sub>sg</sub> - V<sub>th</sub> <br> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1.11V >= 1.22 - 0.39 <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1.11V >= 0.83V <br>
 It satisfies the condition <br><br>
 NMOS:  V<sub>ds</sub> = V<sub>d</sub> - V<sub>s</sub> <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 0.69 - 0 = 0.69V <br>
 V<sub>gs</sub> = V<sub>g</sub> - V<sub>s</sub> <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 0.9 - 0 = 0.9V <br>
 V<sub>ds</sub> >= V<sub>gs</sub> - V<sub>th</sub> <br> 
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0.69 >= 0.9 - 0.366 <br>
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0.69V >= 0.54V <br>
It satisfies the condition
<br><br>
## <ins> **Transient Analysis** </ins> <br><br>
<ins> **Circuit Diagram** </ins> <br>
![Image](https://github.com/user-attachments/assets/8d2a1568-ada1-43b3-8ab1-e359ed96ddab) <br><br>

we cann observe the 180° phase shift in the amplified output wave <br>
gain A<sub>v</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
=2.5 V/V <br><br>
From Calculations: <br>
gm = 2(I<sub>d</sub>) / V<sub>ov</sub> <br>
   = 2(8.93*10<sup>-6</sup>) / ((1.8-0.58) - 0.39) <br>
   = 2.15*10<sup>-5</sup> V/V <br><br>
   
## <ins> **AC Analysis** </ins> <br><br>
<ins> **Circuit Diagram** </ins> <br>
![Image](https://github.com/user-attachments/assets/290d8fc7-cefd-4052-9d35-2b58f015f2b3) <br>

From the graph: <br>
V<sub>out</sub> / V<sub>in</sub> = 2.5 V/V <br>
in d<sub>b</sub> = 20*log<sub>10</sub>(V<sub>out</sub> / V<sub>in</sub>) <br>
= 20*log<sub>10</sub>(2.5) <br>
=7.95 V/V

<ins> **Inference:** </ins> <br>
<p>From circuit 1 (resistive load common source amplifier ) resistor is replaced by PMOS transistor in circuit 2 (active load common source amplifier) <br><br>
  Outcomes: <br>
  -> The PMOS acts as an active load, providing a higher small-signal resistance compared to a passive resistor. This results in a higher voltage gain for the circuit. <br>
  -> The PMOS transistor operates in saturation, offering better linearity and dynamic range than a fixed resistor. <br>
  -> The PMOS requires a proper bias voltage (Vb = 0.58V) at its gate to ensure it remains in saturation. <br>
  -> In intigrated circuits, replacing the resistor by PMOS reduces the space. <br>
  -> Circuit 1 is simple and easy to design, but circuit 2 is complex as you must require a proper biasing voltage (V<sub>b</sub>). <br>
  -> As the resistor responsible for introducing paracitic capacitor, which limits the frequency response. But PMOS helps to have high gain with wide range of frequency. <br>
  -> Gain in the first circuit is 5.1 V/V and second circuit is 7.95 V/V <br>
 </p>
 
