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

## <ins> SIMULATION <ins> <br>
![Image](https://github.com/user-attachments/assets/12950c9b-b754-4f13-b911-143fab5a26a1) <br><br>

<ins>Observed Table</ins> <br>

  <table> 
<tr>
 <th><b>I<sub>ref</sub></b></th>
 <th><b>colspan="2">I<sub>out</sub></b></th>
 <th><b>(W/L)<sub>2</sub></b></th>
 <th><b>(W/L)<sub>1</sub></b></th>
 <th><b>V<sub>x</sub></b></th>
 <th><b>V<sub>out</sub></b></th>
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









