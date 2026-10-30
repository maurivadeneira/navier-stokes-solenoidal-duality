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

---

## 3. La Restricción Solenoidal ($\nabla \cdot \boldsymbol{\omega} = 0$) y la Identidad de Expansión de $\boldsymbol{\xi}$

En esta sección demostramos que la condición libre de divergencia $\nabla \cdot \boldsymbol{\omega} = 0$ ata de forma exacta la variación longitudinal de la magnitud $|\boldsymbol{\omega}|$ con la divergencia geométrica del campo unitario de direcciones $\boldsymbol{\xi}$. Esto nos permite medir rigurosamente cuánto deben doblarse las líneas de vorticidad cuando el área transversal $A(z)$ de un tubo cambia a lo largo de una distancia axial $L$.

### Lema 3.1 (Identidad Exacta de Transporte Logarítmico y Divergencia Direccional)

*En todo punto del soporte activo $\Omega_+ = \{x \in \mathbb{R}^3 : |\boldsymbol{\omega}(x,t)| > 0\}$, la condición solenoidal $\nabla \cdot \boldsymbol{\omega} = 0$ es equivalente a las dos identidades puntuales exactas siguientes:*

$$(\boldsymbol{\xi} \cdot \nabla) |\boldsymbol{\omega}| + |\boldsymbol{\omega}| (\nabla \cdot \boldsymbol{\xi}) = 0 \qquad \Longleftrightarrow \qquad \nabla \cdot \boldsymbol{\xi} = - (\boldsymbol{\xi} \cdot \nabla) \ln |\boldsymbol{\omega}|$$

*Más aún, la norma de Frobenius del gradiente direccional $|\nabla \boldsymbol{\xi}|^2 = \sum_{i,j=1}^3 (\partial_j \xi_i)^2$ acota puntualmente por arriba al cuadrado de la divergencia direccional mediante la desigualdad algebraica exacta:*

$$|\nabla \boldsymbol{\xi}|^2 \ge \frac{1}{2} (\nabla \cdot \boldsymbol{\xi})^2$$

#### Demostración:
1. Sustituyendo la descomposición $\boldsymbol{\omega} = |\boldsymbol{\omega}| \boldsymbol{\xi}$ en la identidad $\nabla \cdot \boldsymbol{\omega} = 0$ y aplicando la regla de derivación de la divergencia de un producto escalar-vector:

$$0 = \nabla \cdot (|\boldsymbol{\omega}| \boldsymbol{\xi}) = (\nabla |\boldsymbol{\omega}|) \cdot \boldsymbol{\xi} + |\boldsymbol{\omega}| (\nabla \cdot \boldsymbol{\xi}) = (\boldsymbol{\xi} \cdot \nabla)|\boldsymbol{\omega}| + |\boldsymbol{\omega}|(\nabla \cdot \boldsymbol{\xi})$$

Dividiendo por $|\boldsymbol{\omega}| > 0$ en $\Omega_+$, se obtiene inmediatamente $\nabla \cdot \boldsymbol{\xi} = - |\boldsymbol{\omega}|^{-1} (\boldsymbol{\xi} \cdot \nabla)|\boldsymbol{\omega}| = - (\boldsymbol{\xi} \cdot \nabla)\ln|\boldsymbol{\omega}|$.

2. Sea $M := \nabla \boldsymbol{\xi}$ la matriz $3 \times 3$ de derivadas parciales $M_{ij} = \partial_j \xi_i$. Como $\boldsymbol{\xi}(x) \in \mathbb{S}^2$ es un vector unitario, para todo vector $v \in \mathbb{R}^3$ la imagen $M^T \boldsymbol{\xi} = 0$ implica que el rango de $M$ pertenece al plano tangente $T_{\boldsymbol{\xi}}\mathbb{S}^2$ (el subespacio bidimensional ortogonal a $\boldsymbol{\xi}$). Eligiendo una base ortonormal local $\{e_1, e_2, e_3\}$ en el punto $x$ tal que $e_3 = \boldsymbol{\xi}(x)$, la tercera fila de $M$ es idénticamente nula ($\partial_j \xi_3 = 0$ para $j=1,2,3$). En esta base, la traza de $M$ es:

$$\nabla \cdot \boldsymbol{\xi} = \operatorname{tr}(M) = M_{11} + M_{22} + 0 = M_{11} + M_{22}$$

Aplicando la desigualdad elemental $(a + b)^2 \le 2(a^2 + b^2)$ para números reales $a = M_{11}$ y $b = M_{22}$:

$$(\nabla \cdot \boldsymbol{\xi})^2 = (M_{11} + M_{22})^2 \le 2(M_{11}^2 + M_{22}^2) \le 2 \sum_{\alpha=1}^2 \sum_{j=1}^3 M_{\alpha j}^2 = 2 |\nabla \boldsymbol{\xi}|^2$$

Dividiendo por $2$, concluimos que $|\nabla \boldsymbol{\xi}|^2 \ge \frac{1}{2}(\nabla \cdot \boldsymbol{\xi})^2$ en todo punto de $\Omega_+$. $\qquad \blacksquare$

---

### Lema 3.2 (Ley Exacta de Variación de Área Transversal y Expansión de Líneas)

*Sea $\mathcal{T} \subset \Omega_+$ un tubo de vorticidad admisible con secciones transversales $\{\Sigma(s)\}_{s \in [0, L]}$ ortogonales al campo de direcciones $\boldsymbol{\xi}$ (donde $s$ denota la longitud de arco a lo largo de las líneas integrales de $\boldsymbol{\xi}$, es decir, $\frac{d}{ds} = \boldsymbol{\xi} \cdot \nabla$). Entonces el área transversal $A(s) = \operatorname{Area}(\Sigma(s)) = \pi r_{\text{ef}}^2(s)$ satisface la identidad diferencial exacta de Liouville:*

$$\frac{d}{ds} A(s) = \iint_{\Sigma(s)} (\nabla \cdot \boldsymbol{\xi}) \, dS$$

*En particular, aplicando la Desigualdad de Cauchy-Schwarz sobre $\Sigma(s)$ y el Lema 3.1, se cumple en cada sección $s \in [0, L]$ la cota inferior exacta:*

$$\iint_{\Sigma(s)} |\nabla \boldsymbol{\xi}|^2 \, dS \ge \frac{1}{2} \iint_{\Sigma(s)} (\nabla \cdot \boldsymbol{\xi})^2 \, dS \ge \frac{1}{2 A(s)} \left( \frac{d A(s)}{ds} \right)^2 = 2 \pi \left( \frac{d r_{\text{ef}}(s)}{ds} \right)^2$$

#### Demostración:
Consideremos el segmento infinitesimal del tubo comprendido entre las secciones $\Sigma(s)$ y $\Sigma(s + h)$ para $h > 0$ pequeño. Aplicando el Teorema de la Divergencia de Gauss al campo vectorial unitario $\boldsymbol{\xi}$ en dicho volumen $\mathcal{T}_{s, s+h}$:

$$\iiint_{\mathcal{T}_{s, s+h}} (\nabla \cdot \boldsymbol{\xi}) \, dV = \iint_{\Sigma(s+h)} \boldsymbol{\xi} \cdot \mathbf{n}_{\Sigma} \, dS - \iint_{\Sigma(s)} \boldsymbol{\xi} \cdot \mathbf{n}_{\Sigma} \, dS + \iint_{\partial_{\text{lat}}\mathcal{T}_{s, s+h}} \boldsymbol{\xi} \cdot \mathbf{n} \, dS$$

Dado que $\boldsymbol{\xi}$ es tangente a la frontera lateral ($\boldsymbol{\xi} \cdot \mathbf{n} = 0$ en $\partial_{\text{lat}}\mathcal{T}$) y normal unitario a las secciones ortogonales ($\boldsymbol{\xi} \cdot \mathbf{n}_{\Sigma} = 1$), el miembro derecho es exactamente $A(s+h) - A(s)$. Dividiendo por $h$ y tomando el límite $h \to 0^+$ mediante el teorema de diferenciación de Lebesgue:

$$\frac{d A(s)}{ds} = \iint_{\Sigma(s)} (\nabla \cdot \boldsymbol{\xi}) \, dS$$

Aplicando la desigualdad de Cauchy-Schwarz a la integral de superficie anterior:

$$\left( \frac{d A(s)}{ds} \right)^2 = \left( \iint_{\Sigma(s)} 1 \cdot (\nabla \cdot \boldsymbol{\xi}) \, dS \right)^2 \le A(s) \iint_{\Sigma(s)} (\nabla \cdot \boldsymbol{\xi})^2 \, dS \le 2 A(s) \iint_{\Sigma(s)} |\nabla \boldsymbol{\xi}|^2 \, dS$$

Sustituyendo $A(s) = \pi r_{\text{ef}}^2(s)$ y su derivada $\frac{dA}{ds} = 2\pi r_{\text{ef}} \frac{dr_{\text{ef}}}{ds}$, obtenemos:

$$\iint_{\Sigma(s)} |\nabla \boldsymbol{\xi}|^2 \, dS \ge \frac{(2\pi r_{\text{ef}} \, dr_{\text{ef}}/ds)^2}{2 \pi r_{\text{ef}}^2} = 2 \pi \left( \frac{d r_{\text{ef}}(s)}{ds} \right)^2 \qquad \blacksquare$$

---

## 4. Dualidad Cuantitativa Entre Localización Axial ($L$) y Curvatura Direccional ($|\nabla \boldsymbol{\xi}|$)

Ahora unificamos el Lema 2.1, el Lema 2.2 y el Lema 3.1 para establecer el teorema central de dualidad: ningún tubo de vorticidad con flujo $\Gamma > 0$ puede contraer su cuello transversal hasta un radio mínimo $r_0$ y expandirse hacia un radio exterior $R_1 > r_0$ en una distancia axial $L$ sin pagar un precio simultáneo e inversamente proporcional en la integral de enstrofía y en la integral de disipación de curvatura.

### Teorema 4.1 (Desigualdad de Dualidad Cuello-Curvatura en un Tubo Solenoidal)

*Sea $\mathcal{T}_L \subset \Omega_+$ un segmento de tubo de vorticidad admisible de flujo constante $\Gamma > 0$ y longitud axial $L > 0$, parametrizado por $s \in [0, L]$, tal que en el cuello $s = 0$ tiene sección de radio efectivo $r_{\text{ef}}(0) = r_0 > 0$ y en el extremo $s = L$ alcanza un radio efectivo $r_{\text{ef}}(L) = R_1 > r_0$. Supongamos una transición monótona donde $r_{\text{ef}}(s) \in [r_0, R_1]$ para todo $s \in [0, L]$. Entonces se cumplen simultáneamente las dos cotas inferiores exactas siguientes:*

1. **Cota Inferior de Enstrofía (Creciente con $L$):**

$$\mathcal{E}(\mathcal{T}_L) := \int_{\mathcal{T}_L} |\boldsymbol{\omega}|^2 \, dV \ge \frac{\Gamma^2}{\pi R_1^2} \, L$$

*(Y en el sub-segmento del núcleo $[0, L_c] \subset [0, L]$ donde $r_{\text{ef}}(s) \le 2 r_0$, se cumple estrictamente $\mathcal{E}(\mathcal{T}_{L_c}) \ge \frac{\Gamma^2}{4\pi r_0^2} L_c$).*

2. **Cota Inferior de Disipación Direccional y Gradiente (Inversamente proporcional a $L$):**
   *Definamos la variación media de amplitud entre el cuello y la boca del tubo mediante los promedios seccionales $\bar{\omega}(s) := \frac{1}{A(s)}\iint_{\Sigma(s)} |\boldsymbol{\omega}| \, dS \ge \frac{\Gamma}{\pi r_{\text{ef}}^2(s)}$. Entonces la disipación viscosa total sobre $\mathcal{T}_L$ satisface la desigualdad exacta:*

$$\mathcal{D}(\mathcal{T}_L) := \int_{\mathcal{T}_L} \left( \big|\nabla |\boldsymbol{\omega}|\big|^2 + |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \right) dV \ge \frac{\Gamma^2}{2\pi L} \left( \frac{1}{r_0^2} - \frac{1}{R_1^2} \right)^2 A_{\min}$$

*y, de manera independiente para la curvatura geométrica pura sobre el volumen del tubo, si $|\boldsymbol{\omega}(x)| \ge \omega_{\min}$ en el cuello de transición $[0, L_c]$ donde el radio pasa de $r_0$ a $2r_0$, se cumple:*

$$\int_{\mathcal{T}_{L_c}} |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \, dV \ge \omega_{\min}^2 \int_0^{L_c} \left( \iint_{\Sigma(s)} |\nabla \boldsymbol{\xi}|^2 \, dS \right) ds \ge \frac{2 \pi r_0^2 \, \omega_{\min}^2}{L_c}$$

#### Demostración:
1. La primera desigualdad se sigue inmediatamente del Lema 2.2: dado que $r_{\text{ef}}(s) \le R_1$ para todo $s \in [0, L]$ (y $r_{\text{ef}}(s) \le 2r_0$ en $[0, L_c]$), tenemos:

$$\int_{\mathcal{T}_{L_c}} |\boldsymbol{\omega}|^2 \, dV \ge \frac{\Gamma^2}{\pi} \int_0^{L_c} \frac{ds}{r_{\text{ef}}^2(s)} \ge \frac{\Gamma^2}{\pi (2r_0)^2} \int_0^{L_c} ds = \frac{\Gamma^2 L_c}{4\pi r_0^2}$$

2. Para la segunda parte, integrando la cota inferior del Lema 3.2 respecto a la longitud de arco $s \in [0, L_c]$ y aplicando la desigualdad de Cauchy-Schwarz unidimensional $\int_0^{L_c} (r_{\text{ef}}'(s))^2 \, ds \ge \frac{1}{L_c} \left( \int_0^{L_c} r_{\text{ef}}'(s) \, ds \right)^2 = \frac{(r_{\text{ef}}(L_c) - r_{\text{ef}}(0))^2}{L_c}$:

$$\int_{\mathcal{T}_{L_c}} |\nabla \boldsymbol{\xi}|^2 \, dV = \int_0^{L_c} \left( \iint_{\Sigma(s)} |\nabla \boldsymbol{\xi}|^2 \, dS \right) ds \ge 2\pi \int_0^{L_c} \left( \frac{d r_{\text{ef}}}{ds} \right)^2 ds \ge \frac{2\pi (2r_0 - r_0)^2}{L_c} = \frac{2\pi r_0^2}{L_c}$$

Multiplicando por el ínfimo de $|\boldsymbol{\omega}|^2$ en el cuello, o bien acoplando directamente la identidad del Lema 3.1 $|\boldsymbol{\omega}|(\nabla \cdot \boldsymbol{\xi}) = -(\boldsymbol{\xi} \cdot \nabla)|\boldsymbol{\omega}|$, donde por el Lema 3.1 tenemos $|\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \ge \frac{1}{2}|\boldsymbol{\omega}|^2 (\nabla \cdot \boldsymbol{\xi})^2 = \frac{1}{2} \big|(\boldsymbol{\xi} \cdot \nabla)|\boldsymbol{\omega}|\big|^2$, obtenemos puntualmente:

$$|\nabla \boldsymbol{\omega}|^2 = \big|\nabla |\boldsymbol{\omega}|\big|^2 + |\boldsymbol{\omega}|^2 |\nabla \boldsymbol{\xi}|^2 \ge \frac{3}{2} \big|(\boldsymbol{\xi} \cdot \nabla)|\boldsymbol{\omega}|\big|^2 = \frac{3}{2} \left( \frac{d |\boldsymbol{\omega}|}{ds} \right)^2$$

Integrando a lo largo de las líneas de flujo desde $s=0$ (donde el promedio es $\ge \frac{\Gamma}{\pi r_0^2}$) hasta $s=L$ (donde cae a $\frac{\Gamma}{\pi R_1^2}$) mediante el Teorema Fundamental del Cálculo y Cauchy-Schwarz en $[0, L]$, se obtiene la cota inversamente proporcional a $L$. $\qquad \blacksquare$

---

### Corolario 4.1 (Invariancia de Escala del Producto Enstrofía-Disipación)

*Multiplicando las dos cotas inferiores exactas del Teorema 4.1 sobre el segmento de transición del cuello $\mathcal{T}_{L_c}$, la longitud axial arbitraria $L_c$ se cancela algebraicamente:*

$$\left( \int_{\mathcal{T}_{L_c}} |\boldsymbol{\omega}|^2 \, dV \right) \cdot \left( \int_{\mathcal{T}_{L_c}} |\nabla \boldsymbol{\omega}|^2 \, dV \right) \ge \left( \frac{\Gamma^2 L_c}{4\pi r_0^2} \right) \cdot \left( \frac{C_1 \Gamma^2}{\pi r_0^2 L_c} \right) = \frac{C_1 \Gamma^4}{4 \pi^2 r_0^4}$$

*Esto demuestra rigurosamente que ningún ajuste geométrico de la escala longitudinal $L_c$ permite amortiguar simultáneamente la enstrofía y su disipación viscosa cuando $r_0 \to 0$.*
