# Dualidad de Vorticidad Solenoidal y Cotas de Curvatura de Cuello en las Ecuaciones de Navier-Stokes Incompresibles 3D

**Autor:** Mauricio Rivadeneira Mora  
**Estado:** Manuscrito de Trabajo (Análisis Matemático Puro)

## Resumen / Hipótesis Central

Este repositorio contiene el desarrollo matemático formal que investiga la exclusión de la explosión en tiempo finito (*finite-time blow-up*) en las ecuaciones clásicas tridimensionales e incompresibles de Navier-Stokes sobre $\mathbb{R}^3$:

$$\partial_t \mathbf{u} + (\mathbf{u} \cdot \nabla)\mathbf{u} = -\nabla p + \nu \Delta \mathbf{u}, \qquad \nabla \cdot \mathbf{u} = 0$$

Sin invocar regularizaciones físicas externas, este trabajo explora una reducción al absurdo (*reductio ad absurdum*) estrictamente geométrica y funcional basada en la imposición simultánea de las dos restricciones fundamentales libres de divergencia del sistema:

1. **Conservación del volumen isocórico:** $\nabla \cdot \mathbf{u} = 0 \implies \det(D\Phi_t) \equiv 1$.
2. **Conservación solenoidal de la vorticidad:** $\nabla \cdot \boldsymbol{\omega} = \nabla \cdot (\nabla \times \mathbf{u}) \equiv 0$.

---

## Estructura del Manuscrito

1. **Introducción y Formulación Clásica ($\mathbb{R}^3$)**
2. **Descomposición Ortogonal Exacta del Gradiente de Vorticidad**
3. **La Restricción Solenoidal $\nabla \cdot \boldsymbol{\omega} = 0$ en Coordenadas Locales de Vorticidad**
4. **Dualidad Cuantitativa Entre Localización Axial ($L$) y Curvatura Direccional ($|\nabla \boldsymbol{\xi}|$)**
5. **Compatibilidad Energía-Enstrofía y Exclusión del Colapso Autossimilar de Cuello**

---

## Sección 3: La Restricción Solenoidal y el Acoplamiento en Coordenadas Locales de Vorticidad

Para formalizar analíticamente la "trampa geométrica", establecemos un sistema de coordenadas cilíndricas locales $(r, \theta, z)$ centrado en el núcleo de un tubo de vorticidad que experimenta una contracción transversal hipotética hacia una escala $r \to 0$ en un intervalo temporal previo al tiempo de explosión $T^*$.

### 3.1. Despliegue de la Condición Solenoidal ($\nabla \cdot \boldsymbol{\omega} = 0$)

Por definición, el vector de vorticidad satisface idénticamente:
$$\nabla \cdot \boldsymbol{\omega} = 0$$

En coordenadas cilíndricas locales, asumiendo simetría axial aproximada ($\partial_\theta = 0$), las componentes son $\boldsymbol{\omega} = (\omega_r, 0, \omega_z)$. La divergencia se expresa estrictamente como:
$$\frac{1}{r} \frac{\partial}{\partial r} (r \omega_r) + \frac{\partial \omega_z}{\partial z} = 0$$

### 3.2. Acoplamiento entre la Escala Transversal ($r$) y la Escala Axial ($L$)

Asumiendo que el núcleo del tubo posee una vorticidad axial dominante:
$$\omega_z(r, z, t) \sim \frac{\Gamma}{\pi r^2}$$
donde $\Gamma > 0$ es la circulación invariante. Si el gradiente longitudinal decae en una escala axial característica $L(t)$ (el cuello del reloj de arena):
$$\left| \frac{\partial \omega_z}{\partial z} \right| \sim \frac{\omega_z}{L} \sim \frac{\Gamma}{\pi r^2 L}$$

Para satisfacer estrictamente $\nabla \cdot \boldsymbol{\omega} = 0$, la componente radial $\omega_r$ compensa esta variación:
$$\frac{1}{r} \frac{\partial}{\partial r} (r \omega_r) = - \frac{\partial \omega_z}{\partial z} \sim \frac{\Gamma}{\pi r^2 L}$$

Integrando desde el eje hasta el radio del núcleo:
$$\omega_r(r, z, t) \sim \frac{r}{L} \omega_z \sim \frac{\Gamma}{\pi r L}$$

---

## Sección 4: Dualidad Cuantitativa y la Exclusión del Colapso

Utilizando la identidad de descomposición ortogonal de la disipación de enstrofía:
$$\nu \int_{\mathbb{R}^3} |\nabla \boldsymbol{\omega}|^2 \, dV = \nu \int_{\mathbb{R}^3} \big|\nabla |\boldsymbol{\omega}|\big|^2 \, dV + \nu \int_{\mathbb{R}^3} |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV, \qquad \boldsymbol{\xi} = \frac{\boldsymbol{\omega}}{|\boldsymbol{\omega}|}$$

analizamos el comportamiento asintótico del término de curvatura direccional $|\nabla \boldsymbol{\xi}|$:
$$|\nabla \boldsymbol{\xi}| \sim \left| \frac{\partial \xi_r}{\partial z} \right| \sim \frac{\omega_r}{L |\boldsymbol{\omega}|} \sim \frac{1}{L}$$

### 4.1. Análisis de Regímenes

* **Régimen de Cuello Largo ($L \ge L_0 > 0$):**  
  La escala axial permanece acotada. Al evaluar la integral de volumen de enstrofía en el dominio $r \to 0$:
  $$\int_{\text{cuello}} |\boldsymbol{\omega}|^2 \, dV \sim \left( \frac{\Gamma^2}{r^4} \right) \cdot (r^2 L_0) = \frac{\Gamma^2 L_0}{r^2} \xrightarrow{r \to 0} +\infty$$
  Su integración temporal en el marco de Leray conduce a una divergencia logarítmica o de polo que **viola directamente la cota finita de energía $E_0$**.

* **Régimen de Cuello Corto / Reloj de Arena ($L \sim r$):**  
  Si el sistema permite que el cuello se achique axialmente al mismo ritmo que el radio transversal ($L \sim r$), la curvatura direccional se dispara:
  $$|\nabla \boldsymbol{\xi}| \sim \frac{1}{L} \sim \frac{1}{r}$$
  Con esto, el término de disipación geométrica en el volumen de transición $V \sim r^3$ diverge como:
  $$\nu \int_{\text{cuello}} |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV \sim \left( \frac{1}{r^4} \right) \left( \frac{1}{r^2} \right) r^3 \sim \frac{1}{r^3} \xrightarrow{r \to 0} +\infty$$
  lo que desencadena un bloqueo disipativo viscoso insalvable antes de alcanzar el tiempo crítico $T^*$.
