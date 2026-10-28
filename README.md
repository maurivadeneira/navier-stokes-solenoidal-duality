# Solenoidal Vorticity Duality and Neck-Curvature Bounds in the 3D Incompressible Navier-Stokes Equations

**Author:** Mauricio Rivadeneira Mora  
**Status:** Working Manuscript (Pure Mathematical Analysis)

## Abstract / Core Hypothesis

This repository contains the formal mathematical development investigating the exclusion of finite-time blow-up in the classical three-dimensional incompressible Navier-Stokes equations on $\mathbb{R}^3$:

$$\partial_t \mathbf{u} + (\mathbf{u} \cdot \nabla)\mathbf{u} = -\nabla p + \nu \Delta \mathbf{u}, \qquad \nabla \cdot \mathbf{u} = 0$$

Without invoking external physical regularizations, this work explores a strictly geometric and functional *reductio ad absurdum* based on the simultaneous enforcement of the two fundamental divergence-free constraints of the system:

1. **Isochoric volume preservation:** $\nabla \cdot \mathbf{u} = 0 \implies \det(D\Phi_t) \equiv 1$.
2. **Solenoidal vorticity conservation:** $\nabla \cdot \boldsymbol{\omega} = \nabla \cdot (\nabla \times \mathbf{u}) \equiv 0$.

### The Neck-Curvature Geometric Trap

Any hypothetical finite-time singularity at $t \to T^*$ preserving the global Leray energy identity

$$\frac{1}{2} \Vert \mathbf{u}(t) \Vert_{L^2}^2 + \nu \int_0^t \Vert \boldsymbol{\omega}(s) \Vert_{L^2}^2 \, ds = E_0 < \infty$$

requires vortex tubes of circulation $\Gamma > 0$ to concentrate transversely ($r \to 0$) within an axially localized neck of length $L(r)$. We analyze the exact orthogonal decomposition of the enstrophy dissipation:

$$\nu \int_{\mathbb{R}^3} |\nabla \boldsymbol{\omega}|^2 \, dV = \nu \int_{\mathbb{R}^3} \big|\nabla |\boldsymbol{\omega}|\big|^2 \, dV + \nu \int_{\mathbb{R}^3} |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV, \qquad \boldsymbol{\xi} = \frac{\boldsymbol{\omega}}{|\boldsymbol{\omega}|}$$

coupled with the cylindrical solenoidal identity $\partial_z \omega_z + \frac{1}{r}\partial_r(r \omega_r) = 0$. This coupling establishes an analytical duality:
- **Regime I (Long Neck, $L \gg r$):** Direction fields remain regular ($|\nabla \boldsymbol{\xi}|$ bounded), activating the Constantin-Fefferman regularity mechanism while forcing the local enstrophy volume integral to violate the Leray bound $E_0$.
- **Regime II (Short Neck / Hourglass Collapse, $L \sim r$):** Evading the volumetric enstrophy bound via axial localization forces an abrupt radial flaring of vortex lines ($\omega_r \sim (r/L)\omega_z$), driving the directional curvature $|\nabla \boldsymbol{\xi}| \sim 1/L \sim 1/r$ to infinity and triggering a compensatory blow-up in the geometric dissipation term $\nu \int |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV$.

## Manuscript Structure
1. **Introduction and Classical Formulation ($\mathbb{R}^3$)**
2. **Exact Orthogonal Decomposition of the Vorticity Gradient**
3. **The Solenoidal Constraint $\nabla \cdot \boldsymbol{\omega} = 0$ in Local Vortex Coordinates**
4. **Quantitative Duality Between Axial Localization ($L$) and Directional Curvature ($|\nabla \boldsymbol{\xi}|$)**
5. **Energy-Enstrophy Compatibility and Exclusion of Self-Similar Neck Collapse**

Iniciamos desde cero el desarrollo de un nuevo paper de Matemática Pura sobre las ecuaciones clásicas incompresibles de Navier-Stokes en R^3:
∂_t u + (u · ∇)u = -∇p + ν Δu, con ∇ · u = 0 y dato inicial suave de energía finita E_0.

Regla estricta de este proyecto: Cero hipótesis físicas externas (no usamos corte espectral Λ ni tiempo de relajación τ). Trabajamos exclusivamente con análisis funcional, geometría diferencial y cálculo vectorial exacto sobre la ecuación clásica.

El objetivo es desarrollar rigurosamente la "Dualidad Geométrica Cuello-Curvatura" para acorralar por reducción al absurdo el colapso puntual (tipo reloj de arena) usando tres herramientas exactas:
1. La conservación de volumen Lagrangiano (∇ · u = 0) y la identidad global de Leray: (1/2)||u(t)||_{L^2}^2 + ν ∫_0^t ||ω(s)||_{L^2}^2 ds = E_0.
2. La condición solenoidal exacta de la vorticidad: ∇ · ω = ∇ · (∇ × u) ≡ 0, que prohíbe que las líneas de vorticidad nazcan o mueran en el cuello de radio r -> 0 y obliga a que ∂_z ω_z = -(1/r) ∂_r(r ω_r).
3. La identidad exacta de descomposición ortogonal de la disipación de enstrofía (conectada al criterio de Constantin-Fefferman con ξ = ω / |ω|):
   |∇ω|^2 = |∇|ω||^2 + |ω|^2 |∇ξ|^2.

Arranquemos por la Sección 2: demostremos paso a paso y con rigor algebraico absoluto la identidad puntual |∇ω|^2 = |∇|ω||^2 + |ω|^2 |∇ξ|^2 y conectémosla con ∇ · ω = 0 para acotar inferiormente |∇ξ|^2 en función de la escala axial L y radial r del tubo.
