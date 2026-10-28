# Dualidad de Vorticidad Solenoidal y Cotas de Curvatura de Cuello en las Ecuaciones de Navier-Stokes Incompresibles 3D

**Autor:** Mauricio Rivadeneira Mora  
**Estado:** Manuscrito de Trabajo (Análisis Matemático Puro)

## Resumen / Hipótesis Central

Este repositorio contiene el desarrollo matemático formal que investiga la exclusión de la explosión en tiempo finito (*finite-time blow-up*) en las ecuaciones clásicas tridimensionales e incompresibles de Navier-Stokes sobre $\mathbb{R}^3$:

$$\partial_t \mathbf{u} + (\mathbf{u} \cdot \nabla)\mathbf{u} = -\nabla p + \nu \Delta \mathbf{u}, \qquad \nabla \cdot \mathbf{u} = 0$$

Sin invocar regularizaciones físicas externas, este trabajo explora una reducción al absurdo (*reductio ad absurdum*) estrictamente geométrica y funcional basada en la imposición simultánea de las dos restricciones fundamentales libres de divergencia del sistema:

1. **Conservación del volumen isocórico:** $\nabla \cdot \mathbf{u} = 0 \implies \det(D\Phi_t) \equiv 1$.
2. **Conservación solenoidal de la vorticidad:** $\nabla \cdot \boldsymbol{\omega} = \nabla \cdot (\nabla \times \mathbf{u}) \equiv 0$.

### La Trampa Geométrica de Cuello-Curvatura

Cualquier singularidad hipotética en tiempo finito cuando $t \to T^*$, preservando la identidad global de energía de Leray

$$\frac{1}{2} \Vert \mathbf{u}(t) \Vert_{L^2}^2 + \nu \int_0^t \Vert \boldsymbol{\omega}(s) \Vert_{L^2}^2 \, ds = E_0 < \infty$$

requiere que los tubos de vorticidad de circulación $\Gamma > 0$ se concentren transversalmente ($r \to 0$) dentro de un cuello axialmente localizado de longitud $L(r)$. Analizamos la descomposición ortogonal exacta de la disipación de enstrofía:

$$\nu \int_{\mathbb{R}^3} |\nabla \boldsymbol{\omega}|^2 \, dV = \nu \int_{\mathbb{R}^3} \big|\nabla |\boldsymbol{\omega}|\big|^2 \, dV + \nu \int_{\mathbb{R}^3} |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV, \qquad \boldsymbol{\xi} = \frac{\boldsymbol{\omega}}{|\boldsymbol{\omega}|}$$

acoplada con la identidad solenoidal cilíndrica $\partial_z \omega_z + \frac{1}{r}\partial_r(r \omega_r) = 0$. Este acoplamiento establece una dualidad analítica:
- **Régimen I (Cuello Largo, $L \gg r$):** Los campos de dirección permanecen regulares ($|\nabla \boldsymbol{\xi}|$ acotado), activando el mecanismo de regularidad de Constantin-Fefferman al tiempo que fuerzan a la integral de volumen de enstrofía local a violar la cota de Leray $E_0$.
- **Régimen II (Cuello Corto / Colapso en Reloj de Arena, $L \sim r$):** Evadir la cota volumétrica de enstrofía mediante localización axial fuerza una abertura radial abrupta de las líneas de vorticidad ($\omega_r \sim (r/L)\omega_z$), llevando la curvatura direccional $|\nabla \boldsymbol{\xi}| \sim 1/L \sim 1/r$ hacia el infinito y desencadenando una explosión compensatoria en el término de disipación geométrica $\nu \int |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV$.

## Estructura del Manuscrito
1. **Introducción y Formulación Clásica ($\mathbb{R}^3$)**
2. **Descomposición Ortogonal Exacta del Gradiente de Vorticidad**
3. **La Restricción Solenoidal $\nabla \cdot \boldsymbol{\omega} = 0$ en Coordenadas Locales de Vorticidad**
4. **Dualidad Cuantitativa Entre Localización Axial ($L$) y Curvatura Direccional ($|\nabla \boldsymbol{\xi}|$)**
5. **Compatibilidad Energía-Enstrofía y Exclusión del Colapso Autossimilar de Cuello**
