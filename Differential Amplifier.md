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
<ins> <b>Through DC Analysis</b></ins>


 
