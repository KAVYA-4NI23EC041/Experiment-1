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
  
<b>For 1:1 aspect ratio having length of 180nm</b> <br>
![Image](https://github.com/user-attachments/assets/80214717-db5a-45b6-8a9c-3fdb596e24bf) <br><br>
I<sub>total</sub> = ( Power / V<sub>dd</sub> ) <br>
= ( 1m / 1.8 ) <br>
= 0.55mA <br><br>
I<sub>ref</sub> = I<sub>d</sub> = ( I<sub>total</sub> / 2 ) <br>
= 0.55m / 2 <br>
= 0.277mA <br><br>

![Image](https://github.com/user-attachments/assets/9ca14069-432f-4373-b20d-054d4f518812) <br><br>

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

### <ins>DC Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/fa0efe8a-a295-4a14-b8aa-1206d7175bdc) <br><br>

From dc analysis: <br>
V<sub>out</sub> = 0.967276V, which is equal to V<sub>x</sub> <br>
I<sub>ref</sub> = I<sub>d</sub> = 277µA <br>

<p>For MOSFET 1 the circuit is <b>diode connected</b> hence, it is working in saturation region. MOSFET 2 has V<sub>sd</sub> = 0.8327V, V<sub>sg</sub> = 0.8327V, and V<sub>th</sub> = 0.496V. It satisfies the P-MOS saturation condition V<sub>ds</sub> > V<sub>gs</sub> - V<sub>th</sub>. For MOSFET 3 it has V<sub>ds</sub> = 0.8327V, V<sub>gs</sub> = 0.5697V, hence satisfies the N-MOS saturation condition.</p>

### <ins>Transient Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/ed0d270e-bcfe-499f-bd9c-d32c6d168ecd) <br><br>
The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 10mV with frequency of 1kHz. <br>
Can observe the output voltage which is 1.237V. 

### <ins>AC Analysis </ins> <br><br>
![Image](https://github.com/user-attachments/assets/15a42ef8-4801-4ee1-a596-a788cb1070c2) <br><br>
The obtained gain from the simulation is 29.28d<sub>B</sub>. <br>
29.28 - 3 = 26.28d<sub>B</sub> <br>
The frequency for this particular d<sub>B</sub> is 547.86MHz, the bandwidth can be calculated as f<sub>H</sub> - f<sub>L</sub>. <br>
= 547.86M - 0 <br>
= 547.86MHz <br>

---

<b>For 1:2 aspect ratio having length of 180nm</b> <br><br>

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
    <td>20µm</td>
    <td>40.495µm</td>
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
      <td> I<sub>ref</sub> = 0.183mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
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

As total current is 0.55mA, it is divided into 3 parts, where 1/3 of current is its reference current I<sub>ref</sub> and remaining is the output current I<sub>d</sub>. <br>
i.e 0.55m / 3 = 0.183mA. <br>
Hence, I<sub>ref</sub> = 0.183mA and I<sub>d</sub> = 0.3667mA <br><br>

---

### <ins>DC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/a0321bed-7f5e-4e45-a1d3-34188767f5c3) <br><br>
From dc analysis: <br>
V<sub>out</sub> = 0.998V, which is less than V<sub>x</sub> = 1.034V <br>
I<sub>ref</sub> =  0.1833mA, I<sub>d</sub> = 366.7µA <br><br>

<b><ins> Comparision table </ins></b> <br>
<table>
  <tr>
    <th> Parameters</th>
    <th> 1:1 </th>
    <th> 1:2 </th>
  </tr>
  <tr>
    <td> V<sub>out</sub></td>
    <td> 0.967276V</td>
    <td> 0.99807V</td>
  </tr>
  <tr> 
    <td> V<sub>x</sub></td>
    <td> 0.967276V</td>
    <td> 1.03471V</td>
  </tr>
</table>

### <ins>Transient Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/05169fd9-d86e-4801-adfc-570dd4a20d0f) <br><br>
The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 10mV with frequency of 1kHz.<br>
Can observe the output voltage which is 1.268V.<br>

<b><ins>Comparision for Transient </ins></b> <br>
![Image](https://github.com/user-attachments/assets/a6260517-ce49-4616-9943-e1574160aa7f) <br><br>
Can observe small dc shift in the output when there is difference in aspect ratio, otherthan that the output swing is same for both 1:1 and 1:2 aspect ratio. <br>

### <ins>AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/c7a953de-09c5-44e2-a7aa-c7339f9c516f) <br><br>
The obtained gain from the simulation is 29.28d<sub>B</sub>. <br>
29.28 - 3 = 26.28d<sub>B</sub>. <br>
The frequency for this particular dB is 547.86MHz, the bandwidth can be calculated as f<sub>H</sub> - f<sub>L</sub>. <br>
= 547.86M - 0 <br>
= 547.86MHz <br>

<b><ins>Comparision for AC </ins></b> <br>
![Image](https://github.com/user-attachments/assets/1412702c-cb4e-47d4-9d35-e07b80d44859) <br><br>
There is no difference in gain for both circuit, both have 29.28d<sub>B</sub> <br> 

---

<b>For 1:1 aspect ratio having length of 500nm</b> <br>

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
    <td>500nm</td>
    <td>500nm</td>
    <td>500nm</td>
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

### <ins>DC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/9ed7cf4a-9688-48a9-97c5-42a90dcc2b20) <br><br>
From dc analysis: <br>
Vout = 0.644704V, which is equal to Vx <br>
Iref = Id = 277µA<br>

<p>For MOSFET 1 the circuit is diode connected hence, it is working in saturation region. MOSFET 2 has Vsd = 1.155V, Vsg = 1.155V, and Vth = 0.496V. It satisfies the P-MOS saturation condition Vds > Vgs - Vth. For MOSFET 3 it has Vds = 1.155V, Vgs = 0.5697V, hence satisfies the N-MOS saturation condition.</p>

![Image](https://github.com/user-attachments/assets/9ece6a57-94bd-4911-b1cb-25a4ed59742f) <br><br> 
The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 1mV with frequency of 1kHz. <br>
Can observe the output voltage which is 721mV. <br>

### <ins>AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/9b6aba58-f642-48ae-bd0e-f8c2242bfb2d) <br><br>
The obtained gain from the simulation is 37.85dB. <br>
37.85 - 3 = 34.85dB<br>
The frequency for this particular dB is 120.748MHz, the bandwidth can be calculated as fH - fL.<br>
= 120.748M - 0<br>
= 120.748MHz <br><br>

---

<b>For 1:2 aspect ratio having length of 500nm</b> <br>

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
    <td>500nm</td>
    <td>500nm</td>
    <td>500nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>10µm</td>
    <td>20µm</td>
    <td>84.1446µm</td>
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
      <td> I<sub>ref</sub> = 0.183mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
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

### <ins> DC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/20049c90-a388-42ce-b367-21fe2fa18fb8) <br><br>
From dc analysis:
Vout = 0.774599V, which is less than Vx = 0.79317V
Iref = 0.1833mA, Id = 366.7µA

<b><ins> Comparision table </ins></b> <br>
<table>
  <tr>
    <th> Parameters</th>
    <th> 1:1 </th>
    <th> 1:2 </th>
  </tr>
  <tr>
    <td> V<sub>out</sub></td>
    <td> 0.644704V</td>
    <td> 0.774599V</td>
  </tr>
  <tr> 
    <td> V<sub>x</sub></td>
    <td> 0.644704V</td>
    <td> 0.79317V</td>
  </tr>
</table>

### <ins>Transient Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/139b172a-697d-45ff-b02e-7599584ae393) <br><br>

The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 1mV with frequency of 1kHz.
Can observe the output voltage which is 1.268V. <br>

<ins><b>Comparision for Transient</ins></b> <br>
![Image](https://github.com/user-attachments/assets/27d840f9-0e36-432c-a12e-db73059a2ee1)<br><br>
Can observe small dc shift in the output when there is difference in aspect ratio, otherthan that the output swing is same for both 1:1 and 1:2 aspect ratio. <br>

### <ins> AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/2dbfc5b9-4877-448d-a0e7-9c2f364ea8b8) <br><br>
The obtained gain from the simulation is 37.97dB. <br>
37.97 - 3 = 34.97dB.<br>
The frequency for this particular dB is 103.26MHz, the bandwidth can be calculated as fH - fL. <br>
= 103.26M - 0 <br>
= 103.26MHz <br>

<ins><b>Comparision for AC</ins></b> <br>
![Image](https://github.com/user-attachments/assets/da3b62c7-b263-47d9-a29f-3b4ab82a6a78)<br><br>
There is no much difference in gain for both the  circuits.<br>

---

<b>For 1:1 aspect ratio having length of 1µm</b> <br>
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
    <td>1µm</td>
    <td>1µm</td>
    <td>1µm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>10µm</td>
    <td>10µm</td>
    <td>92.548µm</td>
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

### <ins> DC Analysis<?ins> <br>
![Image](https://github.com/user-attachments/assets/198cacf3-01de-495c-a701-77a4040480d1) <br><br>
From dc analysis: <br>
Vout = 0.290177V, which is equal to Vx <br>
Iref = Id = 277µA<br>

<p>For MOSFET 1 the circuit is diode connected hence, it is working in saturation region. MOSFET 2 has Vsd = 1.50983V, Vsg = 1.50983V, and Vth = 0.496V. It satisfies the P-MOS saturation condition Vds > Vgs - Vth. For MOSFET 3 it has Vds = 1.50983V, Vgs = 0.5697V, hence satisfies the N-MOS saturation condition.</p> 

### <ins>Transient Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/c065a534-9091-4a23-81d7-8759a82adc76) <br><br>
The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 0.1mV with frequency of 1kHz. <br>
Can observe the output voltage which is 298.8mV. <br>

### <ins>AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/50c54895-b5df-4f5d-badf-56a68c4b1cf7) <br><br>
The obtained gain from the simulation is 35.47dB. <br>
35.47 - 3 = 32.47dB<br>
The frequency for this particular dB is 98.01MHz, the bandwidth can be calculated as fH - fL.<br>
= 98.01M - 0 <br>
= 98.01MHz<br> 

---

<b>For 1:2 aspect ratio having length of 1µm</b> <br>
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
    <td>500nm</td>
    <td>500nm</td>
    <td>500nm</td>
</tr>
<tr>
    <td>Mosfet Width</td>
    <td>10µm</td>
    <td>20µm</td>
    <td>84.1446µm</td>
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
      <td> I<sub>ref</sub> = 0.183mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
      <td> I<sub>d</sub> = 0.3667mA </td>
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

### <ins>DC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/d2a12c41-ce1e-4318-9c43-8999e460a4c3) <br><br>
From dc analysis: <br>
Vout = 0.472318V, which is less than Vx = 0.51519V <br>
Iref = 0.1833mA, Id = 366.7µA <br><br>

<b><ins> Comparision table </ins></b> <br>
<table>
  <tr>
    <th> Parameters</th>
    <th> 1:1 </th>
    <th> 1:2 </th>
  </tr>
  <tr>
    <td> V<sub>out</sub></td>
    <td> 0.293177V</td>
    <td> 0.472318V</td>
  </tr>
  <tr> 
    <td> V<sub>x</sub></td>
    <td> 0.293177V</td>
    <td> 0.51519V</td>
  </tr>
</table>

### <ins>Transient Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/2d6c394b-e67f-4353-bc9a-197b6b6ea3c8) <br><br>
The input voltage given for N-MOS has DC-offset of 0.5697V and amplitude of 0.1mV with frequency of 1kHz.<br>
Can observe the output voltage which is 480.86mV. <br>

<b>Comparision for Transient</b> <br>
![Image](https://github.com/user-attachments/assets/ac5dd329-143b-4ae4-933f-d0e876df91d7) <br><br>
Can observe dc shift in the output when there is difference in aspect ratio, otherthan that the output swing is same for both 1:1 and 1:2 aspect ratio. <br>

### <ins>AC Analysis</ins> <br> 
![Image](https://github.com/user-attachments/assets/81755fe5-4551-4d06-9319-5d30e9556c06) <br><br>
The obtained gain from the simulation is 39.268dB. <br>
39.268 - 3 = 36.268dB. <br>
The frequency for this particular dB is 55.22MHz, the bandwidth can be calculated as fH - fL. <br>
= 55.22M - 0 <br>
= 55.22MHz <br>

<b>Comparision for AC</b>
![Image](https://github.com/user-attachments/assets/a1486a6d-5b88-437f-b957-431eb92fcbed) <br><br>
There is small difference in gain for both circuit.

---

## Part B) <br>

<b>Design the differential amplifier using the same design specification as experiment 3(differential amplifier). Perform DC, Transient, AC analysis for this.</b> <br>
![Image](https://github.com/user-attachments/assets/62ad1b9a-e5f5-47ec-a96a-53c981827882) <br><br>
For this circuit biased voltage is replaced by current mirror circuit, with Vdd = 2.2V<br>
the current through the circuite should be 0.5mA, hence Iss should be of 1mA.<br>
But as we are supplying Iss through current mirror circuit, which as 1:2 aspect ratio, the Iref which is given to MOSFET 6 in the circuit has 0.5mA. <br><br>

### <ins>DC Analysis</ins><br>
![Image](https://github.com/user-attachments/assets/1b96b874-39f4-43fd-95ea-151851708f09) <br><br>
We can observe the Vp and Vout values which is not exactly same as previous experiment, but nearer to that, this variation leads to change in gain of the circuite <br><br>

### <ins>Transient Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/514a7135-ea1d-487f-977d-b37e0cc341fa) <br><br>
The output voltage is 1.42V <br>

### <ins>AC Analysis</ins> <br>
![Image](https://github.com/user-attachments/assets/420c3e84-43b5-43c1-b6ef-fc83535e6145) <br><br>
The gain of the circuit is 29.34dB.







