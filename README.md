# Dualidad de Vorticidad Solenoidal y Cotas de Curvatura de Cuello en las Ecuaciones de Navier-Stokes Incompresibles 3D

**Autor:** Mauricio Rivadeneira Mora  
**Documento:** Manuscrito Técnico Completo (Matemática Pura)

---

## 1. Introducción y Formulación Clásica en $\mathbb{R}^3$

Consideramos el problema de valor inicial para las ecuaciones clásicas tridimensionales e incompresibles de Navier-Stokes en todo el espacio $\mathbb{R}^3$:

$$\partial_t \mathbf{u} + (\mathbf{u} \cdot \nabla)\mathbf{u} = -\nabla p + \nu \Delta \mathbf{u}, \qquad (x, t) \in \mathbb{R}^3 \times [0, T)$$

$$\nabla \cdot \mathbf{u} = 0, \qquad \mathbf{u}(x, 0) = \mathbf{u}_0(x)$$

donde $\mathbf{u}: \mathbb{R}^3 \times [0, T) \to \mathbb{R}^3$ es el campo de velocidades, $p: \mathbb{R}^3 \times [0, T) \to \mathbb{R}$ es la presión escalar, y $\nu > 0$ es la viscosidad cinemática constante. Asumimos un dato inicial suave y libre de divergencia $\mathbf{u}_0 \in C^\infty(\mathbb{R}^3)$ con decaimiento rápido en el infinito, tal que la energía cinética inicial es estrictamente finita:

$$E_0 := \frac{1}{2} \int_{\mathbb{R}^3} |\mathbf{u}_0(x)|^2 \, dV < \infty$$

### 1.1. Identidades Globales de Conservación (Energía y Enstrofía)

Definimos el campo de vorticidad como el rotacional de la velocidad:

$$\boldsymbol{\omega} := \nabla \times \mathbf{u}$$

Debido a la identidad vectorial $\Delta \mathbf{u} = \nabla(\nabla \cdot \mathbf{u}) - \nabla \times (\nabla \times \mathbf{u})$ y a la condición de incompresibilidad $\nabla \cdot \mathbf{u} = 0$, la disipación viscosa de energía equivale exactamente a la norma $L^2$ de la vorticidad (enstrofía). Toda solución suave en $[0, T)$ satisface la **Identidad Global de Energía de Leray**:

$$\frac{1}{2} \int_{\mathbb{R}^3} |\mathbf{u}(x, t)|^2 \, dV + \nu \int_0^t \int_{\mathbb{R}^3} |\boldsymbol{\omega}(x, s)|^2 \, dV \, ds = E_0 \qquad \forall t \in [0, T)$$

En consecuencia, la integral espacio-temporal de la enstrofía posee una cota superior absoluta e inquebrantable independiente de $t$:

$$\int_0^T \int_{\mathbb{R}^3} |\boldsymbol{\omega}(x, s)|^2 \, dV \, ds \le \frac{E_0}{\nu} < \infty$$

Por otra parte, aplicando el operador rotacional a la ecuación de momento se obtiene la ecuación de evolución de la vorticidad:

$$\partial_t \boldsymbol{\omega} + (\mathbf{u} \cdot \nabla)\boldsymbol{\omega} = (\boldsymbol{\omega} \cdot \nabla)\mathbf{u} + \nu \Delta \boldsymbol{\omega}$$

Multiplicando escalarmente por $\boldsymbol{\omega}$ e integrando por partes en $\mathbb{R}^3$, se obtiene la **Identidad Exacta de Evolución de la Enstrofía**:

$$\frac{1}{2} \frac{d}{dt} \int_{\mathbb{R}^3} |\boldsymbol{\omega}|^2 \, dV = \int_{\mathbb{R}^3} (\boldsymbol{\omega} \cdot \mathbf{D} \cdot \boldsymbol{\omega}) \, dV - \nu \int_{\mathbb{R}^3} |\nabla \boldsymbol{\omega}|^2 \, dV$$

donde $\mathbf{D} := \frac{1}{2}(\nabla \mathbf{u} + (\nabla \mathbf{u})^T)$ es el tensor simétrico de tasa de deformación, cuya traza es nula ($\operatorname{tr}(\mathbf{D}) = \nabla \cdot \mathbf{u} = 0$).

### 1.2. Las Dos Restricciones Solenoidales Exactas

El sistema posee dos leyes estructurales de divergencia nula que operan simultáneamente en cada punto $(x,t) \in \mathbb{R}^3 \times [0,T)$:

1. **Incompresibilidad del flujo (conservación del volumen Lagrangiano):** $\nabla \cdot \mathbf{u} = 0$. El flujo Lagrangiano asociado $\Phi_t: \mathbb{R}^3 \to \mathbb{R}^3$ preserva la medida de Lebesgue ($\det(D\Phi_t) \equiv 1$).
2. **Condición solenoidal de la vorticidad (conservación topológica del flujo rotacional):** Por identidad diferencial elemental sobre formas exactas, la divergencia de un rotacional es idénticamente nula:

$$\nabla \cdot \boldsymbol{\omega} = \nabla \cdot (\nabla \times \mathbf{u}) \equiv 0$$

---

## 2. Descomposición Ortogonal Exacta del Gradiente de Vorticidad y Cotas Integrales de Tubo

En esta sección demostramos dos lemas rigurosos: primero, que la disipación viscosa de enstrofía se separa de forma exacta en una componente de amplitud y una componente geométrica de curvatura direccional; segundo, que la condición $\nabla \cdot \boldsymbol{\omega} = 0$ impone una desigualdad inferior exacta sobre la enstrofía de cualquier tubo de vorticidad en función del área de su sección transversal.

### Lema 2.1 (Identidad de Descomposición Ortogonal de $|\nabla \boldsymbol{\omega}|^2$)

*Sea $\Omega_+ := \{x \in \mathbb{R}^3 : |\boldsymbol{\omega}(x, t)| > 0\}$ el soporte activo de la vorticidad, y sea $\boldsymbol{\xi}(x, t) := \frac{\boldsymbol{\omega}(x, t)}{|\boldsymbol{\omega}(x, t)|} \in \mathbb{S}^2$ el campo vectorial unitario de dirección de la vorticidad. Entonces, en todo punto de $\Omega_+$ se cumple la identidad algebraica exacta:*

$$|\nabla \boldsymbol{\omega}|^2 = \big|\nabla |\boldsymbol{\omega}|\big|^2 + |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2$$

#### Demostración:
En $\Omega_+$, expresamos cada componente cartesiana $i \in \{1, 2, 3\}$ del vector de vorticidad como $\omega_i = |\boldsymbol{\omega}| \xi_i$. Derivando respecto a la coordenada $x_j$ ($j \in \{1, 2, 3\}$) mediante la regla de Leibniz:

$$\partial_j \omega_i = (\partial_j |\boldsymbol{\omega}|)\xi_i + |\boldsymbol{\omega}|(\partial_j \xi_i)$$

Elevando al cuadrado y sumando sobre todos los índices $i, j \in \{1, 2, 3\}$ para obtener la norma de Frobenius del tensor gradiente $|\nabla \boldsymbol{\omega}|^2 = \sum_{i,j} (\partial_j \omega_i)^2$:

$$|\nabla \boldsymbol{\omega}|^2 = \sum_{i,j=1}^3 (\partial_j |\boldsymbol{\omega}|)^2 \xi_i^2 + 2 |\boldsymbol{\omega}| \sum_{j=1}^3 (\partial_j |\boldsymbol{\omega}|) \left( \sum_{i=1}^3 \xi_i \partial_j \xi_i \right) + |\boldsymbol{\omega}|^2 \sum_{i,j=1}^3 (\partial_j \xi_i)^2$$

Dado que $\boldsymbol{\xi}$ es un vector unitario en la esfera $\mathbb{S}^2$, satisface la restricción puntual $\sum_{i=1}^3 \xi_i^2 = 1$. Derivando esta identidad constante respecto a $x_j$:

$$\partial_j \left( \sum_{i=1}^3 \xi_i^2 \right) = 2 \sum_{i=1}^3 \xi_i \partial_j \xi_i = 0 \implies \sum_{i=1}^3 \xi_i \partial_j \xi_i \equiv 0 \qquad \forall j \in \{1, 2, 3\}$$

Por ortogonalidad esférica, el término cruzado se anula idénticamente. Sustituyendo $\sum_{i=1}^3 \xi_i^2 = 1$ en el primer término y reconociendo $|\nabla \boldsymbol{\xi}|^2 = \sum_{i,j=1}^3 (\partial_j \xi_i)^2$ en el tercero, concluimos:

$$|\nabla \boldsymbol{\omega}|^2 = \sum_{j=1}^3 (\partial_j |\boldsymbol{\omega}|)^2 (1) + 0 + |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 = \big|\nabla |\boldsymbol{\omega}|\big|^2 + |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \qquad \blacksquare$$

---

### Definición 2.1 (Tubo de Vorticidad Admisible $\mathcal{T}$)

Un dominio suave y conexo $\mathcal{T} \subset \Omega_+$ se denomina un *tubo de vorticidad de longitud paramétrica $[z_1, z_2]$* si su frontera lateral $\partial_{\text{lat}} \mathcal{T}$ es una superficie formada íntegramente por líneas integrales de $\boldsymbol{\omega}$ (es decir, $\boldsymbol{\omega} \cdot \mathbf{n} = 0$ en $\partial_{\text{lat}} \mathcal{T}$, donde $\mathbf{n}$ es la normal exterior), y está foliado por una familia de secciones transversales suaves disjuntas $\{\Sigma(z)\}_{z \in [z_1, z_2]}$ de área finita $A(z) := \operatorname{Area}(\Sigma(z)) = \pi r_{\text{ef}}^2(z)$, donde $r_{\text{ef}}(z) := \sqrt{A(z)/\pi}$ define el **radio efectivo exacto** de la sección.

---

### Lema 2.2 (Invariancia Espacial del Flujo $\Gamma$ y Cota Inferior de Cauchy-Schwarz)

*Sea $\mathcal{T}$ un tubo de vorticidad admisible en un instante fijo $t$. Entonces:*
1. *El flujo de vorticidad $\Gamma := \iint_{\Sigma(z)} \boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma} \, dS$ es una constante topológica espacial independiente de la sección $z \in [z_1, z_2]$.*
2. *La integral de enstrofía sobre el tubo $\mathcal{T}$ satisface la desigualdad inferior exacta:*

$$\int_{\mathcal{T}} |\boldsymbol{\omega}|^2 \, dV \ge \Gamma^2 \int_{z_1}^{z_2} \frac{dz}{A(z)} = \frac{\Gamma^2}{\pi} \int_{z_1}^{z_2} \frac{dz}{r_{\text{ef}}^2(z)}$$

#### Demostración:
1. Para cualesquiera dos secciones $\Sigma(z_a)$ y $\Sigma(z_b)$ con $z_a < z_b$, sea $\mathcal{T}_{a,b}$ el sub-volumen del tubo comprendido entre ellas. Aplicando el Teorema de la Divergencia de Gauss al campo solenoidal $\nabla \cdot \boldsymbol{\omega} = 0$ en $\mathcal{T}_{a,b}$:

$$0 = \iiint_{\mathcal{T}_{a,b}} (\nabla \cdot \boldsymbol{\omega}) \, dV = \iint_{\Sigma(z_b)} \boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma} \, dS - \iint_{\Sigma(z_a)} \boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma} \, dS + \iint_{\partial_{\text{lat}}\mathcal{T}_{a,b}} \boldsymbol{\omega} \cdot \mathbf{n} \, dS$$

Como $\boldsymbol{\omega} \cdot \mathbf{n} = 0$ sobre la pared lateral $\partial_{\text{lat}}\mathcal{T}_{a,b}$, se obtiene $\Gamma(z_b) = \Gamma(z_a) = \Gamma = \text{cte}$.

2. Aplicando la Desigualdad de Cauchy-Schwarz en el espacio $L^2(\Sigma(z))$ a las funciones $f = 1$ y $g = \boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma}$:

$$\Gamma^2 = \left( \iint_{\Sigma(z)} 1 \cdot (\boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma}) \, dS \right)^2 \le \left( \iint_{\Sigma(z)} 1^2 \, dS \right) \left( \iint_{\Sigma(z)} (\boldsymbol{\omega} \cdot \mathbf{n}_{\Sigma})^2 \, dS \right) \le A(z) \iint_{\Sigma(z)} |\boldsymbol{\omega}|^2 \, dS$$

Dividiendo por $A(z) > 0$ e integrando a lo largo de la coordenada longitudinal $z \in [z_1, z_2]$ mediante la fórmula de la coárea (eligiendo $z$ como longitud de arco ortogonal a las secciones), se obtiene directamente:

$$\int_{\mathcal{T}} |\boldsymbol{\omega}|^2 \, dV \ge \int_{z_1}^{z_2} \left( \iint_{\Sigma(z)} |\boldsymbol{\omega}|^2 \, dS \right) dz \ge \Gamma^2 \int_{z_1}^{z_2} \frac{dz}{A(z)} = \frac{\Gamma^2}{\pi} \int_{z_1}^{z_2} \frac{dz}{r_{\text{ef}}^2(z)} \qquad \blacksquare$$
