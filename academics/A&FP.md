### Wind Tunnel Experiment (Velocity vs RPM) (lab exp1)

#### General formula for $V_2$
Start from Bernoulli between points 1 and 2 (same elevation, incompressible, inviscid):
$$
P_1+\tfrac{1}{2}\rho V_1^2 \;=\; P_2+\tfrac{1}{2}\rho V_2^2.
$$
Rearrange for $V_2$:
$$
V_2 \;=\; \sqrt{\,V_1^2 \;+\; \dfrac{2\,(P_1-P_2)}{\rho}\, }.
$$

**Terms:** $P_{1,2}$ = static pressures at points 1 and 2; $V_{1,2}$ = velocities; $\rho$ = fluid density.

---

#### Velocity at exit of a convergent section (use continuity)
Continuity:
$$A_1 V_1 = A_2 V_2 \quad\Rightarrow\quad V_1=\dfrac{A_2}{A_1}V_2.$$
Substitute into Bernoulli ($\Delta P\equiv P_1-P_2$):
$$
V_2^2\Big(1-\Big(\dfrac{A_2}{A_1}\Big)^2\Big) \;=\; \dfrac{2\,(P_1-P_2)}{\rho}.
$$
Thus

$$
P_1-P_2 = \rho_m\,g\,(h_2-h_1) \equiv \rho_m\,g\,\Delta h.
$$

Substitute into the velocity expression:
$$
\boxed{%
V_2 \;=\; \sqrt{\dfrac{\,2\,g\,\Delta h\,\rho_m\,}{\,\rho_a\,[\,1-(A_2/A_1)^2\,]}}.
}
$$

**Terms:**  
- $A_1, A_2$ = cross-sectional areas at the inlet (1) and exit (2) of the convergent section  
- $\rho_m$ = manometric fluid density
- $\rho_a$ = air (flowing fluid) density  
- $\Delta h = h_2 - h_1$ = difference in manometer column heights (both open to atmosphere)

---

#### Velocity from a Pitot–static probe (general form)

Pitot measures total (stagnation) pressure $P_t$ and static nearby is $P_s$.  
By Bernoulli along that streamline:

$$
P_t - P_s = \rho_m g \Delta h.
$$

Substitute into Bernoulli and solve for $V$:
$$
\rho_m g \Delta h = \tfrac{1}{2}\rho_a V^2
\quad\Rightarrow\quad
V = \sqrt{\dfrac{2\,g\,\Delta h\,\rho_m}{\rho_a}}.
$$

**Terms:**  
- $P_t$ = total (stagnation) pressure measured by Pitot opening  
- $P_s$ = static pressure from static port
- $\rho_m$ = manometric fluid density
- $\rho_a$ = air (flowing fluid) density
- $\Delta h$ = difference in manometer column heights

**Note:**  
Applies for **incompressible and inviscid** flow. For compressible or high-Mach flows, use compressible Pitot relations.

#### Difference between Static, Dynamic, and Total Pressure

| Type of Pressure                | Symbol                     | Definition / Meaning                                                   | Measurement Method                                        |
| ------------------------------- | -------------------------- | ---------------------------------------------------------------------- | --------------------------------------------------------- |
| **Static Pressure**             | $P_s$                      | Pressure exerted by fluid at rest or acting equally in all directions. | Measured by a static port (hole parallel to flow).        |
| **Dynamic Pressure**            | $q = \tfrac{1}{2}\rho V^2$ | Pressure due to fluid motion (kinetic energy per unit volume).         | Calculated from velocity or from Pitot–static difference. |
| **Total (Stagnation) Pressure** | $P_t = P_s + q$            | Pressure if fluid is brought to rest isentropically.                   | Measured by Pitot tube facing the flow.                   |

#### Steps to perform experiment

1. Start starter motor (30 rpm).
2. Start main motor, ramp to first rpm (100 rpm).
3. Wait for stable flow.
4. Record manometer readings (inclined at $30^\circ$ and straight tube).
5. Repeat for each rpm: 100, 200, 300, 400, 500.
6. Calculate $V$ for each rpm using the above formula.
7. Plot $V$ vs rpm and check for linearity.
---
