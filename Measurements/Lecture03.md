# Signal Characteristics

## Concept

- A signal is the physical information about a variable being transmitted from input to output in a measurement system. 
- It describes how the physical quantity is changing over time. 

## Characteristics

Waveform
- Provides the shape and form of the signal

Magnitude
- Refers to the maximum value of the signal

Range
- Span between maximum and minimum values of a signal

Amplitude
- Shows signal fluctuations relative to the mean

Frequency
- Indicates the time variation of a signal

## Classification

### Analog vs Discrete Signals

Analog Signal
- Continuous with time
- Takes on any magnitude in range of operations
- Can be described as a continuous function. Can be differentiated, integrated etc...
  - f(x), x(y), etc...

Discrete Signal
- Measuring a continuous variable at discrete points in time
- Typically no function that can fit the data (unless you do curve fitting, trendline etc..)
- Represented by individual data points and coordinates.

Quantization (Digital Signal)
- Discretized magnitude at discrete times
- Magnitude is determined by quantization at each discrete point
- Quantization assigns a single value to a range of magntiudes of a continuous signal
- For example, a digital watch displays a single numerical value for the entire duration of one minute, until it is updated at the next discrete time stop (next minute). Conversely, a dial watch can display continuous time steps.

### Static, Dynamic, Periodic, Aperiodic Signals

Static Waveform
- Signal $y(t)$ remains constant over the time $(t)$ period of interest.
- $y(t) = A_0$

Dynamic Waveform
- Signal varies with time
- Deterministic: Signal can be described by an equation (other than any integral approximation or performing a fourier series)

Periodic Waveforms
- Follow the shape of a sin wave or similar structure. Regularly repeats the signal.

Aperiodic Waveform
- Not periodic, not static, and not dynamic. Very specific type of signal. Includes steps, rises, ramps and pulses.

The table below highlights the equations for each signal type. Page 66 in the PDF, 38 in the textbook page numbers.
![](2024-01-16-13-55-43.png)

# Signal Analysis

## Mean Signal

### Mean Value


- Mean/Average value of the continuous signal over the period $t_1$ to $t_2$
- $\bar y = \dfrac{1}{t_2 - t_1} \int \limits_{t_1}^{t_2}\normalsize y(t)dt$

### Root Mean Square Value

- Equivalent to finding a constant effective current $I_e$ passing through a resistor $R$ with equal energy dissipation as a time varrying current $I$ passing through the same resistor $R$.
  - In simpler terms, we take a circuit where the current is constant, and try to find what value of constant current would have the same power use/dissipation as a circuit where the current is changing.
- RMS is an indication of the amount of variation in the dynamic portion ofthe signal
- Only the effective positive magnitude measurement of that signal is considered
- When no DC component exists (or has been subtracted from the signal) the RMS value is a statistical measure (standard deviation) of the magnitude of the fluctuations of the signal.
- $y_{rms} = \sqrt{\dfrac{1}{t_2 - t_1}}\int \limits_{t_1}^{t_2}(y(t))^2 dt$

## Example - Signal Analysis

Consider the function $y(t) = 25 + 10 \sin (6 \pi t)$. Find the mean and RMS values over the time periods 0.4 to 0.5 seconds.

# Spring Mass System

For a linear spring, $F = ky$

Applying NEwton's second law gives:
- $m \dfrac{d^2y}{dt^2} + ky = 0$

The solution (for the no-damping case) is:
- $y = A \cos (\omega t) + B \sin (\omega t)$
- Where the circular frequency is $\omega = \sqrt{\dfrac{k}{m}}$
- And the period is $T = \dfrac{2\pi}{\omega}$
- $A = y(t=0) = y_0$
- $b = \dfrac{v_0}{\omega}$

Combining these:
- $y = C \cos (\omega t - \phi)$
- Or $y = C\sin (\omega t + \phi ^*)$

We can find these variables by the following:
- 

## Example - Vibration Problem

For the given mass/spring lumped parameter model, given tha the mass is displaced upwards 0.1m from its equilibrium position and released from rest, determine the response ($y(t)$)

Model:
- $m = 1.2kg$
- $k = 750 N/m$
- $g = 9.81 m/s^2$
- Y axis downwards.

# Fourier Series

Fourier Analysis is the method of expressing a complex signal as a series of sines and cosines of differing periods and amplitudes, which are added together in an infinite trigonometric series.   

## Even and Odd

If you can plug in a negative number and the function result is negative, the function is odd.
- $y(-t) = -y(t)$

If you can plug in a negative number and the function result is positive/unchanged, the function is even
- $y(-t) = y(t)$

If the function is even the Fourier series only contains cosines
- Fourier Cosine Series
- $y(t) = \sum \limits_{n=0}^\infty A_n \cos \dfrac{2\pi n t}{T} = \sum \limits_{n=0}^\infty A_n \cos n \omega t$

If the function is odd, the Fourier series only contains sines.
- Fourier Sine Series
- $y(t) = \sum \limits_{n=0}^\infty B_n \sin \dfrac{2\pi n t}{T} = \sum \limits_{n=0}^\infty B_n \sin n \omega t$


# Frequency Domain

Signals $y(t)$ can be expressed in the frequency domain relating amplitude to frequency

The Fourier Transform of a signal $y(t) will provide amplitude/frequency properties of the signal.
- Computational time proportional to $N^2$
- For large data sets this can be expensive

For large data sets, a Fast Fourier Transform (FFT) is used instead, developed by Cooley and Tukey.