# Problem 1

# Measuring the Acceleration Due to Gravity Using a Simple Pendulum

## Objective
To measure the acceleration due to gravity \( g \) using a simple pendulum and rigorously analyze the uncertainties involved in the measurements.

## Materials

- String (length: 1.5 m)
- Weight (e.g., bag of coins)
- Stopwatch (±0.01 s resolution)
- Measuring tape (±0.001 m resolution)
- Protractor (optional, for ensuring small angle)

## Procedure

### 1. Setup

The pendulum was suspended from a fixed point. The length \( L \) of the pendulum was measured from the point of suspension to the center of mass of the weight.

- $$ L = 1.500 \, \text{m} $$
- $$ \delta L = \pm 0.001 \, \text{m} $$

### 2. Data Collection

The pendulum was displaced by an angle less than \( 15^\circ \). For each trial, the time for 10 oscillations was measured using a stopwatch. This process was repeated 10 times.

## Tabulated Data

| Trial | Time for 10 Oscillations (s) |
|-------|-------------------------------|
| 1     | 24.81                         |
| 2     | 24.76                         |
| 3     | 24.85                         |
| 4     | 24.78                         |
| 5     | 24.83                         |
| 6     | 24.79                         |
| 7     | 24.77                         |
| 8     | 24.86                         |
| 9     | 24.80                         |
| 10    | 24.84                         |

- Stopwatch resolution: ±0.01 s → $$ \delta T_{\text{meas}} = 0.005 \, \text{s} $$

## Calculations

### 1. Mean Time and Standard Deviation

$$
\overline{T_{10}} = \frac{1}{10} \sum T_{10i} = 24.809 \, \text{s}
$$

$$
T = \frac{\overline{T_{10}}}{10} = 2.4809 \, \text{s}
$$

$$
\sigma = \sqrt{\frac{1}{n-1} \sum (T_{10i} - \overline{T_{10}})^2} \approx 0.030 \, \text{s}
$$

$$
\delta T = \frac{\sigma}{\sqrt{n}} = \frac{0.030}{\sqrt{10}} \approx 0.0095 \, \text{s}
$$

### 2. Calculation of \( g \)

The period \( T \) of a simple pendulum is related to the acceleration due to gravity \( g \) by the formula:

$$
T = 2\pi \sqrt{\frac{L}{g}} \Rightarrow g = \frac{4\pi^2 L}{T^2}
$$

Substituting the known values:

$$
g = \frac{4\pi^2 \cdot 1.500}{(2.4809)^2} \approx 9.61 \, \text{m/s}^2
$$

### 3. Uncertainty in \( g \)

Using propagation of uncertainty:

$$
\left( \frac{\delta g}{g} \right)^2 = \left( \frac{\delta L}{L} \right)^2 + \left( 2\frac{\delta T}{T} \right)^2
$$

Where:

$$
\frac{\delta L}{L} = \frac{0.001}{1.500} = 6.67 \times 10^{-4}, \quad \frac{\delta T}{T} = \frac{0.0095}{2.4809} = 3.83 \times 10^{-3}
$$

Now calculating:

$$
\frac{\delta g}{g} = \sqrt{(6.67 \times 10^{-4})^2 + (2 \cdot 3.83 \times 10^{-3})^2} \approx 7.75 \times 10^{-3}
$$

Therefore:

$$
\delta g = 9.61 \cdot 7.75 \times 10^{-3} \approx 0.075 \, \text{m/s}^2
$$

Thus, the acceleration due to gravity is:

$$
\boxed{g = 9.61 \pm 0.08 \, \text{m/s}^2}
$$

##

<video controls src="download.mp4" title="Title"></video>


## Discussion

### Comparison with Standard Value

- Standard value of \( g \) ≈ $$ 9.81 \, \text{m/s}^2 $$
- Measured value: $$ 9.61 \pm 0.08 \, \text{m/s}^2 $$
- Deviation: $$ \approx 0.20 \, \text{m/s}^2 $$, which is more than the uncertainty margin, suggesting possible systematic error.

### Sources of Uncertainty

1. **Length Measurement**:
   - Only one measurement was taken.
   - The center of mass may not be well estimated for irregular weights.

2. **Timing Errors**:
   - Human reaction time (~0.2 s) can bias stopwatch readings.
   - Repeated measurements helped reduce random timing errors.

3. **Small Angle Assumption**:
   - Valid for \( \theta < 15^\circ \), assumed satisfied here.
   - Larger angles would make \( T \) slightly longer.

4. **Air Resistance and Friction**:
   - Dampen the motion slightly, elongating period.
   - Negligible over 10 oscillations.

5. **Support Flexibility**:
   - Any swinging or flexibility in the support point introduces error.

## Conclusion

The experimental value of $$ g = 9.61 \pm 0.08 \, \text{m/s}^2 $$ is reasonably close to the standard value, demonstrating the validity of using a simple pendulum for estimating gravitational acceleration. This experiment also highlights the importance of uncertainty analysis in experimental physics.
