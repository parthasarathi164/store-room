## Wind Tunnel Experiment (Velocity vs RPM) (lab exp1)

### Derivation of the Velocity Formula (Alcohol Manometer)

#### Governing Equations

The derivation uses two primary equations:

* **Bernoulli's Equation:** $P_1 + \frac{1}{2}\rho v_1^2 = P_2 + \frac{1}{2}\rho v_2^2$
    * **$P$**: Static pressure of the fluid (Pascals, Pa).
    * **$\rho$**: Density of the flowing fluid, which is air (kg/m³).
    * **$v$**: Velocity of the air (m/s).
    * **Subscripts 1 and 2**: Refer to the upstream settling chamber and the test section, respectively.

* **Continuity Equation:** $A_1 v_1 = A_2 v_2$
    * **$A$**: Cross-sectional area of the tunnel (m²).

#### Velocity Derivation

Combining the two equations and solving for the test section velocity ($v_2$, or simply $v$) gives:
$$
v^2 = \frac{2(P_1 - P_2)}{\rho \left(1 - \left(\frac{A_2}{A_1}\right)^2\right)}
$$

#### Manometer Pressure

The pressure difference is measured with an alcohol manometer.
$$
P_1 - P_2 = \frac{\rho_{alc} g (\Delta h)}{1000}
$$
* **$\rho_{alc}$**: Density of the manometer fluid, which is alcohol (kg/m³).
* **$g$**: Acceleration due to gravity (m/s²).
* **$\Delta h$**: Height difference in the manometer (millimeters, mm).
* The **1000** converts $\Delta h$ from millimeters to meters.

#### Final Formula

Substituting the manometer pressure into the velocity equation yields the final formula:
$$
v = \sqrt{\frac{2 \cdot \frac{\rho_{alc} g (\Delta h)}{1000}}{\rho \left(1 - \left(\frac{A_2}{A_1}\right)^2\right)}}
$$

#### Steps to perform experiment

1. Start starter motor (30 rpm).
2. Start main motor, ramp to first rpm (100 rpm).
3. Wait for stable flow.
4. Record manometer readings (inclined at $30^\circ$ and straight tube).
5. Repeat for each rpm: 100, 200, 300, 400, 500.
6. Calculate $V$ for each rpm using the above formula.
7. Plot $V$ vs rpm and check for linearity.
---
