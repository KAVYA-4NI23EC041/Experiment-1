# Monostable multivibrator using 555 timer IC . <br>
<p> A multivibrator is a switching circuit that uses two amplifying stages with positive feedback to generate square waves. It oscillates between HIGH and LOW states and is widely used in digital electronics for timing, data storage, and signal generation. There are three types: astable (free-running), monostable (one-shot), and bistable (flip-flop).</p>

The multivibrators are classified into three categories- <br>
1.Astable Multivibrator.<br>
2.Monostable Multivibrator.<br>
3.Bistable Multivibrator.<br>
![Image](https://github.com/user-attachments/assets/bf37f480-e56b-4810-a5cd-257c7470b30b) <br><br>

### Astable Multivibrator <br>
1.It is also known as a free-running multivibrator.<br>
2.It has no stable state, hence the name astable.<br>
3.It produces a continuous series of pulses with a predetermined frequency and duty cycle.<br>
4.It requires two identical transistors two capacitors, and a few resistors.<br>
5.It is commonly used in oscillator circuits, pulse generators, and clock circuits.<br><br>

### Monostable Multivibrator <br>
1.Also known as a one-shot multivibrator.<br>
2.It has only one stable state.<br>
3.It produces a single output pulse of a predetermined width when triggered by an input signal.<br>
4.It requires two transistors, two capacitors, and a few resistors.<br>
5.It is commonly used in timing circuits, delay circuits, and pulse width modulation circuits.<br><br>

### Bistable Multivibrator <br>
![Image](https://github.com/user-attachments/assets/2b76c0fe-aea8-4602-a517-bfecab0075dd) <br><br>
1.Also known as a flip-flop multivibrator. <br>
2.It has two stable states and can remain in either state indefinitely without any input signal.<br>
3.It requires two transistors, two capacitors, and a few resistors.<br>
4.It is commonly used in digital circuits as a memory element, latch, or flip-flop.<br>
5.It is also used in applications where a simple on/off switch is required.<br><br>

## Working of Monostable Multivibrator with 555 Timer Circuit <br>
<p> The output of the monostable multivibrator using 555 timer remains in its stable state until it gets a trigger. In monostable 555 multivibrator, when both the transistor and capacitor are shorted then this state is called as a stable state. When the voltage goes below at the second pin of the 555 IC, the o/p becomes high. This high state is called quasi stable state. When the circuit activates then the transition from a stable state to quasi stable state. Then the discharge transistor is cut off and capacitor starts charging to VCC. Charging of the capacitor is done via the resistor R1 with a time constant R1C1. Hence, the voltage of the capacitor increases and finally exceeds 2/3 Vcc, it will change the internal control flip flop, thereby turning off the 555 timer IC. Thus the o/p goes back to its stable state from an unstable state.

The Time duration of the pulse is given by

T = 1.1RC
Where, R is in Ω and C in Farads.

Finally we can conclude that, in the monostable multivibrator using 555 timer, the o/p stays in a low state until it gets a trigger i/p. This type of operation is used in push to operate systems. When the input is triggered, then the o/p will go to high state & comes back to its original state.</p>

## Design a  Monostable Multivibrator with 555 Timer Circuit to generate pulse of width 0.5 ms using input triggers. <br><br>

### Case 1 
![Image](https://github.com/user-attachments/assets/f9f0c116-e879-4577-a3ed-ff5f33dc963b) <br><br>
1.The input trigger just initiates the output change. <br>
2.The duration of the output pulse (HIGH or LOW) is determined by the values of the resistor (R) and capacitor (C) in the timing circuit, not by the trigger pulse width.<br><br>

### Case 2 
![Image](https://github.com/user-attachments/assets/800e544f-f183-49ca-87ca-6bbd7302b58c) <br><br>
1.It generates a single output pulse of fixed duration (1 ms). <br>
2.During that 1 ms, it ignores any further triggers<br>
3.Only after returning to the stable state, it can respond to a new trigger.<br><br>

### Case 3
![Image](https://github.com/user-attachments/assets/d741d208-41ac-48ab-9307-a3987bda3e8d)<br><br>
1.When the 0.2 ms trigger arrives, it activates the monostable.<br>
2.The monostable then generates a fixed output pulse of 0.5 ms, regardless of the trigger pulse duration.<br>
3.After 0.5 ms, the output returns to its stable (LOW) state.<br>

<p>A monostable multivibrator generates a single, fixed-duration output pulse in response to a trigger, regardless of the trigger’s duration. The output pulse width is set by the circuit’s resistor-capacitor (RC) time constant.
It responds only to the first valid trigger and ignores additional triggers during the output pulse period.
This makes it ideal for timing applications, pulse shaping, and debouncing. </p>

## Astable multivibrator and monostable multivibrator using 555 timer IC<br>

### Inernal Design <br>
![Image](https://github.com/user-attachments/assets/3c521130-ad73-4c3c-b985-a4b595dfb1a4) <br><br>

### Procedure
1.	Build the circuit as per the Circuit diagram. <br>
2.	Calculate the resistor R and capacitor C for Astable multivibrator Differentiator, clipper and Monostable multivibrator. <br>
3.	Analyze the capacitor charging and discharging Voltage per time.<br>
4.	Analyze the ton period when input is triggered.<br>

### Calculation <br>
![Image](https://github.com/user-attachments/assets/6cd76aeb-4c95-478c-8eca-1b6ec0590476) <br><br>
![Image](https://github.com/user-attachments/assets/da406075-421f-4d77-bcff-ee890fc7668e) <br><br>

### Case 1 <br>
![Image](https://github.com/user-attachments/assets/a86f52f0-75fb-4809-9e9b-7f0313d2e008)<br><br>
V1 is Output of the Astable Multivibrator, V2 is Capacitor Voltage of Astable Multivibrator, V3 is Output of Differentiator, V4 is Capacitor Voltage of Monostable Multivibrator, Vout is Output of Monostable Multivibrator pulse width is 0.5ms

### Case 2 <br>
![Image](https://github.com/user-attachments/assets/701c6f73-1d7c-4511-a859-f514a3e72a2a) <br><br>

V1 is Output of the Astable Multivibrator, V2 is Capacitor Voltage of Astable Multivibrator, V3 is Output of Differentiator, V4 is Capacitor Voltage of Monostable Multivibrator, Vout is Output of Monostable Multivibrator pulse width is 0.5ms

### Case 3 <br>

V1 is Output of the Astable Multivibrator, V2 is Capacitor Voltage of Astable Multivibrator, V3 is Output of Differentiator, V4 is Capacitor Voltage of Monostable Multivibrator, Vout is Output of Monostable Multivibrator pulse width is 0.5ms

### Inference <br>
1. We saw that changing the resistor and capacitor values in a 555 timer changes how long the output stays ON and OFF. But with the basic 555 setup, we can’t always get the exact ON/OFF times we want. <br>
2.Sometimes, like when we need the OFF time to be longer than the ON time, the normal 555 astable circuit doesn’t give the right output directly. That’s why in Case 3, we used an inverter to flip the signal. <br>
3.By adding a simple NOT gate (made using a transistor), we could reverse the signal. This helped us create the output timing we needed more easily. <br>
4.In Case 2, we used very short pulses (less than a millisecond). To make that work, we used small resistor and capacitor values. This showed how important it is to choose the right and precise components for accurate timing.<br>
5.A differentiator circuit helped us spot the exact moment when the input signal goes from LOW to HIGH. This is useful when we want to respond only to the change, not the full length of the pulse. <br>
6.When we used the monostable 555 timer and triggered it with those edges, it gave us a clean and steady pulse every time. This is very helpful when we want the output to stay the same no matter how long the input pulse is. <br><br>






