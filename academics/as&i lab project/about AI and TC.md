#### images about turn and roll

![[turn due to bank.png]]
`above fig: how turn happens`

![[TC and AI.png]]
`above fig: turn coordinator and Attitude Indicator`

![[modern AI.png]]
`modern AI`

---
#### Turn Coordinator

It shows **rate of turn** and **quality of turn**.

- Works using a **gyroscope** whose axis is tilted about 30° upward from the longitudinal axis.
- When the aircraft **yaws or rolls**, the gyroscopic precession makes the pointer (airplane symbol) tilt and move.
- It shows **rate of turn** (how fast the aircraft is turning) and whether the turn is **coordinated** (ball centered).

Rate of turn ($\dot{\psi}$) is related to bank angle ($\phi$) and true airspeed ($V$):

$$
\dot{\psi} = \frac{g \tan\phi}{V}
$$

- If the ball is centered → **coordinated turn**  
- Ball to inside → **slip**
- Ball to outside → **skid**

Output to pilot:
→ Turn direction and coordination (turn rate, slip/skid)

---
#### Attitude Indicator

It shows **pitch** and **bank (roll)** angles of the aircraft.

- Uses a **gyroscope** that stays fixed in space due to rigidity.
- The aircraft moves around the gyro, and the **artificial horizon** moves accordingly.

Outputs to pilot:  
- **Pitch angle ($\theta$)** → aircraft nose up/down
- **Bank (roll) angle ($\phi$)** → wings level, left or right bank
---
#### Roll Rate
- What it is: How fast the aircraft rolls about its longitudinal axis (banks left or right).
- Formula:
  $$
  p = \frac{d\phi}{dt}
  $$
  where $\phi$ = bank angle (roll angle).
- Cockpit indication: Displayed on the Attitude Indicator (AI) or Primary Flight Display (PFD) as the rate at which the horizon bar tilts; also measured by the roll-rate gyro (symbol $p$). It also visually represents the aircraft's pitch (nose up/down, affecting the horizon's vertical position).
---
#### traditional v/s modern system
| Instrument             | Traditional              | Modern (Boeing/Airbus PFD)                                | Key Integration                                   |
| ---------------------- | ------------------------ | --------------------------------------------------------- | ------------------------------------------------- |
| **Attitude Indicator** | Mechanical gyro horizon  | Electronic EADI with pitch/bank ladder & trends           | Center of PFD; synthetic horizon line             |
| **Turn Coordinator**   | Gyro + inclinometer ball | Graphical slip/skid (ball/triangle) + heading rate vector | Bottom of attitude display; yaw damper automation |

---
