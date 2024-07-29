# Electrical Engineering Concepts

This project is created to demonstrate my understanding and diligence in studying electrical engineering. I aim to transfer to programming, and for this, I need to show my involvement in the current subjects.

## Contents

1. [Thevenin's Theorem](#thevenins-theorem)
2. [Triangular and Sawtooth Waves](#triangular-and-sawtooth-waves)
3. [Converting Degrees to Radians](#converting-degrees-to-radians)
4. [Explain Integrators and Differentiators in Detail](#explain-integrators-and-differentiators-in-detail)
5. [Resonant Filters](#resonant-filters)
6. [Kilowatt-hour](#kilowatt-hour)
7. [Sinusoidal Voltage Equation and Graph](#sinusoidal-voltage-equation-and-graph)
8. [Calculating Self-Inductance of a Solenoid](#calculating-self-inductance-of-a-solenoid)


## Thevenin's Theorem

**Thevenin's Theorem** states that any linear electrical network with voltage and current sources and resistances can be replaced at terminals A-B by an equivalent voltage source <code>V<sub>th</sub></code> in series with a resistance <code>R<sub>th</sub></code>.

### Steps to Find Thevenin Equivalent Circuit

1. **Remove the Load:** Remove the load resistance connected across terminals A-B.
2. **Find <code>V<sub>th</sub></code>:** Calculate the open-circuit voltage across terminals A-B.

   <code>V<sub>th</sub> = V<sub>AB</sub> = V<sub>s</sub> &sdot; (R<sub>2</sub> / (R<sub>1</sub> + R<sub>2</sub>))</code>

3. **Calculate <code>R<sub>th</sub></code>:** Determine the equivalent resistance <code>R<sub>th</sub></code> seen from terminals A-B by deactivating all independent voltage and current sources.

   <code>R<sub>th</sub> = (R<sub>1</sub> &sdot; R<sub>2</sub>) / (R<sub>1</sub> + R<sub>2</sub>)</code>
4. **Construct the Equivalent Circuit:** Replace the original circuit with the Thevenin equivalent circuit, which consists of a voltage source <code>V<sub>th</sub></code> in series with a resistance <code>R<sub>th</sub></code>.

### Example

Consider the following circuit:

```
     +---R1---+
     |        |
    (A)      (B)
     |        |
    R2       R3
     |        |
     +---Vs---+
     |
   (GND)
```

1. **Remove the Load:**
   - Remove the load resistance <code>R<sub>L</sub></code>.

2. **Find <code>V<sub>th</sub></code>:**
   - Calculate the open-circuit voltage across terminals A-B with the load removed.

3. **Calculate <code>R<sub>th</sub></code>:**
   - Deactivate all independent sources:
     - Replace voltage sources with short circuits.
     - Replace current sources with open circuits.
   - Calculate the resistance between terminals A-B.

4. **Construct the Equivalent Circuit:**
   - Assemble the equivalent circuit with <code>V<sub>th</sub></code> and <code>R<sub>th</sub></code>.

```
     V_th
      |
     R_th
      |
     (A)
      |
     R_L
      |
     (B)
      |
    (GND)
```
---
## Triangular and Sawtooth Waves
![image](https://github.com/user-attachments/assets/39ebb727-c207-4bb7-90c2-8dcd1f5459b1)

### Triangular Waves
![image](https://github.com/user-attachments/assets/4a3d9ce8-aa00-48d3-83a6-dce3516d2c99)

**Triangular waves** are a type of non-sinusoidal waveform that is characterized by a linear rise and fall in amplitude. These waves are used in various applications such as audio synthesizers and communication systems.

- **Characteristics:**
  - Linearly rising and falling waveform
  - Symmetrical shape with equal rise and fall times
  - Fundamental frequency and harmonics present

- **Formula:**
  - The mathematical representation of a triangular wave can be given as:
   
  $$
  x(t) = \frac{2A}{\pi} \arcsin(\sin(2\pi ft))
  $$
    
where <code>A</code> is the amplitude, <code>f</code> is the frequency, and <code>t</code> is time.

### Sawtooth Waves
![image](https://github.com/user-attachments/assets/a74f8978-4d13-47b5-a815-9cf3eea64c9e)

**Sawtooth waves** are a type of non-sinusoidal waveform that features a linear rise in amplitude followed by a sharp drop. These waves are used in applications such as signal processing and music synthesis.

- **Characteristics:**
  - Linearly rising waveform with a sudden drop
  - Asymmetrical shape
  - Contains both odd and even harmonics

 - **Formula:**
   - The mathematical representation of a sawtooth wave can be given as:
    
$$
x(t) = 2A \left( \frac{t}{T} - \left\lfloor \frac{t}{T} + \frac{1}{2} \right\rfloor \right)
$$

   where <code>A</code> is the amplitude, <code>T</code> is the period, and <code>t</code> is time.


### Important Notes

- **Applications:**
  - **Triangular Waves:** Used in audio synthesis, modulation techniques, and waveform generation.
  - **Sawtooth Waves:** Common in synthesizers for sound design, control systems, and PWM signals.

- **Harmonics:**
  - **Triangular Waves:** Contain only odd harmonics, which decrease in amplitude as the harmonic number increases.
  - **Sawtooth Waves:** Contain both odd and even harmonics, providing a richer harmonic content compared to triangular waves.

- **Visualization:**
  - The provided image shows the waveforms of sine, square, rectangular, sawtooth, and triangular waves, illustrating their unique shapes and characteristics.
---
## Converting Degrees to Radians

![output](https://github.com/user-attachments/assets/7b5b67fb-b30e-45f1-aa58-15833aa264db)

**Converting degrees to radians** is a common task in mathematics and engineering, especially in the context of trigonometric functions and angular measurements.

### Formula

The formula to convert degrees to radians is:

<code>radians = degrees * (π / 180)</code>

### Example

Consider converting 45 degrees to radians:

<code>radians = 45 * (π / 180) = π/4</code>

### Important Notes

- **Applications:** This conversion is essential in various applications, including physics, engineering, and computer graphics.
- **Radians:** Radians provide a natural way of measuring angles in terms of the arc length, which is particularly useful in calculus and trigonometry.
- **Unit Circle:** In the unit circle, one full rotation (360 degrees) is equal to \(2π\) radians.
- **General Conversion:**
  - 90° = π/2 rad
  - 180° = π rad
  - 270° = 3π/2 rad
  - 360° = 2π rad

By understanding and utilizing these conversions, you can work more effectively with angles in various mathematical and engineering contexts.

---
## Explain Integrators and Differentiators in Detail

### Integrators

**Integrator circuits** are designed to perform the mathematical operation of integration, which means summing the input signal over time. Integrators are commonly used in analog computers, signal processing, and control systems.

#### Equation

The output voltage <code>V<sub>out</sub></code> of an ideal integrator is given by the integral of the input voltage <code>V<sub>in</sub></code>:

![image](https://github.com/user-attachments/assets/ed604193-2700-4e0b-b1a3-a29f4d01e005)


### Differentiators

**Differentiator circuits** are designed to perform the mathematical operation of differentiation, which means calculating the rate of change of the input signal. Differentiators are used in analog computers, signal processing, and instrumentation.

#### Equation

The output voltage <code>V<sub>out</sub></code> of an ideal differentiator is given by the derivative of the input voltage <code>V<sub>in</sub></code>:

![image](https://github.com/user-attachments/assets/57b15c6e-22e8-46cc-90fc-44af18bdb94e)


where:
- <code>R</code> is the resistance
- <code>C</code> is the capacitance

#### Waveform
![Triangular_to_Square_Wave_Dark](https://github.com/user-attachments/assets/41c63504-0dd4-4478-9dca-f88bef784f7e)

For an input signal <code>V<sub>in</sub></code> which is a square wave, the output <code>V<sub>out</sub></code> will be a triangular wave, showing the integration effect.
<pre>
V<sub>out</sub>(t) = -<sup>1</sup>&frasl;<sub>RC</sub> ∫ V<sub>in</sub>(t) dt
</pre>
<pre>
V<sub>out</sub>(t) = -RC dV<sub>in</sub>(t)&frasl;dt
</pre>


---
### Resonant Filters

**Resonant filters** are electronic circuits that use the resonance phenomenon to filter specific frequencies from a signal. They are commonly used in radio receivers, audio equipment, and various signal processing applications.

#### Example Circuits

- **LC Circuit**: A simple resonant circuit with an inductor (L) and a capacitor (C). The resonance frequency is 

$$
f_r = \frac{1}{2\pi\sqrt{LC}}
$$

- **Crystal Filter**: Uses a piezoelectric crystal for high Q and precise frequency selection, commonly used in communication systems.
---
### Kilowatt-hour

A **kilowatt-hour (kWh)** is a unit of energy representing the consumption of 1000 watts for one hour. It is commonly used by utility companies to measure and bill for electricity usage. For example, a 100-watt light bulb operating for 10 hours consumes 1 kWh.

---
### Sinusoidal Voltage Equation and Graph

For a sinusoidal voltage with a frequency of 30 Hz and a peak value of 10V, the equation is:

![image](https://github.com/user-attachments/assets/40f06b7f-baed-49e7-9acc-4fb137f245a1)

where:
- \(V(t)\) is the voltage at time \(t\)
- 10 is the peak voltage (V)
- 30 is the frequency (Hz)
- \(t\) is the time (s)
---
### Calculating Self-Inductance of a Solenoid

To calculate the self-inductance of a solenoid with a length of 20 cm, diameter of 8 cm, and 200 coils, use the following formula:

$$
L = \mu_0 \frac{N^2 A}{l}
$$

- Where:
	- <code>L</code> is the inductance in henrys (H)
	- <code>&mu;<sub>0</sub></code> is the permeability of free space (<code>&mu;<sub>0</sub> = 4&pi; &times; 10<sup>-7</sup> H/m</code>)
	- <code>N</code> is the number of turns
	- <code>A</code> is the cross-sectional area of the solenoid in square meters (m²)
	- <code>l</code> is the length of the solenoid in meters (m)

- Given:
  	- Length (<code>l</code>) = 20 cm = 0.2 m  
  	- Diameter (<code>d</code>) = 8 cm = 0.08 m  
  	- Number of coils (<code>N</code>) = 200  

First, calculate the cross-sectional area \( A \):

$$
A = \pi \left( \frac{d}{2} \right)^2 = \pi \left( \frac{0.08}{2} \right)^2 \approx 0.005024 \, \text{m}^2
$$

Now, plug the values into the formula:

$$
L = \mu_0 \frac{N^2 A}{l} = 4\pi \times 10^{-7} \times \frac{200^2 \times 0.005024}{0.2} \approx 1.26 \times 10^{-3} \, \text{H}
$$

So, the self-inductance of the solenoid is approximately <code>1.26</code> mH.
