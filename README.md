# One-Dimensional Superposition of Sine Waves
    Linear Superposition of Waveforms and Resultant Interference Patterns

Modeling and visualization of the superposition 
principle in one dimension.

* Python 3.11.4
* Matplotlib 3.7.2 
* Seaborn 0.12.2 
* NumPy 1.25.2

---
### Main Project Files
* [Standalone Module](sine_wave_superposition.py)
* [IPython Notebook / Jupyter Notebook](sine_wave_superposition_notebook.ipynb)
---

## Content
#### Theoretical Background
* [Wave equation](#wave-equation)
* [Superposition principle](#superposition-principle)

#### Parameters
* [Wave model parameters](#wave-model-parameters)
* [Superposition plot parameters](#superposition-plot-parameters)

#### Implementation
* [Modeling of sine wave superposition phenomena and interference patterns](#modeling-of-sine-wave-superposition-phenomena-and-interference-patterns)

---

### Wave Equation

The sine wave equation in one-dimension can be represented as:

$y(x, t) = A \sin(kx \pm \omega t + \phi)$

where:

$y(x,t)$ is the wave displacement at position $x$ and time $t$</br>
$A$ is the amplitude</br>
$k = \frac{2\pi}{\lambda}$ is the wave number</br>
$\omega = 2\pi f$ is the angular frequency</br>
$\phi$ is the phase offset</br>
$+$ or $−$ depends on the direction of propagation (right or left)
</br>

### Superposition Principle

The superposition principle states that when two or more waves overlap in space, 
the resultant wave is the algebraic sum of their individual waves. When two waves $W_1$ and $W_2$ 
interfere, the resultant wave $W_R$ can be given by:

$W_R(x, t) = W_1(x, t) + W_2(x, t)$

Interference patterns are the result of the superposition of two or more waves.
These patterns can be either constructive or destructive depending on the phase 
and amplitude of the interacting waves. These patterns can display areas of both constructive and 
destructive interference, and they are commonly seen in phenomena like double-slit experiments and 
sound wave interference.

---

### Wave Model Parameters
>model_sinewave() function

| Parameter      | Description                                                                       | Type              |
|:---------------|:----------------------------------------------------------------------------------|:------------------|
| x              | Positions of the wave ($x$): Positions where the wave is evaluated (m)            | numpy.ndarray     |
| t              | Time of evaluation ($t$): Time at which the wave is evaluated (s)                 | float             |
| A              | Amplitude ($A$): Maximum displacement from equilibrium (m)                        | float             |
| wavelength     | Wavelength ($\lambda$): Length of one complete wave cycle (m)                     | float             |
| frequency      | Frequency ($f$): Number of oscillations per second (Hz)                           | float             |
| phi            | Phase offset ($\phi$): Shifts the wave horizontally (radians)                     | float (optional)  |
| propagation    | Propagation direction: 'Right' for positive x-direction, 'Left' for negative      | string (optional) |
| phase_polarity | Phase polarity (y): 'Positive' retains form, 'Negative' flips the wave vertically | string (optional) |

These parameters can be used to represent the waves in the model:

$y(x, t) = A \sin\left( \frac{2\pi}{\text{wavelength}} \cdot x \pm 2\pi \cdot \text{frequency} \cdot t + \phi \right)$

---

### Superposition Plot Parameters
>plot_wave_superposition() function

| Parameter     | Description                                              | Type            |
|:--------------|:---------------------------------------------------------|:----------------|
| wave_1_params | Wave 1 Parameters                                        | dictionary      |
| wave_2_params | Wave 2 Parameters                                        | dictionary      |
| dark_theme    | Dark Theme: If True, uses a dark background for the plot | bool (optional) |

---
## Implementation
### Modeling of sine wave superposition phenomena and interference patterns

#### 1. Standing waves

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 5.0      | 5.0      |
| wavelength     | $\lambda$: Wavelength | 10.0     | 10.0     |
| frequency      | $f$: Frequency        | 90.0     | 90.0     |
| phi            | $\phi$: Phase offset  | 0.0      | 0.0      |
| propagation    | Propagation direction | right    | left     |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:----------:|:-----------:|:-----:|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/standing_waves.gif'/>
</p>

#### 2. Wave beats

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 5.0      | 5.0      |
| wavelength     | $\lambda$: Wavelength | 4.0      | 5.0      |
| frequency      | $f$: Frequency        | 10.0     | 20.0     |
| phi            | $\phi$: Phase offset  | 0.0      | 0.0      |
| propagation    | Propagation direction | right    | right    |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/wave_beats.gif'/>
</p>

#### 3. Constructive Interference

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 10.0     | 5.0      |
| wavelength     | $\lambda$: Wavelength | 10.0     | 10.0     |
| frequency      | $f$: Frequency        | 90.0     | 90.0     |
| phi            | $\phi$: Phase offset  | 0.0      | 0.0      |
| propagation    | Propagation direction | right    | right    |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/constructive_interference.gif'/>
</p>

#### 4. Destructive Interference

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 10.0     | 5.0      |
| wavelength     | $\lambda$: Wavelength | 10.0     | 10.0     |
| frequency      | $f$: Frequency        | 90.0     | 90.0     |
| phi            | $\phi$: Phase offset  | 0.0      | $\pi$    |
| propagation    | Propagation direction | right    | right    |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/destructive_interference.gif'/>
</p>

#### 5. Perfect Destructive Interference (Cancellation)

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 10.0     | 10.0     |
| wavelength     | $\lambda$: Wavelength | 10.0     | 10.0     |
| frequency      | $f$: Frequency        | 90.0     | 90.0     |
| phi            | $\phi$: Phase offset  | 0.0      | $\pi$    |
| propagation    | Propagation direction | right    | right    |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/wave_cancellation.gif'/>
</p>

#### 6. Fundamental Frequency + 2nd Harmonic

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 5.0      | 2.5      |
| wavelength     | $\lambda$: Wavelength | 4.0      | 2.0      |
| frequency      | $f$: Frequency        | 90.0     | 180.0    |
| phi            | $\phi$: Phase offset  | 0.0      | 0.0      |
| propagation    | Propagation direction | right    | right    |
| phase_polarity | Phase polarity (y)    | positive | positive |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/sine_wave_superposition_1.gif'/>
</p>

#### 7. General superposition

| Parameter      | Description           | $W_1$    | $W_2$    |
|:---------------|:----------------------|:---------|:---------|
| A              | $A$: Amplitude        | 10.0     | 5.0      |
| wavelength     | $\lambda$: Wavelength | 6.0      | 10.0     |
| frequency      | $f$: Frequency        | 90.0     | 110.0    |
| phi            | $\phi$: Phase offset  | 0.0      | 0.0      |
| propagation    | Propagation direction | right    | left     |
| phase_polarity | Phase polarity (y)    | positive | negative |

| Parameter  | Description | Value |
|:-----------|:------------|:------|
| dark_theme | Dark Theme  | True  |

#### Output:

<p align='left'>
  <img src='img/sine_wave_superposition_2.gif'/>
</p>