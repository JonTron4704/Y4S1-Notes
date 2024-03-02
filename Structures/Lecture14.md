# Torsion of Closed-Section Beams


In closed-section beams, torque does NOT cause normal stresses. $\sigma_z = \sigma_s = 0$
- $\dfrac{\partial q}{\partial S} + t \dfrac{\partial \sigma_Z}{\partial z} = 0$
- $\dfrac{\partial q}{\partial z} + t \dfrac{\partial \sigma_S}{\partial S} = 0$

This gives us:
- $\dfrac{\partial q}{\partial S} = 0$
- $\dfrac{\partial q}{\partial z} = 0$

This tells the application of pure torque to a closed-section beam creates a constant shear flow. 

If $q$ is constant, $\tau \not =$ constant if $t = t(S)$
- $T = R \oint q dS$

If $q$ is constant:
- $T = Rq \oint dS$
- $T = Rq 2\pi R$
- $T = 2\pi R^2 q$
- $T = 2Aq$

Solving for $q$:
- $q = \dfrac{T}{2A}$
- This is known as the "Bread-Batho Formula"
- $A$ is the area enclosed by the midline of the cross-section

If $q$ is constant:
- $\dfrac{d\theta}{dz} = \dfrac{1}{2A} \oint \dfrac{q}{Gt}dS$
- $\dfrac{d\theta}{dz} = \dfrac{q}{2A} \oint \dfrac{dS}{Gt}$

Substituting in the equation $q = \dfrac{T}{2A}$:
- $\dfrac{d\theta}{dz} = \dfrac{T}{4A^2} \oint \dfrac{dS}{Gt}$
- This is the rate of twist for Bread-Batho flow.

# Example 14.1

Figure 1

Given:
- Circular Beam
- Loading: $T = 30 kNm$
- Material Properties: $G = 25 GPa$
- Constraints:
  - $\tau_{allow} = 200 MPa$ (strength)
  - $\theta_{allow} = 2\degree$ (stiffness)
- Geometry:
  - $d = 200mm$
  - $L = 2m = 2000 mm$

Find: 
- Find $t_{min}$ based on the given constraints

Solution:
- This problem is statically indeterminate. This means that the static equilibrium equations are not enough to solve the problem.
- $T_a + T_b - T = 0$
- Both $T_a$ and $T_b$ are unknown, and generally they are not equal to each other, so we cannot assume that either.

To solve this we need to know the internal forces within the beam. We use the Method of Sections.
- Refer to figure 2.
- Using the right hand rule, if you curl your fingers in the direction of the torque, and your thumb points towards the beam, that is POSITIVE. If your thumb points away, that is NEGATIVE.

Solving for the angle of twist:
- $\theta_{AB} = \sum \dfrac{T_i L_i}{J_i G_i}$
- $\theta_{AB} = \dfrac{L_i}{JG} \sum T_i$ 
- $\theta_{AB} = \dfrac{L_i}{JG} (T_{AC} + T_{CB})$
- $\theta_{AB} = \dfrac{L_i}{JG} (-T_A + T_B) = 0$

Since it's equal to zero we drop the $\dfrac{L_I}{JG}$ term.
- $T_B - T_A = 0$

Using $T_a + T_b - T = 0$ (eq1) and $T_B - T_A = 0$ (eq2):
- $T_A = T_B = \dfrac{T}{2}$

Using the strength constaint, $\tau \le \tau_{allow}$
- $T_{AC} = T_{CB} = \dfrac{T}{2} = 2A q = \dfrac{2 \pi d^2}{4}(\tau t)$
- $\tau = \dfrac{T}{\pi d^2 t} \le \tau_{allow}$

We can then solve for the thickness 
- $t \ge \dfrac{T}{\pi d^2 \tau_{allow}}$

Substituting in numbers:
- $t \ge \dfrac{30 \times 10^6}{\pi (200^2)(200)} = 1.2 mm$

This satifies the strength constaint. However, we must stil consider the stiffness constraint.
- $\theta_{max} \le \theta_{allow} = 2\degree$

Using the angle of twist equation found before:
- $\dfrac{d \theta}{dZ} = \dfrac{T}{4A^2} \oint \dfrac{dS}{Gt}$

<br>

- $\dfrac{d \theta}{dZ} = \dfrac{T}{4A^2 Gt} \oint dS$

<br>

- $\dfrac{d \theta}{dZ} = \dfrac{T \pi d}{4A^2 Gt}$

<br>

- $d\theta = \dfrac{T\pi d}{4A^2 Gt}dZ$

<br>

- $\theta = \dfrac{T \pi d}{4A^2 Gt}Z + C_1$

$C_1$ is a constant of integration
- When $Z = 0 \rightarrow \theta = 0 \Rightarrow C_1 = 0$
- $\theta = \dfrac{T \pi d}{4A^2 Gt}Z$

Looking at $\theta_{max}$:
- $\theta = \theta_{max}$ at the midspan, where $Z = \dfrac{L}{2}$
- $\theta_{max} = \dfrac{T \pi d}{4 A^2 Gt} \dfrac{L}{2} \le \theta_{allow}$
- NOTE!! $\theta_{allow}$ must be stated in Radians because the calculated result will be in radians.

Solving for thickness:
- $t \ge \dfrac{T \pi Ld}{8 A^2 G \theta_{allow}}$
- $t \ge \dfrac{30\times 10^6 \pi (200)(2000)}{8 \left(\dfrac{\pi \times 200^2}{4} \right)^2\times 25,000 \times \dfrac{2\degree \pi}{180\degree})} = 2.7mm$

Now comparing this thickness to the one from the strength condition. It must satisfy both:
- $t_{min} = \textrm{max}[t_\textrm{stiffness}, t_\textrm{strength}] = 2.7mm$

# Torsion in Open-Section Beams

Looking at open section beams and skipping the derivation:

Figure 3

From deformable bodies:
- $\theta = \dfrac{TL}{GJ}$

For the differential element:
- $d\theta = \dfrac{TdZ}{GJ}$

Solving for the rate of angular twist:
- $\dfrac{d\theta}{dZ} = \dfrac{T}{GJ}$

J is solved by looking at each segment (S):
- $J = \sum \dfrac{S t^3}{3}$

Using shear stress:
- $\tau = \dfrac{T}{J} 2n$
- $\tau = \tau_{max}$ when $n = n_{max} = \pm \dfrac{t}{2}$
- $\tau_{max} = \dfrac{T}{J} t$
  - $J$ is the same in both equations 

# Example 14.2

Open-section beam problem

Figure 4

Given:
- $T = 10 Nm$
- $G = 25 GPa$

Find:
- $\tau_{max}$

$\tau_{max}$ occurs where $t = t_{max} = 2.5mm$

We calculate J:
- $J = \sum \dfrac{S t^3}{3}$
- $J = \dfrac{1}{3} \left( 25\times1.5^3\times 2 + 50\times2.5^3 \right)$
  - We multiply by two in the first term because the top and bottom segments are identical.
- $J = 316.7 mm^4$

Now find $\tau_{max}$:
- $\tau_{max} = \dfrac{T}{J} t_{max} = \dfrac{10^4 Nmm}{316.7 mm^4} \times 2.5mm$
- $\tau_{max} = 78.9 MPa$
- $\tau_{max} \le \tau_{allow}$