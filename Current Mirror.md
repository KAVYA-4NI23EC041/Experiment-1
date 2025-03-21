# Current Mirror <br>
<p>The current mirror is an analog circuit that senses the reference current and generates the copy or number of copies of the reference current, with the same characteristics. The replicated current is as stable as the reference current source. The replicated current could be the same as the reference current (I<sub>d</sub> = I<sub>ref</sub>)</p>

<b><ins>Why Current Mirrors are used?</ins></b><br>
<p>Current Mirrors are particularly useful in the integrated circuits, for biasing the amplifiers. The advantage of biasing the amplifiers with the current source is that it provides a high voltage gain and good biasing stability. This current source can be generated using a simple PMOS transistor or using a MOS transistor in cascode configuration (to achieve higher gain).</p> 

![Image](https://github.com/user-attachments/assets/bb327c23-5a9f-4fdf-b878-55bbe08b5af1) <br><br>

<p>But this type of MOS current source is susceptible to the change in the biasing voltage and the change in temperature. Moreover, the integrated circuit may contain hundred or thousand of such amplifiers. To bias all the amplifiers with precise biasing voltage is another challenge. So, to overcome all these problems, in integrated circuits, one stable current source is fabricated within IC, and using the current mirror the multiple copies of the stable current source is generated (which can be used to bias the amplifiers).</p> 

---

<b><ins>MOSFET- Current Mirror</ins></b> <br><br>
<p>The figure shows a current mirror circuit using the NMOS transistor. The reference current is converted to the voltage using diode connected transistor and the same is applied between the gate and the source of the another MOSFET.</p>

![Image](https://github.com/user-attachments/assets/a34dd2c9-6e9f-4eec-894a-5cddae810c5e) <br><br>

The relation between the I<sub>d</sub> and I<sub>ref</sub> can be given by the following expression. <br><br>
I<sub>d</sub> = ( (W/L)<sub>1</sub> / (W/L)<sub>ref</sub> ) * I<sub>ref</sub> <br>
<p>By changing the W/L ratio of the two transistors, the current which is fraction or multiple of the reference current can be generated. The only thing which needs to be ensured is that, the MOSFET should operate in the saturation region.</p>

---

<b><ins>Effect of Channel Length Modulation on Current Mirror</ins></b> <br><br>
If the channel length modulation effect is also considered, then as shown in figure the drain to source voltage (V<sub>ds</sub>) of the MOSFET increases, the drain current also slightly increases. <br><br>
![Image](https://github.com/user-attachments/assets/728068cf-d43c-489c-8703-43d6f6daa926) <br><br>
Considering the channel length modulation effect, if VDS of MOSFET M1 changes by ΔVDS then the drain current ID1 also changes to I<sub>d1</sub> + ΔI<sub>d1</sub>. <br><br>
![Image](https://github.com/user-attachments/assets/06b5ea7c-0585-483d-9f3b-d3238f0f8e2d) <br><br>
The effect of channel length modulation can be reduced by increasing the length of the channel for the given W/L ratio. <br><br>

---

### <ins> SIMULATION <ins> <br>
![Image](https://github.com/user-attachments/assets/12950c9b-b754-4f13-b911-143fab5a26a1) <br><br>

<ins>Observed Table</ins> <br>
For I<sub>ref</sub> = 100u <br>

  <table> 
<tr>
 <th><b>I<sub>out(expected)</sub>(A)</b></th>
 <th><b>I<sub>out(appeared)</sub>(A)</b></th>
 <th><b>(W/L)<sub>2</sub>(m)</b></th>
 <th><b>(W/L)<sub>1</sub>(m)</b></th>
 <th><b>V<sub>x</sub>(V)</b></th>
 <th><b>V<sub>out</sub>(V)</b></th>
</tr>
<tr>
    <td>100µ</td>
    <td>103.5µ</td>
    <td>(180n/180n)</td>
    <td>(180n/180n)</td>
    <td>1.275V</td>
    <td>1.715V</td>
</tr>
<tr>
    <td>100µ</td>
    <td>100.715µ</td>
    <td>(500n/500n)</td>
    <td>(500n/500n)</td>
    <td>1.4375V</td>
    <td>1.717V</td>
</tr>
<tr>
    <td>100µ</td>
    <td>100.648µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/1µ)</td>
    <td>1.3972V</td>
    <td>1.71747V</td>
</tr>
<tr>
    <td>200µ</td>
    <td>197.637µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/2µ)</td>
    <td>1.397V</td>
    <td>1.637V</td>
</tr>
    <tr>
      <td>50µ</td>
    <td>52.13µ</td>
    <td>(1µ/1µ)</td>
    <td>(1µ/0.5µ)</td>
    <td>1.3972V</td>
    <td>1.75725V</td>
    </tr>
    <tr>
      <td>100µ</td>
    <td>101.539µ</td>
    <td>(1µ/2µ)</td>
    <td>(1µ/2µ)</td>
    <td>1.08762V</td>
    <td>1.71674V</td>
    </tr>
     <tr>
      <td>100µ</td>
    <td>102.131µ</td>
    <td>(1µ/3µ)</td>
    <td>(1µ/3µ)</td>
    <td>0.95619V</td>
    <td>1.71625V</td>
    </tr>
</table> 
<br>

---

<ins>How Channel Length Modulation Affects the Current?</ins> <br>
In saturation ( V<sub>ds</sub> > V<sub>gs</sub> - V<sub>th</sub> ), the MOSFET ideally acts as a constant current source. <br>
However, at higher V<sub>ds</sub>, the depletion region at the drain end of the channel widens, effectively reducing the channel length. <br>
This reduction in channel length increases the drain current, as the effective channel resistance decreases.
The relationship considering channel length modulation is:
<b>I<sub>d</sub> = I<sub>d0</sub> (1+𝜆*V<sub>ds</sub> ) </b> <br>
where: I<sub>d0</sub>  is the ideal current without channel length modulation.<br>
λ is the channel length modulation parameter inversely proportional to the effective channel length.<br>

----

<b><ins>PMOS Current Mirror</ins></b> <br><br>
![Image](https://github.com/user-attachments/assets/c839bee1-fe18-41fc-86cd-d5b355416d03) <br><br>
<p> In PMOS current mirror, the source terminals for both transistors are connected to Supply voltage Vdd. The relation between the ID1 and IREF can be given by the same expression. The only thing which needs to be ensured is that M2 and M3 should operate in the saturation region. Or in other words, V<sub>SD1</sub> ≥ V<sub>SG </sub> – |V<sub>TP</sub> |, Where VTP is the threshold voltage of the PMOS transistor.</p>

---

### <ins> SIMULATION <ins> <br><br>

<p><b>Design a current mirror circuit which has a gain of A<sub>V</sub> = -10V/V, power supply of V<sub>dd</sub> = 1.8V, and power of P <= 1mW. Find reference current (I<sub>ref</sub>), output current (I<sub>d</sub>), and total current (I<sub>total</sub>). Perform DC and AC analysis for mirror ratio 1:1, 1:2. Vary length from 180nm -> 500nm -> 1µm and do the analysis. </b></p> <br><br>
  
![Image](https://github.com/user-attachments/assets/80214717-db5a-45b6-8a9c-3fdb596e24bf) <br><br>
I<sub>total</sub> = ( Power / V<sub>dd</sub> ) <br>
= ( 1m / 1.8 ) <br>
= 0.55mA <br><br>
I<sub>ref</sub> = I<sub>d</sub> = ( I<sub>total</sub> / 2 ) <br>
= 0.55m / 2 <br>
= 0.277mA <br><br>

 <table> 
<tr>
 <th><b>Parameters</b></th>
 <th><b>MOSFET1</b></th>
 <th><b>MOSFET2</b></th>
 <th><b>MOSFET3</b></th>
</tr>
<tr>
    <td>Model</td>
    <td>CMOSP</td>
    <td>CMOSP</td>
    <td>CMOSN</td>
</tr>
<tr>
    <td>Mosfet Length</td>
    <td>180nm</td>
    <td>180nm</td>
    <td>180nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>10µm</td>
    <td>10µm</td>
    <td>30.86947µm</td>
</tr>
<tr>
    <td>Threshold Voltage</td>
    <td> -0.507V</td>
    <td> -0.507V</td>
    <td> 0.496V</td>
</tr>
   <tr>
    <td>Channel Length</td>
    <td>1.3822</td>
    <td>1.3822</td>
    <td>1.3299</td>
</tr>
    <tr>
      <td>Current(I)</td>
      <td> I<sub>ref</sub> = 0.227mA </td>
      <td> I<sub>d</sub> = 0.227mA </td>
      <td> I<sub>d</sub> = 0.227mA </td>
    </tr>
    <tr>
      <td>Supply Voltage</td>
      <td> 1.8V</td>
      <td> 1.8V</td>
      <td> --- </td>
    </tr>
     <tr>
      <td>Biased Voltage</td>
      <td> --- </td>
      <td> --- </td>
      <td> 0.5697V</td>
    </tr>
</table>
<br>

### <ins>DC Analysis </ins> <br>












