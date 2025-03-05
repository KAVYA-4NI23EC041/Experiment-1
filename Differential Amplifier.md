# <ins> Differential Amplifier </ins> <br>
<p>A differential amplifier is a type of electronic amplifier that amplifies the difference between two input signals while rejecting any common-mode signals. It is a fundamental building block in analog circuits, particularly in operational amplifiers (op-amps) and communication systems.</p>
<p>Differential amplifiers process the difference between two input signals, which allows them to effectively eliminate noise or interference present in both signals. They also suppress common-mode signals, removing any DC offset and applying gain only to the desired signal, which is advantageous in integrated circuit (IC) design by eliminating the need for large DC-blocking capacitors. This subtraction feature facilitates the integration of differential amplifiers into negative feedback systems, enhancing amplifier performance.</p>

# <ins> Design Question </ins> <br>
<b> Design and analyse the differential amplifier circuit for the following specifications V<sub>dd</sub> : 2.2V, Power<=2.2mW, V<sub>incm</sub> : 1.2V, V<sub>ocm</sub> : 1.25V, V<sub>p</sub> : 0.4V. Perform DC Analysis, Transient Analysis, Frequency responce and extract the parameters</b> <br><br>
<b>Stage1</b><br>
![Image](https://github.com/user-attachments/assets/b19dea00-a71e-4385-9fe5-a39b78791d65)
<br> basic circuit for differential amplifier: <br><br>
The above circuit is Amplifier circuit with common source configuration, <br>
To measure R<sub>d</sub> value: (output load equation is) <br>
V<sub>out</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
R<sub>d</sub> = ( V<sub>dd</sub> - V<sub>out</sub> ) / I<sub>d</sub> <br>
R<sub>d</sub> = ( 2.2 - 1.25 )/1*10^-3 <br>
R<sub>d</sub> = 950Ω <br><br>
### <ins>Component details:<ins>
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
    <td> 3.81442µm</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> 0.366V</td>
</tr>
    <tr>
      <td>Resistor</td>
      <td> 950Ω</td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 2.2V</td>
    </tr>
</table> 
<br><br>

### <ins>Through DC Analysis</ins> <br> <br>

![Image](https://github.com/user-attachments/assets/99c5ca8b-2f48-4771-a26a-dfd13e5d9dcc) <br><br>
V<sub>out</sub> = 1.25V, V<sub>gs</sub> = 1.2V, V<sub>ds</sub> = 1.25V, I<sub>d</sub> = 1mA, gm = 1.7mV/V. <br><br>
gm = ( 2 * I<sub>d</sub> ) / (  V<sub>gs</sub> -  V<sub>th</sub> ) <br>
gm = ( 2 * 1m) / ( 1.2 - 0.49 ) <br>
gm = 1.71m V/V <br> <br>
### <ins> Transient Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/4e4b719d-f3be-4730-a21f-8b1c89885009) <br><br>
For the same circuit, perform the transient analysis keeping the sinusoidal voltage signal DC offset as 0.9V, and amplitude 50mV, and frequency = 1kHz <br>
And the AC amplitude as 1V.<br>
We can observe 180° phase shift in the amplified output voltage wave <br>
    Overall gain (Av) = V<sub>out</sub> / V<sub>in</sub> <br>
    = 1.45/1.2 <br>
    = 1.52 V/V <br><br>
### <ins> AC Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/68e3fd75-8909-440d-af86-380831cac9dc) <br>
From calculations: <br>
gm = 1.71m V/V <br> R<sub>d</sub> = R<sub>out</sub> = 950Ω <br>
A<sub>v</sub> = gm *  R<sub>d</sub> <br>
A<sub>v</sub> = 1.71m * 950 <br>
A<sub>v</sub> = 3.52 V/V <br> <br>
in d<sub>b</sub> = 20 * log<sub>10</sub>(  V<sub>out</sub> / V<sub>in</sub> ) <br>
= 20 * log<sub>10</sub>( 1.52 ) <br>
= 3.63V/V <br><br>
<br>
## <ins> If The Configure Is Differential Circuit ? </ins> <br><br>
<b>Stage2:</b> <br>
![Image](https://github.com/user-attachments/assets/d64a40e7-68ab-4e77-9f96-83ec610a2c8a) <br><br>
<p>The amplifier consists of two <b>MOSFETS(M1 & M2)</b> in differential pair. The drain terminals of <b>M1</b> & <b>M2</b> are connected to <b>V<sub>dd</sub></b> through <b>R<sub>d</sub></b>. The source terminals of both MOSFET is connected to common source resistor <b>R<sub>ss</sub></b> which is then connected to ground. The <b>V<sub>in1</sub></b> & <b>V<sub>in2</sub></b> with <b>1.2V (DC offset), 50mV (amplitude), 1kHz (frequency) </b> and for any one input signal apply a phase shift of <b>180°</b> are applied to gates of <b>M1</b> & <b>M2</b>. </p>

We assume, the circuit has identical components that is R<sub>d1</sub> = R<sub>d2</sub> = R<sub>d</sub>. <br>
V<sub>incm</sub> = V<sub>in1</sub> = V<sub>in2</sub> <br> <br>
<b> <ins> Calculation </ins> </b> <br><br>
I<sub>ss</sub> = P / V<sub>dd</sub> = 2.2m / 2.2 = 1mA. <br>
I<sub>d</sub> = I<sub>ss</sub> / 2 = 1m / 2 = 0.5mA.<br>
V<sub>out</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
R<sub>d</sub> =  ( V<sub>dd</sub> - V<sub>out</sub> ) / I<sub>d</sub> <br>
= (2.2 -1.25)/0.5m <br>
= 1.9KΩ <br><br> 
V<sub>p</sub> = ( I<sub>ss</sub> * R<sub>ss</sub> ) <br>
R<sub>ss</sub> = V<sub>p</sub> / I<sub>ss</sub> <br>
= 0.4 / 1m <br>
= 400Ω <br><br> 
### <ins>Circuite Parameters:</ins> <br>

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
    <td> 6.4125µm</td>
</tr>
<tr>
    <td>Threshold Voltage(V<sub>th</sub>)</td>
    <td> 0.366V</td>
</tr>
    <tr>
      <td>Resistor(R<sub>d</sub>)</td>
      <td> 1.9KΩ</td>
    </tr>
    <tr>
      <td>Resistor(R<sub>ss</sub>)</td>
      <td> 400Ω</td>
    </tr>
    <tr>
      <td>Resistor(V<sub>p</sub>)</td>
      <td> 1.9KΩ</td>
    </tr>
    <tr>
      <td>Supply Voltage(V<sub>dd</sub>)</td>
      <td> 2.2V</td>
    </tr>
</table> 

### <ins> Through DC Analysis </ins> <br> <br>
![Image](https://github.com/user-attachments/assets/b0976b64-bb62-4d12-aaeb-9f446e675842) <br> Voltage List <br> <br>
![Image](https://github.com/user-attachments/assets/dd896d06-ee23-4136-b728-f5e58dcc1876)<br> Current List <br><br>

From diagram we can observe: <br>
V<sub>out1</sub> = V<sub>out2</sub> = 1.25V <br>, I<sub>d1</sub> = I<sub>d2</sub> = 0.5mA, I<sub>ss</sub> = 1mA. <br> <br>
In the above circuit V<sub>g</sub> = V<sub>in</sub> = 1.2V, V<sub>s</sub> = V<sub>p</sub> = 0.4V. <br><br>
<b> Through ERROR LOG </b> <br><br>
![Image](https://github.com/user-attachments/assets/1f936627-7a2c-4653-b706-ebd56610f244) <br><br>
Obtained V<sub>gs</sub> = 0.8V, V<sub>ds</sub> = 0.85V, V<sub>th</sub> = 0.495V,
I<sub>d</sub> = 0.5mA. <br><br>




 
