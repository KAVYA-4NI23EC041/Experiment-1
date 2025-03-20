# Current Mirror <br>
<p>The current mirror is an analog circuit that senses the reference current and generates the copy or number of copies of the reference current, with the same characteristics. The replicated current is as stable as the reference current source. The replicated current could be the same as the reference current (I<sub>d</sub> = I<sub>ref</sub>)</p>
<b><ins>Why Current Mirrors are used?</ins></b><br>
<p>Current Mirrors are particularly useful in the integrated circuits, for biasing the amplifiers. The advantage of biasing the amplifiers with the current source is that it provides a high voltage gain and good biasing stability. This current source can be generated using a simple PMOS transistor or using a MOS transistor in cascode configuration (to achieve higher gain).</p> 

![Image](https://github.com/user-attachments/assets/bb327c23-5a9f-4fdf-b878-55bbe08b5af1) <br><br>
<p>But this type of MOS current source is susceptible to the change in the biasing voltage and the change in temperature. Moreover, the integrated circuit may contain hundred or thousand of such amplifiers. To bias all the amplifiers with precise biasing voltage is another challenge. So, to overcome all these problems, in integrated circuits, one stable current source is fabricated within IC, and using the current mirror the multiple copies of the stable current source is generated (which can be used to bias the amplifiers).</p> 
<b><ins>MOSFET- Current Mirror</ins></b> <br><br>
<p>The figure shows a current mirror circuit using the NMOS transistor. The reference current is converted to the voltage using diode connected transistor and the same is applied between the gate and the source of the another MOSFET.</p>

![Image](https://github.com/user-attachments/assets/a34dd2c9-6e9f-4eec-894a-5cddae810c5e) <br><br>
The relation between the I<sub>d</sub> and I<sub>ref</sub> can be given by the following expression. <br><br>
I<sub>d</sub> = ( (W/L)<sub>1</sub> / (W/L)<sub>ref</sub> ) * I<sub>ref</sub> <br>
<p>By changing the W/L ratio of the two transistors, the current which is fraction or multiple of the reference current can be generated. The only thing which needs to be ensured is that, the MOSFET should operate in the saturation region.</p>







