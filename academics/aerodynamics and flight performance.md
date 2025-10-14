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
---
### Derivation for Free Stream Velocity (doubt)

#### Governing Equation (Bernoulli's Principle)

For a Pitot-static probe in a free stream, the total (or stagnation) pressure is the sum of the static pressure and the dynamic pressure.

* **Equation:** $P_0 = P_\infty + \frac{1}{2}\rho v^2$
    * **$P_0$**: Free stream total pressure (Pascals, Pa). This is measured at a point where the flow is brought to a stop.
    * **$P_\infty$**: Free stream static pressure (Pascals, Pa). This is the pressure of the surrounding fluid.
    * **$\rho$**: Density of the flowing fluid, which is air (kg/m³).
    * **$v$**: Velocity of the free stream air (m/s).

#### Velocity Derivation

Rearranging Bernoulli's equation to solve for the velocity ($v$):
$$
v = \sqrt{\frac{2(P_0 - P_\infty)}{\rho}}
$$

#### Manometer Pressure

The pressure difference ($P_0 - P_\infty$) is measured by an alcohol manometer.

* **Equation:** $P_0 - P_\infty = \frac{\rho_{alc} g (\Delta h)}{1000}$
    * **$\rho_{alc}$**: Density of the manometer fluid, which is alcohol (kg/m³).
    * **$g$**: Acceleration due to gravity (m/s²).
    * **$\Delta h$**: Height difference in the manometer (millimeters, mm).
    * The **1000** converts $\Delta h$ from millimeters to meters.

#### Final Formula

Substituting the manometer pressure into the velocity equation yields the final formula for a free-stream measurement:
$$
v = \sqrt{\frac{2 \rho_{alc} g (\Delta h)}{1000 \rho}}
$$

> **Note:** This derivation is based on your description of measuring free-stream total and static pressure. The area ratio term, $(1 - (A_2/A_1)^2)$, seen in your original image's formula, is used specifically for flow inside a duct that changes area (like a Venturi tube or a wind tunnel nozzle), not for a standard free-stream Pitot-tube measurement.
---

#### Steps to perform experiment

1. Start starter motor (30 rpm).
2. Start main motor, ramp to first rpm (100 rpm).
3. Wait for stable flow.
4. Record manometer readings (inclined at $30^\circ$ and straight tube).
5. Repeat for each rpm: 100, 200, 300, 400, 500.
6. Calculate $V$ for each rpm using the above formula.
7. Plot $V$ vs rpm and check for linearity.

