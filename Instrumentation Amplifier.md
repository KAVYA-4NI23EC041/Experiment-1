# <ins>Instrumentation Ampliier </ins>
<p>An instrumentation amplifier is an essential integrated circuit (IC) designed for signal amplification. As a type of differential amplifier, it enhances the difference between two inputs while effectively reducing unwanted noise. The Common-Mode Rejection Ratio (CMRR) is a critical characteristic that indicates the amplifier’s ability to reject noise. With features like high CMRR, high open-loop gain, minimal drift, and low DC offset, instrumentation amplifiers are vital for precise circuit design.</p>

---

### <ins> Why Instrumentation Amplifier? </ins> 
* Inputs to the instrumentation amplifiers will have very low signal energy. Therefore the instrumentation amplifier should have high gain and should be accurate. <br>
* The gain should be easily adjustable using a single control.<br>
* It must have High Input Impedance and Low Output Impedance to prevent loading. <br>
* The Instrumentation amplifier should have High CMRR since the transducer output will usually contain common mode signals such as noise when transmitted over long wires. <br>
* It must also have a High Slew Rate to handle sharp rise times of events and provide a maximum undistorted output voltage swing. <br>

![Image](https://github.com/user-attachments/assets/a4036729-8892-4d93-8257-396f576a8ab7) <br><br>

---

### <ins>What is an Operational Amplifier?</ins> <br>
<p>An operational amplifier (op amp) is an analog circuit block that takes a differential voltage input and produces a single-ended voltage output. Op amps usually have three terminals: two high-impedance inputs and a low-impedance output port. The inverting input is denoted with a minus (-) sign, and the non-inverting input uses a positive (+) sign. Operational amplifiers work to amplify the voltage differential between the inputs, which is useful for a variety of analog functions including signal chain, power, and control applications.</p>

<b>Operational Amplifiers: Key Characteristics and Parameters</b> <br>
<p><b>Open-loop gain </b> refers to the gain of an operational amplifier when no feedback is used. This gain is often very high (10,000+) but is mainly useful in voltage comparators, which compare input terminal voltages and can quickly drive the output to extreme values with small voltage differences. High open-loop gains are advantageous in closed-loop configurations, promoting stability across varying conditions.</p>

![Image](https://github.com/user-attachments/assets/07c2decc-6701-4892-8389-e3094081cfd4) <br><br>

**Input Impedance**  <br>
Op amps have high input impedance (ideally infinite) to reduce source loading, influenced by circuit configuration and input capacitance.<br><br>

**Output Impedance**  <br>
Ideally zero, output impedance impacts current driving capability and voltage buffering. <br><br>

**Frequency response and bandwidth (BW)** <br>
An ideal op amp has infinite bandwidth and high gain at all frequencies. Real op amps have a finite BW, the “-3dB point,” where gain drops, decreasing at -20dB per decade. Higher BW improves performance but increases power consumption and cost. <br><br>

![Image](https://github.com/user-attachments/assets/2f4332bf-a810-4004-9397-bd1bbfbbecb3) <br><br>

**Gain Bandwidth Product (GBP)**  <br>
GBP is the product of an amplifier’s gain and bandwidth and remains constant across the curve. It can be calculated using the formula: <br>
{GBP} = {Gain}*{Bandwidth} <br>

<p>GBP is measured at the frequency where the operational amplifier's gain is unity, allowing for the calculation of open-loop gain at various frequencies. A higher GBP indicates better performance at higher frequencies, making it an essential parameter for selecting an operational amplifier. Other important factors may include input offset voltage, noise, quiescent current, and supply voltages, depending on the application.</p>

**Voltage follower** <br>
<p>The most basic operational amplifier circuit is a voltage follower (see Figure 4). This circuit does not generally require external components, and provides high input impedance and low output impedance, which makes it a useful buffer. Because the voltage input and output are equal, changes to the input produce equivalent changes to the output voltage.</p>
V<sub>out</sub> = V<sub>in</sub> <br>

![Image](https://github.com/user-attachments/assets/3f37a40b-54b2-4268-baa0-a7b05654d70f) <br>

<p>The most common op amp used in electronic devices are voltage amplifiers, which increase the output voltage magnitude. Inverting and non-inverting configurations are the two most common amplifier configurations. Both of these topologies are closed-loop (meaning that there is feedback from the output back to the input terminals), and thus voltage gain is set by a ratio of the two resistors.</p>

**Inverting operational amplifier** <br>
In inverting operational amplifiers, the op amp forces the negative terminal to equal the positive terminal, which is commonly ground. Therefore, the input current is determined by the VIN / R1 ratio <br> 

![Image](https://github.com/user-attachments/assets/764c8737-ccd5-4b42-bf65-2ee1b1ffa440) <br><br>

In this inverting configuration, current through R2 creates an inverted voltage at the op amp's negative terminal. The output can only swing between its supplies, needing a negative supply for a negative output voltage. VOUT can be calculated with <br>
V<sub>out</sub> = -(R2/R1) * V<sub>in</sub> <br><br>

**Non-inverting operational amplifier** <br>
In a non-inverting amplifier circuit, the input signal from the source is connected to the non-inverting (+) terminal <br>

![Image](https://github.com/user-attachments/assets/5d57b283-af56-44f9-925c-bacdc6874af7) <br><br>

The operational amplifier matches the inverting terminal voltage to the input, allowing current through feedback resistors. In a non-inverting amplifier, the output is in phase with the input, and the voltage gain is greater than 1.<br>
V<sub>out</sub> = (1+(R2/R1)) * V<sub>in</sub> <br><br>

---

### <ins>Internal circuitry of 741-type op amp </ins>

![Image](https://github.com/user-attachments/assets/0667ef30-fc7b-4a5d-8fe6-04fac015e77a) <br><br>

A component-level diagram of the common 741 op amp. Dotted lines outline:  <br>
<code style="color : red">Red</code> : current mirrors; <code style="color : blue">Blue</code> :  differential amplifier; <code style="color : pink">Pink</code> : class A gain stage; <code style="color : green">Green</code> : voltage level shifter; <code style="color : aqua">Aqua</code> : output stage. <p> 

---

### Instrumentation Amplifier inside IC 

![image](https://github.com/user-attachments/assets/347b5b21-ab88-4d62-af9f-06df9486dd43) <br><br> 

<ins><b>Advantages of Instrumentation Amplifier</ins></b> <br>
1.The advantages of the instrumentation amplifier include the following.<br>
2.The gain of a three op-amp instrumentation amplifier circuit can be easily varied by adjusting the value of only one resistor Rgain.<br>
3.The gain of the amplifier depends only on the external resistors used.<br>
4.The input impedance is very high due to the emitter follower configurations of amplifiers 1 and 2. <br>
5.The output impedance of the instrumentation amplifier is very low due to the difference amplifier3.<br>
6.The CMRR of the op-amp 3 is very high and almost all of the common mode signal will be rejected.<br><br>

---

<ins><b>Applications of Instrumentation Amplifier</b></ins> <br>
->These amplifiers mainly involve where the accuracy of high differential gain is required, strength must be preserved in noisy surroundings, as well as where huge common-mode signals are there. <br>
->Instrumentation amplifiers are used in data acquisition from small o/p transducers like thermocouples, strain gauges, measurements of Wheatstone bridge, etc.<br>
->These amplifiers are used in navigation, medical, radar, etc. <br>
->These amplifiers are used to enhance the S/N ratio (signal to noise) in audio applications like audio signals with low amplitude.<br>
->These amplifiers are used for imaging as well as video data acquisition in the conditioning of high-speed signal.<br>
->These amplifiers are used in RF cable systems for amplification of the high-frequency signal.<br><br>

---

<ins><b>Difference between Operational Amplifier and Instrumentation Amplifier</b></ins> <br>
1.An operational amplifier (op-amp) is one kind of an integrated circuit.<br>
2.The instrumentation amplifier is one type of differential amplifier<br>
3.Instrumentation amplifier can be built with three operational amplifiers.<br>
4.The differential amplifier can be built with a single operational amplifier.<br>
5.The output voltage of difference amplifier gets affected because of the mismatch resistors<br>
6.Instrumentation amplifier offers gain with a single resistor of its primary phase which does not need a resistor matching.<br><br>

---

## <ins>Simulation <ins> 
<p><b> Design an Instrumentation Amplifier using 3 op-am configuration with the following constraints: <br>
R1=R3=10KΩ, R2=R4=20KΩ, R5=R6=10KΩ. <br>
Calculate A<sub>DM</sub> for R<sub>G</sub> = 10Ω, 100Ω, 1KΩ, 10KΩ, 20KΩ. Find A<sub>CM</sub> and calculate CMRR for each case. Use LTspice simulation.</b></p>

![Image](https://github.com/user-attachments/assets/f702d454-f6ef-4af3-85e7-f61f5d4f2962) <br><br>

Let us assume that the input is of 0V DC offset, 1mV amplitude with frequency 1KHz. <br><br>

<ins><b>Calculations:</b></ins> <br><br>

<b> 1) When R<sub>G</sub> = 10Ω </b><br>

The Differential gain is given by: <br>
A<sub>DM</sub> = (R2/R1) x [1+(2xR5/R<sub>G</sub>)] <br>
= (20K/10K) x [1 + (2x10K / 10)] <br>
= 4002 V/V 
in dB scale = 20*log<sub>10</sub>(4002) <br>
= 72.04 dB <br><br>
![Image](https://github.com/user-attachments/assets/0a801459-b376-4bcf-b4b1-d973a2e79142) <br><br>
The obtained gain through simulation for differential mode is 72.02dB (same as theoretical). <br><br>

For Common mode gain, do the transient analysis first, to find the V<sub>out</sub> <br><br>
![Image](https://github.com/user-attachments/assets/1c41a18e-a8ae-4bdb-a79e-c3d9aa8c99c9) <br><br>
The output voltage is in nano range, 3.899nV <br>
A<sub>DM</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
= 3.899n / 1m <br>
=3.899µ V/V <br>
in dB scale = 20*log<sub>10</sub>(3.899µ) <br>
= -108.18dB <br><br>
![Image](https://github.com/user-attachments/assets/b72eced4-f9ed-43f2-9f30-c545a5be3240) <br><br>
Through simulation, we can see that at 1.01KHz the gain is equal to -108.075dB <br><br>

For A<sub>V</sub> = A<sub>DM</sub> / A<sub>CM</sub> <br>
= 4002 / 3.899µ <br>
= 1.02G V/V <br>

CMRR = 180.172dB <br><br>

---

<b> 2) When R<sub>G</sub> = 100Ω </b><br>

The Differential gain is given by: <br>
A<sub>DM</sub> = (R2/R1) x [1+(2xR5/R<sub>G</sub>)] <br>
= (20K/10K) x [1 + (2x10K / 100)] <br>
= 402 V/V 
in dB scale = 20*log<sub>10</sub>(402) <br>
= 52.08 dB <br><br>
![Image](https://github.com/user-attachments/assets/86d0c8dc-5bc0-4e40-9be8-481a023ab374) <br><br>
The obtained gain through simulation for differential mode is 52.08dB (same as theoretical). <br><br>

For Common mode gain, do the transient analysis first, to find the V<sub>out</sub> <br><br>
![Image](https://github.com/user-attachments/assets/bec39c1d-5836-4670-b175-604b0ae9516b) <br><br>
The output voltage is in nano range, 3.902nV <br>
A<sub>DM</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
= 3.902n / 1m <br>
=3.902µ V/V <br>
in dB scale = 20*log<sub>10</sub>(3.902µ) <br>
= -108.16dB <br><br>
![Image](https://github.com/user-attachments/assets/a58b91a6-bc7a-4779-ac0d-3913886a8cfa) <br><br>
Through simulation, we can see that at 1.01KHz the gain is equal to -108.06dB <br><br>

For A<sub>V</sub> = A<sub>DM</sub> / A<sub>CM</sub> <br>
= 402 / 3.902µ <br>
= 102.8M V/V <br>

CMRR = 160.23dB <br><br>

---

<b> 3) When R<sub>G</sub> = 1KΩ </b><br>

The Differential gain is given by: <br>
A<sub>DM</sub> = (R2/R1) x [1+(2xR5/R<sub>G</sub>)] <br>
= (20K/10K) x [1 + (2x10K / 1K)] <br>
= 42 V/V 
in dB scale = 20*log<sub>10</sub>(42) <br>
= 32.46 dB <br><br>
![Image](https://github.com/user-attachments/assets/79526cac-f1af-446e-af88-50140aad7058) <br><br>
The obtained gain through simulation for differential mode is 32.46dB (same as theoretical). <br><br>

For Common mode gain, do the transient analysis first, to find the V<sub>out</sub> <br><br>
![Image](https://github.com/user-attachments/assets/d0ff8bc1-878b-42dc-b17f-866ac3965589) <br><br>
The output voltage is in nano range, 3.904nV <br>
A<sub>DM</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
= 3.904n / 1m <br>
=3.904µ V/V <br>
in dB scale = 20*log<sub>10</sub>(3.904µ) <br>
= -108.161dB <br><br>
![Image](https://github.com/user-attachments/assets/e446ad30-b6f8-4a4f-aa78-32b5e0fd3b31) <br><br>
Through simulation, we can see that at 1.01KHz the gain is equal to -108.156dB <br><br>

For A<sub>V</sub> = A<sub>DM</sub> / A<sub>CM</sub> <br>
= 42 / 3.904µ <br>
= 10.75M V/V <br>

CMRR = 140.62dB <br><br>

---

<b> 4) When R<sub>G</sub> = 10KΩ </b><br>

The Differential gain is given by: <br>
A<sub>DM</sub> = (R2/R1) x [1+(2xR5/R<sub>G</sub>)] <br>
= (20K/10K) x [1 + (2x10K / 10K)] <br>
= 6 V/V 
in dB scale = 20*log<sub>10</sub>(6) <br>
= 15.56 dB <br><br>
![Image](https://github.com/user-attachments/assets/97410e0a-d495-4b4e-b043-98c8f62ea9de) <br><br>
The obtained gain through simulation for differential mode is 32.46dB (same as theoretical). <br><br>

For Common mode gain, do the transient analysis first, to find the V<sub>out</sub> <br><br>
![Image](https://github.com/user-attachments/assets/4de0ecfe-8764-48bd-bb21-5b2108575a31) <br><br>
The output voltage is in nano range, 3.906nV <br>
A<sub>DM</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
= 3.906n / 1m <br>
=3.906µ V/V <br>
in dB scale = 20*log<sub>10</sub>(3.906µ) <br>
= -108.165dB <br><br>
![Image](https://github.com/user-attachments/assets/f2e4a1b8-bed6-4093-94f6-3110e3dc8ebd)  <br><br>
Through simulation, we can see that at 1.01KHz the gain is equal to -108.19dB <br><br>

For A<sub>V</sub> = A<sub>DM</sub> / A<sub>CM</sub> <br>
= 6 / 3.906µ <br>
= 1.53M V/V <br>

CMRR = 123.72dB <br><br>

---

<b> 5) When R<sub>G</sub> = 20KΩ </b><br>

The Differential gain is given by: <br>
A<sub>DM</sub> = (R2/R1) x [1+(2xR5/R<sub>G</sub>)] <br>
= (20K/10K) x [1 + (2x10K / 20K)] <br>
= 4 V/V 
in dB scale = 20*log<sub>10</sub>(4) <br>
= 12.04 dB <br><br>
![Image](https://github.com/user-attachments/assets/5f9d8a0d-7f3a-406a-9153-1cc7d70a1976) <br><br>
The obtained gain through simulation for differential mode is 12.04dB (same as theoretical). <br><br>

For Common mode gain, do the transient analysis first, to find the V<sub>out</sub> <br><br>
![Image](https://github.com/user-attachments/assets/e3adf214-678f-4a4e-b68c-8fcbc618af3c) <br><br>
The output voltage is in nano range, 3.906nV <br>
A<sub>DM</sub> = V<sub>out</sub> / V<sub>in</sub> <br>
= 3.906n / 1m <br>
=3.906µ V/V <br>
in dB scale = 20*log<sub>10</sub>(3.906µ) <br>
= -108.165dB <br><br>
![Image](https://github.com/user-attachments/assets/80e4783f-8920-4727-9fb9-60f3d4c6e78e)  <br><br>
Through simulation, we can see that at 1.01KHz the gain is equal to -108.19dB <br><br>

For A<sub>V</sub> = A<sub>DM</sub> / A<sub>CM</sub> <br>
= 4 / 3.906µ <br>
= 1.024M V/V <br>

CMRR = 120.17dB <br><br>

---

## <ins>Comparision Table</ins>
<table>
  <tr>
    <th> R<sub>G</sub> </th>
    <th> A<sub>DM</sub> </th>
    <th> A<sub>DM</sub> dB </th>
    <th> A<sub>CM</sub> </th>
    <th> A<sub>CM</sub> dB </th>
    <th> CMRR</th>
  </tr>
  <tr>
    <td> 10Ω </td>
    <td> 4002 V/V</td>
    <td> 72.04 dB </td>
    <td> 3.899µ V/V </td>
    <td> -108.73 dB </td>
    <td> 180.172 dB</td>
  </tr>
    <tr>
    <td> 100Ω </td>
    <td> 402 V/V</td>
    <td> 52.08 dB </td>
    <td> 3.907µ V/V </td>
    <td> -108.73 dB </td>
    <td> 160.28 dB</td>
  </tr>
      <tr>
    <td> 1KΩ </td>
    <td> 42 V/V</td>
    <td> 32.46 dB </td>
    <td> 3.9079µ V/V </td>
    <td> -108.16 dB </td>
    <td> 140.62 dB</td>
  </tr>
     <tr>
    <td> 10KΩ </td>
    <td> 6 V/V</td>
    <td> 15.56 dB </td>
    <td> 3.9078µ V/V </td>
    <td> -108.1613 dB </td>
    <td> 123.72 dB</td>
  </tr>
      <tr>
    <td> 20KΩ </td>
    <td> 4 V/V</td>
    <td> 12.04 dB </td>
    <td> 3.9079µ V/V </td>
    <td> -108.16 dB </td>
    <td> 120.19 dB</td>
  </tr>
</table>

<p>The experiment successfully demonstrates how the gain of a 3-opamp instrumentation amplifier can be controlled by varying R<sub>G</sub>  decreases, the gain increases significantly. However, extremely low values (like 0Ω) lead to saturation and potential instability. Conversely, higher values (like 20kΩ) offer lower gain with better noise immunity. An optimal R<sub>G</sub>  should be chosen based on the desired amplification and the expected input signal level.</p> 

---

### <ins>When input is given in microvolts? </ins> 
<ins><b>Common Mode</b></ins> <br><br>

![Image](https://github.com/user-attachments/assets/eefdfefe-f5fc-4512-8329-38a0fb60a5e1) <br><br>

When both input signals to the instrumentation amplifier have the same DC offset of 0.5 µV and the same amplitude of 1 mV, the output remains ideally zero volts, even with high gain. <br>

This is because the amplifier only amplifies the difference between V₁ and V₂. Since both signals are identical, the differential input is zero.<br><br>
<ins>AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/c8c1b405-843f-4c61-bf53-d42d87ce1991) <br><br>

<ins><b>Differential Mode</b></ins> <br><br>
![Image](https://github.com/user-attachments/assets/d876e38c-e36c-4ccd-8ce6-4978e2c17f42) <br><br>
<p>When one input of the instrumentation amplifier receives a signal of 1 mV amplitude and the other receives 10 mV amplitude, with both signals having the same frequency and phase but a very small differential input voltage of 0.5 µV, the output is successfully amplified to 35 mV. <br><br>
  
![Image](https://github.com/user-attachments/assets/ddf93b1b-5c0d-49a8-9dc8-79194842799a)<br><br>
This confirms that the instrumentation amplifier circuit is capable of detecting and amplifying very small voltage differences (in microvolt range), even when both input signals are in the millivolt range. It also demonstrates the circuit's high gain and effective differential amplification, while rejecting common-mode components.</p>

---

### <ins>When R<sub>G</sub> is shorted? </ins> <br><br>
<ins><b> Common mode </b></ins> <br><br>
![Image](https://github.com/user-attachments/assets/293d190d-0e77-4b0a-b86f-9bd5670a98a5) <br><br> 
In the common-mode case (V₁ = V₂), the output remains ideally at zero volts, confirming the amplifier’s ability to reject common-mode signals even at high gain. This showcases its strong common-mode rejection ratio (CMRR) <br><br>
<ins><b>Differential mode</b></ins> <br><br>
![Image](https://github.com/user-attachments/assets/1a8fca75-cad3-4959-b11c-cf7598f0335c) <br><br>
In the differential-mode case (V₁ ≠ V₂), the output is significantly amplified, even for very low input voltage differences (e.g., microvolt-level), due to the high gain resulting from RG = 0 Ω <br><br>

<p>This experiment shows that when RG is shorted, the amplifier gives the highest possible gain. This helps in detecting very small signals, like those from the human body (biomedical), weight sensors (strain gauges), or temperature sensors (thermocouples). But since the gain is very high, even tiny unwanted signals like noise or offset can also get amplified, so the circuit must be used carefully.</p>















































