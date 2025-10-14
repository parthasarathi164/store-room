## what is ansys APDL?

Ansys APDL (Ansys [Parametric Design Language](https://www.google.com/search?sca_esv=650ecf1b08cfc5b0&sxsrf=AE3TifNymkUK21TBhXyU6623WFM8kSLszg%3A1760239994039&q=Parametric+Design+Language&sa=X&sqi=2&ved=2ahUKEwiHv8H83J2QAxXnSGcHHddqB18QxccNegQILBAB&mstk=AUtExfBiYewJvJfyf51YjoD6_p6INbJUR2W7n_X2_9ZmorHCiJGUnPH7nL0azQsZtwumpy9-jS5IEJPb-6S44gHd6OFXs6THYe9ymUOs-kSOkCmbHooxbcTiOJ9xKyawUzY1IGDm9XXdbGqk9tZFGHv8Pc5zF0fd69KTmgWXRFPbYyVGDhHNvtdNxNTkt13cw4v7hVN_XvsvFghW2Pjcg_DSix7NfHQ_Z_pSPwzsdneH0Nh8iD6WSydyMDBK-H4wVAvExLC64kjxO0xJI-lKN-pdmy8k&csui=3)) is ==a scripting language used to control and automate the Ansys Mechanical finite element analysis (FEA) solver==. It enables users to define geometries, set solver parameters, customize workflows, and develop custom applications, providing deeper access to the software's capabilities beyond the standard graphical user interface (GUI). APDL is utilized for parametric design, batch processing, and fine-tuning complex simulations.

**importance**
- we use this in our FEM lab.
- 

## 1D Bar Element Stiffness Matrix (Natural Coordinates)

### 1. Shape Functions
Shape functions describe how nodal displacements influence any point inside the element. For a linear element between node 1 ($\xi = -1$) and node 2 ($\xi = 1$):
$$
N_1(\xi) = \frac{1 - \xi}{2}
$$
$$
N_2(\xi) = \frac{1 + \xi}{2}
$$
So, displacement inside the element is:
$$
u(\xi) = N_1(\xi) u_1 + N_2(\xi) u_2
$$

### 2. Strain-Displacement
Strain is the spatial derivative of displacement, relating how much the bar stretches:
$$
\varepsilon = \frac{du}{dx}
$$
The coordinate transformation uses the Jacobian $dx/d\xi = L/2$, so $d\xi/dx = 2/L$. This gives:
$$
\frac{dN_1}{dx} = -\frac{1}{L}, \quad \frac{dN_2}{dx} = \frac{1}{L}
$$
Thus, strain varies linearly with nodal displacements:
$$
\varepsilon = -\frac{1}{L} u_1 + \frac{1}{L} u_2
$$

### 3. Stiffness Matrix
The stiffness matrix quantifies how much force is needed at each node for a given displacement, based on material ($E$), area ($A$), and length ($L$). By applying the energy principle:
$$
K = \int_0^L EA \left[\frac{dN}{dx}\right]^T \left[\frac{dN}{dx}\right] dx
$$
For this element, the derivatives are constant, so the integration is straightforward:
$$
K = \frac{EA}{L}
\begin{bmatrix}
1 & -1 \\
-1 & 1
\end{bmatrix}
$$

### 4. Final Equation
In matrix form, the equilibrium of forces and displacements at the nodes is:
$$
F = K X
$$
Here:
- $F$ is the vector of nodal forces,
- $K$ is the element stiffness matrix,
- $X$ is the vector of nodal displacements.
---
## 1D Bar Element Strain Matrix (B-matrix)

### Derivation and Explanation
The B-matrix links nodal displacements to the strain at any point in the element. For a 1D linear element, displacement at any $\xi$ is:
$$
u(\xi) = N_1(\xi) u_1 + N_2(\xi) u_2
$$
Strain is the spatial derivative of displacement:
$$
\varepsilon = \frac{du}{dx}
$$
Apply the chain rule using the Jacobian ($dx/d\xi = L/2$):
$$
\frac{du}{dx} = \frac{du}{d\xi} \cdot \frac{d\xi}{dx}
$$

Shape function derivatives:
- $dN_1/d\xi = -1/2$, $dN_2/d\xi = 1/2$
- $d\xi/dx = 2/L$

So, with respect to $x$:
$$
\frac{dN_1}{dx} = \left(-\frac{1}{2}\right) \frac{2}{L} = -\frac{1}{L}
$$
$$
\frac{dN_2}{dx} = \left(\frac{1}{2}\right) \frac{2}{L} = \frac{1}{L}
$$
Thus, for the element:
$$
\varepsilon = -\frac{1}{L} u_1 + \frac{1}{L} u_2
$$
Or in matrix form:
$$
\varepsilon = 
\begin{bmatrix}
-\frac{1}{L} & \frac{1}{L}
\end{bmatrix}
\begin{bmatrix}
u_1 \\
u_2
\end{bmatrix}
$$
So, the **strain matrix** (B-matrix) is:
$$
B = \begin{bmatrix} -\frac{1}{L} & \frac{1}{L} \end{bmatrix}
$$
- B-matrix transforms nodal displacements into strain for a 1D bar element.
---
## Bar vs Beam Element (DOF)

- **Bar element:** Each node has only one degree of freedom (translational/axial).
- **Beam element:** Each node has multiple degrees of freedom, including translational and rotational (typically 2 or 3 per node).
---
## 2-Element Cantilever Bar FEM Solution (SI Units)

**Given:**  
- Bar length $L = 0.1\ \text{m}$  
- Cross-section $A = 2 \times 10^{-4}\ \text{m}^2$  
- Young's modulus $E = 2 \times 10^{11}\ \text{N/m}^2$  
- Fixed at $x = 0$; load $F = 1{,}000\ \text{N}$ at $x = 0.1\ \text{m}$  
- Divide into 2 elements: $L_e = 0.05\ \text{m}$ each  

### 1. Stiffness Matrix for Each Element
$$
K_e = \frac{EA}{L_e} 
\begin{bmatrix}
1 & -1 \\
-1 & 1
\end{bmatrix}
$$
Substitute:  
$$
K_e = \frac{2 \times 10^{11} \times 2 \times 10^{-4}}{0.05} = 8 \times 10^8\ \text{N/m}
$$
So,  
$$
K_e = 8 \times 10^8
\begin{bmatrix}
1 & -1 \\
-1 & 1
\end{bmatrix}\,\text{N/m}
$$

### 2. Global Stiffness Matrix
With nodes $u_0$ (fixed), $u_1$, $u_2$:  
$$
K = 8 \times 10^8
\begin{bmatrix}
1 & -1 & 0 \\
-1 & 2 & -1 \\
0 & -1 & 1
\end{bmatrix}
$$

### 3. Boundary & Loading Conditions
- $u_0 = 0$ (fixed)
- $F_1 = 0$
- $F_2 = 1{,}000\ \text{N}$

Equation system for free nodes ($u_1$, $u_2$):
$$
\begin{bmatrix}
2 & -1 \\
-1 & 1 \\
\end{bmatrix}
\begin{Bmatrix}
u_1 \\ u_2
\end{Bmatrix}
= \frac{1}{8 \times 10^8}
\begin{Bmatrix}
0 \\ 1{,}000
\end{Bmatrix}
$$

Or, plugging in $K_e$:
$$
\begin{bmatrix}
1.6 \times 10^9 & -8 \times 10^8 \\
-8 \times 10^8 & 8 \times 10^8
\end{bmatrix}
\begin{Bmatrix}
u_1 \\ u_2
\end{Bmatrix}
=
\begin{Bmatrix}
0 \\ 1{,}000
\end{Bmatrix}
$$

### 4. Displacements
- $-8 \times 10^8 u_1 + 8 \times 10^8 u_2 = 1{,}000$
- $u_2 = u_1 + \frac{1{,}000}{8 \times 10^8} = u_1 + 1.25 \times 10^{-6}$

Now plug into main equation:
- $1.6 \times 10^9 u_1 - 8 \times 10^8 (u_1 + 1.25 \times 10^{-6}) = 0$
- $1.6 \times 10^9 u_1 - 8 \times 10^8 u_1 - 1{,}000 = 0$
- $8 \times 10^8 u_1 = 1{,}000$
- $u_1 = \frac{1{,}000}{8 \times 10^8} = 1.25 \times 10^{-6}\ \text{m}$  
- $u_2 = 1.25 \times 10^{-6} + 1.25 \times 10^{-6} = 2.5 \times 10^{-6}\ \text{m}$

So:  
- $u_0 = 0$
- $u_1 = 1.25 \times 10^{-6}\ \text{m}$
- $u_2 = 2.5 \times 10^{-6}\ \text{m}$

### 5. Strain in Each Element
$$
\varepsilon_e = \frac{1}{L}\begin{bmatrix} -1 & 1 \end{bmatrix}
\begin{bmatrix} u_i \\ u_j \end{bmatrix}
$$
- **Element 1:** $\varepsilon_1 = \frac{1.25 \times 10^{-6} - 0}{0.05} = 2.5 \times 10^{-5}$
- **Element 2:** $\varepsilon_2 = \frac{2.5 \times 10^{-6} - 1.25 \times 10^{-6}}{0.05} = 2.5 \times 10^{-5}$

### 6. Stress in Each Element
$$
\sigma_e = E\varepsilon_e = 2 \times 10^{11} \times 2.5 \times 10^{-5} = 5 \times 10^6\ \text{N/m}^2 = 5\ \text{MPa}
$$

### Summary Table

| Node | Displacement (m)     | Strain (element)    | Stress (N/m$^2$) |
|------|----------------------|---------------------|------------------|
| 0    | $0$                  | $2.5 \times 10^{-5}$ (Elem 1)  | $5 \times 10^{6}$ (Elem 1) |
| 1    | $1.25 \times 10^{-6}$| $2.5 \times 10^{-5}$ (Elem 2)  | $5 \times 10^{6}$ (Elem 2) |
| 2    | $2.5 \times 10^{-6}$ |                     |                  |

---

