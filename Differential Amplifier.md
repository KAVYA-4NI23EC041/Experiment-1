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
in d<sub>B</sub> = 20 * log<sub>10</sub>(  V<sub>out</sub> / V<sub>in</sub> ) <br>
= 20 * log<sub>10</sub>( 1.52 ) <br>
= 3.63 dB <br><br>
<br>

## <ins> If The Configure Is Differential Circuit With Resistive Load ? (Resistor Loaded Differential Pair) </ins> <br><br>
<b>Stage2:</b> <br>
![Image](https://github.com/user-attachments/assets/d64a40e7-68ab-4e77-9f96-83ec610a2c8a) <br><br>
<p>The amplifier consists of two <b>MOSFETS(M1 & M2)</b> in differential pair. The drain terminals of <b>M1</b> & <b>M2</b> are connected to <b>V<sub>dd</sub></b> through <b>R<sub>d</sub></b>. The source terminals of both MOSFET is connected to common source resistor <b>R<sub>ss</sub></b> which is then connected to ground. The <b>V<sub>in1</sub></b> & <b>V<sub>in2</sub></b> with <b>1.2V (DC offset), 50mV (amplitude), 1kHz (frequency) </b> and for any one input signal apply a phase shift of <b>180°</b> are applied to gates of <b>M1</b> & <b>M2</b>. </p>

We assume, the circuit has identical components that is R<sub>d1</sub> = R<sub>d2</sub> = R<sub>d</sub>. <br>
V<sub>incm</sub> = V<sub>in1</sub> = V<sub>in2</sub> <br> <br>
<b> <ins> Calculation </ins> </b> <br><br>
<b> To calculate Current </b> <br>
I<sub>ss</sub> = P / V<sub>dd</sub> = 2.2m / 2.2 = 1mA. <br>
I<sub>d</sub> = I<sub>ss</sub> / 2 = 1m / 2 = 0.5mA.<br><br>
<b> To find Drain Resistor  </b> <br>
V<sub>out</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
R<sub>d</sub> =  ( V<sub>dd</sub> - V<sub>out</sub> ) / I<sub>d</sub> <br>
= (2.2 -1.25)/0.5m <br>
= 1.9KΩ <br><br> 
<b> To find Source Resistor </b> <br>
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

From result we can observe: <br>
V<sub>out1</sub> = V<sub>out2</sub> = 1.25V <br>, I<sub>d1</sub> = I<sub>d2</sub> = 0.5mA, I<sub>ss</sub> = 1mA. <br> <br>
In the above circuit V<sub>g</sub> = V<sub>in</sub> = 1.2V, V<sub>s</sub> = V<sub>p</sub> = 0.4V. <br><br>

<b><ins> From ERROR LOG</ins> </b> <br><br>
![Image](https://github.com/user-attachments/assets/1f936627-7a2c-4653-b706-ebd56610f244) <br><br>
Obtained V<sub>gs</sub> = 0.8V, V<sub>ds</sub> = 0.85V, V<sub>th</sub> = 0.495V,
I<sub>d</sub> = 0.5mA. <br><br>
<b> V<sub>ds</sub> > V<sub>gs</sub> - V<sub>th</sub> </b> <br>
 <b>Hence the mosfet operates in saturation region</b>
   <br><p> The circuit functions as a high-gain amplifier. Operating in saturation enhances CMRR, helping to reject noise and unwanted common-mode signals. The total tail current (sum of both MOSFET drain currents) remains nearly constant, ensuring symmetrical operation.
Any increase in current through one MOSFET is balanced by a decrease in the other.</p> 
The Q-point ( V<sub>ds</sub> , I<sub>d</sub> ) = ( 0.85V , 0.5mA ) <br><br>

### <ins>Transient Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/f3512313-b58e-4378-8dfa-c6021d8e712e) <br><br>
V<sub>out(p-p)</sub> = 1.44 + 1.05 = 2.49V <br>
The output peak to peak voltage is same for both +ve and -ve half cycle ( both MOSFETS ) <br><br>

### <ins> AC Analysis </ins> <br><br> 
![Image](https://github.com/user-attachments/assets/32114f2d-e14c-4e21-b33a-3d42bf6011c1) <br><br>
The observed gain is 12.1dB <br><br>
![Image](https://github.com/user-attachments/assets/10f98eab-6959-4172-b5be-c785269c7122) <br><br>
Find gain through calcultion: <br>
A<sub>v</sub> = ( V<sub>out1</sub> - V<sub>out2</sub> ) / ( V<sub>in1</sub> - V<sub>in2</sub> ) <br>
= 399.759 / 99.4 <br>
= 4.015 V/V <br>
<b> In dB = 20*log<sub>10</sub> (4.015) </b> <br>
= 12.07 dB <br><br>
<b> To find the bandwidth: </b> <br>
12.12 dB - 3 dB = 9.12 dB <br>
The frequency for gain 9.12 dB is 21.7GHz <br>
Bandwidth = High frequency - Low frequency <br>
= 21.7GHz - 0Hz = 21.7GHz <br>
A bandwidth of 21.7 GHz means the amplifier can process high-frequency signals efficiently.<br><br>
<b> We can observe the increase in gain from stage 1 circuit. </b> <br><br>

### If there is difference in input voltages ? <br><br>
<b> a) When V<sub>in1</sub> > V<sub>in2</sub> </b> <br><br>
![Image](https://github.com/user-attachments/assets/432c463b-746e-4335-9f63-a20d6870722e) <br><br>
In the above circuit, the V<sub>incm1</sub> = 1.2V , V<sub>incm2</sub> = 0.5V with same amplitude and frequency.<br>
we can observe V<sub>out1</sub> = 0.811V and V<sub>out2</sub> = 2.19V nealy equal to V<sub>dd</sub>. <br><br>
<b> b) When V<sub>in1</sub> < V<sub>in2</sub> </b> <br><br>
![Image](https://github.com/user-attachments/assets/ac1a2cb4-0b7a-486f-9f98-2242af55cc9b) <br> <br>
From the above circuit, the V<sub>incm1</sub> = 0.5V , V<sub>incm2</sub> = 1.2V with same amplitude and frequency.<br>
we can observe V<sub>out2</sub> = 0.811V and V<sub>out1</sub> = 2.19V nealy equal to V<sub>dd</sub>. <br><br>
To make this circuit to work as a linear amplifier, the difference between input voltages must be very less. <br>
![Image](https://github.com/user-attachments/assets/b0417d60-1d51-4a63-8a36-67490e3ee145) <br><br>

<ins>Lets Check the input and output voltage swing of the circuit </ins> <br><br>
V<sub>incm(min)</sub> = V<sub>th</sub> + V<sub>p</sub> <br>
= 0.366 + 0.4 <br>
= 0.766 V <br><br>
V<sub>incm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) + V<sub>th</sub> <br>
= 2.2 - ( 0.5m * 1.9K ) + 0.366 <br>
= 1.616 V <br><br>
V<sub>ocm(min)</sub> = V<sub>ov1</sub> + V<sub>p</sub>   <br>
= V<sub>gs</sub> - V<sub>th</sub> +V<sub>p</sub>  <br>
= 0.8 - 0.36 + 0.4 <br>
= 0.84 V <br><br>
V<sub>ocm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
= 2.2 - ( 0.5m * 1.9K) <br>
= 1.25V <br><br>

<b><ins> Lets check in Transient Analysis</ins> </b> <br><br>
<b> When amplitude is 50mV </b> <br>
a) When V<sub>incm</sub> = 0.5V ( <0.76V (V<sub>incm(min)</sub>) ) <br>
![Image](https://github.com/user-attachments/assets/430a8713-021b-4a0c-a6dd-3f02f83996d8) <br><br>
![Image](https://github.com/user-attachments/assets/297a3164-a022-449a-a5d6-d88636f8deb2) <br><br>
From simulation we can observe <b> V<sub>ds</sub> < V<sub>gs</sub> - V<sub>th</sub> and  V<sub>gs</sub> <  V<sub>th</sub> </b> <br>
Can see the ac analysis of this circuit, which is in negative <br><br>
![Image](https://github.com/user-attachments/assets/52a0012f-1c24-47e3-af23-d539c6d55b81) <br><br>
The circuit operates in <b> Cut-off region </b> hence the output wave is not symmetrical. <br><br>
b) When V<sub>incm</sub> = 1.7V ( >1.616V (V<sub>incm(max)</sub>) ) <br> 
![Image](https://github.com/user-attachments/assets/fcf69a7a-9a12-4c80-9523-a8e4bea2c79b) <br><br> 
![Image](https://github.com/user-attachments/assets/62a130da-f6a8-41e1-9904-b6aa6e8bbdd8) <br><br> 
From simulation we can observe <b> V<sub>ds</sub> < V<sub>gs</sub> - V<sub>th</sub> and  V<sub>gs</sub> >  V<sub>th</sub> </b> <br>
Can observe in ac analysis which has a negative gain <br><br> 
![Image](https://github.com/user-attachments/assets/0ed91fd2-ceac-42cf-b764-8bc7ec9cdbfc) <br><br> 
The circuit operates in <b> Triode region </b> hence the output is not symmetrical. <br><br>


## If R<sub>ss</sub> is replaced by current source ? (Current Source Loaded Differential Pair) <br><br>
![Image](https://github.com/user-attachments/assets/b61f3fbd-3c20-45b9-a29f-dc6d40e13889) <br><br>
Replacing R<sub>ss</sub> with a current source improves gain, CMRR, and stability, making the circuit better for high-performance analog applications, such as op-amps, ADC front ends, and RF systems.Since the total current remains constant, hencs if there is difference in current they are balanced finally. <br> <br>

### <ins> DC Analysis </ins> <br>
![Image](https://github.com/user-attachments/assets/967cc97f-4afc-4a1a-b0f5-b4df1ac28bcf) <br><br>
Through DC Analysis we can conclude that theere is no much difference between resistor load differential pair circuit and current source loaded differential pair circuit. <br>
<b><ins> Error Log </ins></b> <br>
![Image](https://github.com/user-attachments/assets/14a9b40c-28a5-47e2-ab93-65235d4a7aae) <br><br>
The circuit has V<sub>gs</sub> = 0.8V, V<sub>ds</sub> = 0.85V, with I<sub>d</sub> = 0.5mA.<br>
<b> V<sub>ds</sub> > V<sub>gs</sub> - V<sub>th</sub> <br>
 Hence the circuit is in saturation region. </b> <br> 
 The Q-point is ( V<sub>ds</sub> , I<sub>d</sub> ) = ( 0.85V , 0.5mA ) <br><br>
 
 ### <ins> Transient Analysis </ins> <br>
 ![Image](https://github.com/user-attachments/assets/d38a3475-84b7-4877-ba8f-30e5a9d6dacd) <br><br>
 V<sub>out(p-p)</sub> = 1.44 + 1.05 = 2.49V <br>
 The output voltage is same for both +ve and -ve half cycle, and is equal to resistive load circuit. <br><br>
 
 ### <ins> AC Analysis </ins> <br>
![Image](https://github.com/user-attachments/assets/63b3135a-50ce-4d62-a81f-5c0570ca82a0) <br><br>
The observed gain is 12.12 dB. <br><br>
![Image](https://github.com/user-attachments/assets/5dcaf70b-2564-4ef9-a1e4-c1c3d416c8dc) <br><br>
Find gain through calcultion: <br>
A<sub>v</sub> = ( V<sub>out1</sub> - V<sub>out2</sub> ) / ( V<sub>in1</sub> - V<sub>in2</sub> ) <br>
= 399.559 / 99.1 <br>
= 4.035 V/V <br>
In dB = 20*log<sub>10</sub> (4.035) <br>
= 12.116 dB <br><br>
<b>To find the bandwidth: </b> <br>
12.12 dB - 3 dB = 9.12 dB <br>
The frequency for gain 9,12 dB is 21.7GHz <br>
Bandwidth = High frequency - Low frequency <br>
= 21.7GHz - 0Hz = 21.7GHz <br>
A bandwidth of 21.7 GHz means the amplifier can process high-frequency signals efficiently. <br> 
<b> The gain is almost equal to resistive load differential amplifier. </b> <br><br>

<ins>Lets Check the input and output voltage swing of the circuit </ins> <br><br>
V<sub>incm(min)</sub> = V<sub>th</sub> + V<sub>p</sub> <br>
= 0.366 + 0.4 <br>
= 0.766 V <br><br>
V<sub>incm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) + V<sub>th</sub> <br>
= 2.2 - ( 0.5m * 1.9K ) + 0.366 <br>
= 1.616 V <br><br>
V<sub>ocm(min)</sub> = V<sub>ov1</sub> + V<sub>ov3</sub>   <br>
= V<sub>gs1</sub> - V<sub>th1</sub> +V<sub>p</sub>  <br>
= 0.8 - 0.36 + 0.4 <br>
= 0.84 V <br><br>
V<sub>ocm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
= 2.2 - ( 0.5m * 1.9K) <br>
= 1.25V <br><br> 

### <ins> If Current Source Is Replaced By Mosfet? ( Mosfet a Current Source ) </ins> <br><br>
<p>The tail current source (previously an ideal current source) is replaced by an NMOS transistor operating in the saturation region. The gate of this MOSFET is biased with a fixed voltage to set a constant drain current.The MOSFET acts as an active current source, providing a nearly constant tail current. The differential pair MOSFETs share this tail current, adjusting their drain currents based on the input difference. Common-mode signals are rejected, as the tail MOSFET prevents variations in total current.</p> 

### <ins> DC Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/ca9b4a8c-0cd4-4779-b4e5-fffa2e4844fb) <br><br>
<ins> <b> Error Log </b> </ins> <br>
![Image](https://github.com/user-attachments/assets/cde21af9-6298-4fcb-b60d-5358a84c1062) <br><br>

### <ins> Transient Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/2ebe18dc-e63b-45cb-83d4-d5dca3ce8034) <br><br>
<ins>Calculate Gain<ins> <br>
![Image](https://github.com/user-attachments/assets/67c54a25-1570-43d3-b659-6ff04716e3fe) <br><br>

### <ins> AC Analysis </ins> <br><br> 
![Image](https://github.com/user-attachments/assets/340707d5-3061-4cb6-9f24-99dc1578233d) <br><br>

<b> <ins> Check Voltage Swing </ins> </b> <br>
V<sub>incm(min)</sub> = V<sub>th</sub> + V<sub>p</sub> <br>
= 0.495 + 0.4 <br>
= 0.896 V <br><br>
V<sub>incm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) + V<sub>th</sub> <br>
= 2.2 - ( 0.5m * 1.9K ) + 0.495 <br>
= 1.745 V <br><br>
V<sub>ocm(min)</sub> = V<sub>ov1</sub> + V<sub>ov3</sub>   <br>
= ( V<sub>gs1</sub> - V<sub>th</sub> ) + ( V<sub>gs3</sub> - V<sub>th</sub> ) <br>
= ( 0.895 - 0.498 ) +  ( 0.8 - 0.495 ) <br>
= 0.702 V <br><br>
V<sub>ocm(max)</sub> = V<sub>dd</sub> - ( I<sub>d</sub> * R<sub>d</sub> ) <br>
= 2.2 - ( 0.5m * 1.9K) <br>
= 1.25 V <br><br>

<ins> Lets check in Transient Analysis </ins> <br>
<b> When amplitude is 50mV </b> <br>
a) When V<sub>incm</sub> = 0.3V ( <0.895V (V<sub>incm(min)</sub>) ) <br>
<b> <ins>DC Values</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/5faa56b5-03d4-417b-9b91-37dcd6c741ee) <br><br>
<b> <ins>Transient Analysis</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/9ebe9570-6688-479b-bb99-fb5d6598f421) <br><br>
<b> <ins>AC Analysis</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/052b7635-26e9-4612-85dd-813b8879aba4) <br><br>
b) When V<sub>incm</sub> = 1.8V ( >1.745V (V<sub>incm(max)</sub>) ) <br> 
<b> <ins>DC Values</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/0068b21d-bfda-4f6b-84ea-30a7aeee8fa1) <br><br>
<b> <ins>Transient Analysis</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/3928cee9-7d7c-4956-b2ea-d04bf8fddac6) <br><br>
<b> <ins>AC Analysis</ins> </b> <br>
![Image](https://github.com/user-attachments/assets/58e2db20-ef5b-48a8-b5fa-b19e1abfe314) <br><br>

## <ins> If Drain Resistors Is Replaced By P-Mosfet ? ( Differential Amplifier With Curent Mirror Circuit ) <br><br>
<p>This is a differential amplifier with a current mirror load. It consists of two NMOS transistors forming the differential pair and two PMOS transistors acting as a current mirror. The tail current source (NMOS) sets the bias current for the differential pair.When a differential input (V_in1 - V_in2) is applied, the current is steered between the two NMOS transistors. The current mirror reflects the current to provide a high output impedance, increasing gain.</p>

### <ins> DC Analysis </ins> <br>






 
