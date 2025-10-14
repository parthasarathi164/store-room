## Wind Tunnel Experiment (Velocity vs RPM) (lab exp1)

### Pitot-Static Tube Velocity Formula Derivation

Total pressure at pitot tube: $p_0$

Static pressure at static port: $p_\infty$

Dynamic pressure: $q = p_0 - p_\infty = \frac{1}{2} \rho V^2$

Rearrange for velocity $V$:
$$
V = \sqrt{\frac{2(p_0 - p_\infty)}{\rho}}
$$

Manometer measures height difference $\Delta h$ (in mm):

Pressure difference: $p_0 - p_\infty = \rho_{m} g\, \Delta h / 1000$

Manometric fluid density: $\rho_m$

So,
$$
V = \sqrt{ \frac{2\, \rho_{m} g\, \Delta h / 1000}{\rho} }
$$

For area correction:
$$
V = \sqrt{ \frac{2\, \rho_{m} g\, \Delta h / 1000}{\rho \left[ 1 - \left( \frac{A_s}{A_t} \right)^2 \right] } }
$$

Or, as a simplified coefficient:
$$
V = 3.78 \sqrt{ \Delta h } \text{ (if density and units are standard) }
$$

### Steps

1. Start starter motor (30 rpm).
2. Start main motor, ramp to first rpm (100 rpm).
3. Wait for stable flow.
4. Record manometer readings (inclined at $30^\circ$ and straight tube).
5. Repeat for each rpm: 100, 200, 300, 400, 500.
6. Calculate $V$ for each rpm using the above formula.
7. Plot $V$ vs rpm and check for linearity.
---
