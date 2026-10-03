# Detailed derivation notes for `Non-Hermitian Quantum Geometry of Causal Thermal Transport`
> **GitHub math compatibility:** inline equations use `$...$`; display equations use GitHub's fenced `math` blocks. Equation numbers are written as Markdown text rather than `\\tag{}`.
## 1. What this theory is trying to do

The manuscript does **not** claim that temperature is a quantum operator or that heat conduction is a microscopic quantum-coherent process. The phrase **quantum geometry** is used in the standard mathematical sense of the projective geometry of eigenstates/eigenprojectors. In a non-Hermitian problem the natural objects are the right and left eigenstates,


```math
\mathcal L|R_n\rangle=s_n|R_n\rangle,
\qquad
\langle L_n|\mathcal L=s_n\langle L_n|.
```


The physical starting point is the Maxwell--Cattaneo model. The reason for using it instead of the Fourier equation alone is structural: the state must contain both temperature and heat flux, and the resulting first-order generator has two branches. Those two branches can coalesce at an exceptional point (EP). A one-branch Fourier diffusion equation,


```math
\partial_tT=\alpha\nabla^2T,
```

does not by itself have this two-mode EP structure.

The 1985 Mandelis paper is important historically because it already organized thermal-wave physics using Hamilton--Jacobi variables, a thermal harmonic oscillator, Schrödinger-like equations, and Ehrenfest relations. However, the present theory is deliberately different: it starts from a dissipative time-evolution generator and studies **biorthogonal eigenstate geometry**. This avoids claiming that the Mandelis thermal harmonic oscillator is literally a modern non-Hermitian quantum Hamiltonian.

---

## 2. From energy conservation and Maxwell--Cattaneo to a two-state generator

Start from


**Equation (1)**

```math
C\,\partial_tT+\nabla\cdot\mathbf q=0,
```

and


**Equation (2)**

```math
\tau\,\partial_t\mathbf q+\mathbf q=-\kappa\nabla T.
```


Here


```math
C=\rho c_p,\qquad
\alpha=\frac{\kappa}{C}.
```


Differentiate Eq. (1) with respect to time:


```math
C\,\partial_t^2T+\nabla\cdot\partial_t\mathbf q=0.
```


From Eq. (2),


```math
\partial_t\mathbf q
=
-\frac{1}{\tau}\mathbf q
-\frac{\kappa}{\tau}\nabla T.
```


Therefore


```math
C\,\partial_t^2T
-\frac{1}{\tau}\nabla\cdot\mathbf q
-\frac{\kappa}{\tau}\nabla^2T=0.
```


Use Eq. (1),


```math
\nabla\cdot\mathbf q=-C\,\partial_tT,
```

to obtain


```math
C\,\partial_t^2T
+\frac{C}{\tau}\partial_tT
-\frac{\kappa}{\tau}\nabla^2T=0.
```


Multiply by $\tau/C$:


**Equation (3)**

```math
\boxed{
\tau\partial_t^2T+\partial_tT-\alpha\nabla^2T=0.
}
```


This is a telegrapher-type thermal equation. The coefficient of the wave term gives the characteristic velocity


**Equation (4)**

```math
\boxed{
c=\sqrt{\frac{\alpha}{\tau}}.
}
```


### Longitudinal reduction

For one spatial Fourier component,


```math
T(\mathbf r,t),\mathbf q(\mathbf r,t)
\propto
e^{i\mathbf k\cdot\mathbf r},
```

the gradient becomes


```math
\nabla\rightarrow i\mathbf k.
```


Only


```math
q_L=\hat{\mathbf k}\cdot\mathbf q
```

enters the energy equation. The two transverse components satisfy


```math
\partial_t q_T=-\frac{1}{\tau}q_T
```

and therefore decouple. The interesting dynamics is exactly two-dimensional.

Define


**Equation (5)**

```math
\varphi=\frac{q_L}{Cc}.
```

Because


```math
[Cc]=\frac{\mathrm J}{\mathrm m^3\,K}\frac{\mathrm m}{\mathrm s}
=\frac{\mathrm W}{\mathrm m^2\,K},
```

$\varphi$ has units of kelvin, just like $T$.

Equation (1) becomes


```math
\partial_tT=-ick\,\varphi.
```


Equation (2) gives


```math
\partial_t\varphi
=
-ick\,T-\frac{1}{\tau}\varphi.
```


Hence


**Equation (6)**

```math
\boxed{
\partial_t
\begin{pmatrix}
T\\
\varphi
\end{pmatrix}
=
\begin{pmatrix}
0&-ick\\
-ick&-\gamma
\end{pmatrix}
\begin{pmatrix}
T\\
\varphi
\end{pmatrix},
\qquad
\gamma=\frac1\tau.
}
```


The matrix is complex symmetric,


```math
\mathcal L^T=\mathcal L,
```

but it is not Hermitian because


```math
\mathcal L^\dagger\neq\mathcal L.
```


---

## 3. Exact spectrum and the thermal exceptional point

Write


```math
\mathcal L
=
-\frac{\gamma}{2}I+\mathcal H
```

with


**Equation (7)**

```math
\mathcal H
=
\begin{pmatrix}
\gamma/2&-ick\\
-ick&-\gamma/2
\end{pmatrix}.
```


This can be expressed as


**Equation (8)**

```math
\mathcal H
=
\frac{\gamma}{2}\sigma_z
-ick\,\sigma_x.
```


Square it:


```math
\mathcal H^2
=
\left[
\left(\frac{\gamma}{2}\right)^2-c^2k^2
\right]I.
```


Define


**Equation (9)**

```math
\Delta(k)
=
\sqrt{
\frac{\gamma^2}{4}-c^2k^2
}.
```


Then the two eigenvalues are


**Equation (10)**

```math
\boxed{
s_\pm
=
-\frac{\gamma}{2}\pm\Delta.
}
```


### Regime 1: overdamped

If


```math
c^2k^2<\frac{\gamma^2}{4},
```

then $\Delta$ is real and both $s_\pm$ are real and negative.

### Regime 2: propagating but damped

If


```math
c^2k^2>\frac{\gamma^2}{4},
```

write


```math
\Delta=i\Omega_k,
```

where


```math
\Omega_k
=
\sqrt{
c^2k^2-\frac{\gamma^2}{4}
}.
```


Then


```math
s_\pm
=
-\frac{\gamma}{2}\pm i\Omega_k.
```


### Exceptional point

Set $\Delta=0$:


```math
k_c=\frac{\gamma}{2c}.
```


Using


```math
c=\sqrt{\frac{\alpha}{\tau}},
\qquad
\gamma=\frac1\tau,
```

one obtains


**Equation (11)**

```math
\boxed{
k_c
=
\frac{1}{2c\tau}
=
\frac{1}{2\sqrt{\alpha\tau}}.
}
```


At the critical point,


```math
\mathcal H_c^2=0
```

but


```math
\mathcal H_c\neq0.
```

Therefore $\mathcal H_c$ is nonzero and nilpotent. A $2\times2$ matrix with this property has a repeated eigenvalue but only one independent eigenvector: this is a second-order EP.

This is stronger than merely saying "the discriminant is zero." The nilpotency condition proves defectiveness directly.

---

## 4. Why spectral projectors are the cleanest object

The eigenvectors can be normalized in many gauges. Near an EP any explicit normalization tends to become awkward. Instead use the projectors.

Because


```math
\mathcal H^2=\Delta^2 I,
```

the projectors are


**Equation (12)**

```math
\boxed{
P_\pm
=
\frac12
\left(
I\pm\frac{\mathcal H}{\Delta}
\right).
}
```


Check:


```math
P_\pm^2=P_\pm,
\qquad
P_+P_-=0,
\qquad
P_++P_-=I.
```


The factor $1/\Delta$ immediately signals a singular eigenbasis as $\Delta\to0$. The original operator remains finite; what becomes singular is the decomposition into individual modes.

This distinction is physically important:
- the evolution equation itself is regular at the EP;
- the isolated-band description is singular there.

---

## 5. Biorthogonal quantum geometric tensor

Take right and left eigenvectors satisfying


```math
\mathcal L|R_n\rangle=s_n|R_n\rangle,
```



```math
\langle L_n|\mathcal L=s_n\langle L_n|,
```

and


```math
\langle L_m|R_n\rangle=\delta_{mn}.
```


For a parameter $\lambda^\mu$, define


**Equation (13)**

```math
\boxed{
Q_{\mu\nu}^{(n)}
=
\langle\partial_\mu L_n|
(1-P_n)
|\partial_\nu R_n\rangle.
}
```


Using


```math
P_n=|R_n\rangle\langle L_n|,
```

one can show


**Equation (14)**

```math
\boxed{
Q_{\mu\nu}^{(n)}
=
\operatorname{Tr}
\left[
P_n(\partial_\mu P_n)(\partial_\nu P_n)
\right].
}
```


The projector expression is useful for three reasons:

1. It is invariant under the eigenvector gauge
   

```math
|R_n\rangle\rightarrow e^{f_n}|R_n\rangle,
   \qquad
   \langle L_n|\rightarrow e^{-f_n}\langle L_n|.
```


2. It does not require choosing a singular normalization close to the EP.

3. Under a **parameter-independent** similarity transformation,
   

```math
P\rightarrow S^{-1}PS,
```

   the trace in Eq. (14) is unchanged.

The third point is why it is safe to use the scaled flux $\varphi=q/(Cc)$ when studying the $k$-geometry at fixed material parameters.

### Important caveat for material-parameter geometry

If one varies $\alpha$ or $\tau$, then $c=\sqrt{\alpha/\tau}$ changes, so the scaling $q/(Cc)$ itself becomes parameter dependent. A parameter-dependent similarity transformation contributes additional connection terms. Therefore the closed-form metric derived below is presented primarily as a **momentum-space metric at fixed material parameters**. A later extension to $\alpha$- or $\tau$-geometry should fix a parameter-independent physical state-space metric or reference scaling before comparing different materials.

This caveat is important and should remain in the paper.

---

## 6. Two-state formula for the QGT

Write


```math
\mathcal H=\mathbf d\cdot\boldsymbol\sigma,
```

where


```math
\mathbf d=(-ick,0,\gamma/2).
```


Since


```math
\Delta^2=\mathbf d\cdot\mathbf d,
```

define


```math
\hat{\mathbf d}=\frac{\mathbf d}{\Delta}.
```


Then


```math
P_\pm=\frac12(I\pm\hat{\mathbf d}\cdot\boldsymbol\sigma).
```


Differentiate:


```math
\partial_\mu P_\pm
=
\pm\frac12
(\partial_\mu\hat{\mathbf d})\cdot\boldsymbol\sigma.
```


Use


```math
(\mathbf a\cdot\boldsymbol\sigma)
(\mathbf b\cdot\boldsymbol\sigma)
=
(\mathbf a\cdot\mathbf b)I
+i(\mathbf a\times\mathbf b)\cdot\boldsymbol\sigma.
```


Substituting into the projector definition gives


**Equation (15)**

```math
\boxed{
Q_{\mu\nu}^{(\pm)}
=
\frac14
\left[
\partial_\mu\hat{\mathbf d}\cdot
\partial_\nu\hat{\mathbf d}
\pm i\hat{\mathbf d}\cdot
(
\partial_\mu\hat{\mathbf d}
\times
\partial_\nu\hat{\mathbf d}
)
\right].
}
```


For the Maxwell--Cattaneo model, $\hat{\mathbf d}$ always lies in the $x$-$z$ plane. Therefore


```math
\hat{\mathbf d}\cdot
(
\partial_\mu\hat{\mathbf d}
\times
\partial_\nu\hat{\mathbf d}
)=0.
```


So the minimal model has:
- a nontrivial metric sector;
- zero Berry curvature.

This is a useful result rather than a weakness. It prevents the paper from making an unjustified claim about Berry-curvature-induced heat transport in a model that cannot support it.

---

## 7. Exact derivation of $Q_{kk}$

For fixed $c$ and $\gamma$,


```math
\hat d_x=-\frac{ick}{\Delta},
\qquad
\hat d_z=\frac{\gamma}{2\Delta}.
```


Since


```math
\Delta^2=\frac{\gamma^2}{4}-c^2k^2,
```



```math
\partial_k\Delta
=
-\frac{c^2k}{\Delta}.
```


Now


```math
\partial_k\hat d_x
=
-\frac{ic}{\Delta}
-\frac{ic^3k^2}{\Delta^3},
```

and


```math
\partial_k\hat d_z
=
\frac{\gamma c^2k}{2\Delta^3}.
```


Because the curvature term is zero,


```math
Q_{kk}
=
\frac14
\left[
(\partial_k\hat d_x)^2
+
(\partial_k\hat d_z)^2
\right].
```


After simplification,


**Equation (16)**

```math
\boxed{
Q_{kk}^{(\pm)}
=
-\frac{c^2\gamma^2}
{(\gamma^2-4c^2k^2)^2}.
}
```


Use


```math
c^2=\frac{\alpha}{\tau},
\qquad
\gamma=\frac1\tau,
```

to obtain


**Equation (17)**

```math
\boxed{
Q_{kk}^{(\pm)}
=
-\frac{\alpha\tau}
{(1-4\alpha\tau k^2)^2}.
}
```


The two branches have the same diagonal metric because changing $+\hat{\mathbf d}$ to $-\hat{\mathbf d}$ changes both derivatives by a minus sign, which cancels in the quadratic metric term.

### Why the metric is negative

In a Hermitian problem the quantum metric is positive semidefinite. The biorthogonal non-Hermitian tensor is different: the left-right pairing is not a positive Hilbert-space norm, so $Q_{kk}$ can be negative or complex. The physically robust statement is the singular projective susceptibility, not the sign interpreted as a variance.

If a later experimental section needs a positive quantity, one can define a separate positive projector susceptibility such as a Hilbert--Schmidt norm of $\partial_kP$. That should be introduced as a **different** object, not silently called the biorthogonal metric.

---

## 8. Universal exceptional-point scaling

From


```math
k_c=\frac{1}{2\sqrt{\alpha\tau}},
```

we have


```math
4\alpha\tau k_c^2=1.
```


Near the positive EP let


```math
k=k_c+\delta k.
```


Then


```math
1-4\alpha\tau k^2
=
1-\frac{k^2}{k_c^2}.
```


Expand:


```math
\frac{k^2}{k_c^2}
=
1+\frac{2\delta k}{k_c}
+\mathcal O(\delta k^2).
```


Therefore


```math
1-4\alpha\tau k^2
=
-\frac{2\delta k}{k_c}
+\mathcal O(\delta k^2).
```


Insert into Eq. (17):


```math
Q_{kk}
\sim
-\alpha\tau
\frac{k_c^2}{4\delta k^2}.
```


But


```math
\alpha\tau k_c^2=\frac14.
```


Hence


**Equation (18)**

```math
\boxed{
Q_{kk}
\sim
-\frac{1}{16(k-k_c)^2}.
}
```


This is an especially attractive result because the leading prefactor is independent of $\alpha$ and $\tau$. The EP leaves a universal second-order pole in momentum-space eigenstate geometry.

---

## 9. Projective coordinate: the shortest route to the same result

Solve the first row of


```math
\mathcal L
\begin{pmatrix}
T\\
\varphi
\end{pmatrix}
=
s
\begin{pmatrix}
T\\
\varphi
\end{pmatrix}.
```


It gives


```math
-sT-ick\varphi=0.
```


Therefore


**Equation (19)**

```math
\boxed{
\zeta\equiv\frac{\varphi}{T}
=
\frac{is}{ck}.
}
```


Use


```math
|R\rangle=
\begin{pmatrix}
1\\
\zeta
\end{pmatrix}.
```


Because the matrix is complex symmetric, the left row can be chosen proportional to the transpose. Biorthogonal normalization gives


**Equation (20)**

```math
\langle L|
=
\frac{(1,\zeta)}{1+\zeta^2}.
```


Substituting this parameterization into the QGT gives


**Equation (21)**

```math
\boxed{
Q_{kk}
=
\frac{(\partial_k\zeta)^2}{(1+\zeta^2)^2}.
}
```


At the EP,


```math
s_{\rm EP}=-\frac{\gamma}{2},
\qquad
k_c=\frac{\gamma}{2c}.
```


Thus


```math
\zeta_{\rm EP}
=
\frac{i(-\gamma/2)}
{c(\gamma/2c)}
=-i.
```


Therefore


**Equation (22)**

```math
1+\zeta_{\rm EP}^2
=
1+(-i)^2
=0.
```


This is the explicit **self-orthogonality** condition. It explains why the metric diverges more strongly than one would guess merely from the closing eigenvalue gap: the eigenvector normalization also becomes singular.

---

## 10. Direct connection to thermal impedance

Since


```math
q_L=Cc\,\varphi,
```

the modal temperature--flux ratio is


```math
Z_n(k)
\equiv
\frac{q_L}{T}
=
Cc\,\zeta_n.
```


Using Eq. (19),


**Equation (23)**

```math
\boxed{
Z_n(k)
=
\frac{iCs_n(k)}{k}.
}
```


Therefore


**Equation (24)**

```math
\boxed{
Q_{kk}^{(n)}
=
\frac{
[\partial_k(Z_n/Cc)]^2
}{
[1+(Z_n/Cc)^2]^2
}.
}
```


This is one of the most useful equations in the manuscript.

It says that the non-Hermitian eigenstate geometry is not merely an abstract property of eigenvectors. It measures how rapidly the **temperature--flux composition of a mode** changes with wave number.

Possible experimental route:
1. Measure complex $T(k,\omega)$.
2. Infer or independently measure $q(k,\omega)$.
3. Form the complex ratio $Z=q/T$.
4. Compare its variation with the predicted geometric singularity.

The paper should be careful not to promise that $q$ is always directly measured; in many experiments it may be reconstructed from a constitutive model or boundary calibration.

---

## 11. Biorthogonal Ehrenfest theorem

The 1985 Mandelis theory used expectation values and an Ehrenfest construction, but its derivation invoked a Hermitian Hamiltonian assumption. The natural non-Hermitian replacement is to evolve right and left states independently:


**Equation (25)**

```math
\partial_t|\Psi^R\rangle
=
\hat{\mathcal L}|\Psi^R\rangle,
```



**Equation (26)**

```math
\partial_t\langle\Psi^L|
=
-\langle\Psi^L|\hat{\mathcal L}.
```


Then


```math
\frac{d}{dt}
\langle\Psi^L|\Psi^R\rangle=0.
```


Define


**Equation (27)**

```math
\langle A\rangle_B
=
\frac{
\langle\Psi^L|\hat A|\Psi^R\rangle
}{
\langle\Psi^L|\Psi^R\rangle
}.
```


Differentiate the numerator:


```math
\frac{d}{dt}
\langle\Psi^L|\hat A|\Psi^R\rangle
=
-\langle\Psi^L|\mathcal L A|\Psi^R\rangle
+
\langle\Psi^L|\partial_tA|\Psi^R\rangle
+
\langle\Psi^L|A\mathcal L|\Psi^R\rangle.
```


Hence


**Equation (28)**

```math
\boxed{
\frac{d}{dt}\langle A\rangle_B
=
\left\langle
\partial_tA+[A,\mathcal L]
\right\rangle_B.
}
```


This is the non-Hermitian biorthogonal Ehrenfest identity used in the manuscript.

### Position operator

In momentum space,


```math
X=i\partial_k.
```


For a matrix $\mathcal L(k)$,


```math
[X,\mathcal L]
=
i\partial_k\mathcal L.
```


Therefore


**Equation (29)**

```math
\boxed{
\dot X_B
=
i\langle\partial_k\mathcal L\rangle_B.
}
```


For one isolated eigenmode, differentiate


```math
\mathcal L|R_n\rangle=s_n|R_n\rangle
```

and project with $\langle L_n|$. One obtains the biorthogonal Hellmann--Feynman relation


**Equation (30)**

```math
\boxed{
\langle L_n|
\partial_k\mathcal L
|R_n\rangle
=
\partial_ks_n.
}
```


Thus


**Equation (31)**

```math
\boxed{
\dot X_B=i\partial_ks_n.
}
```


Write


```math
s_n=\sigma_n+i\Omega_n.
```

Then


```math
i\partial_ks_n
=
-\partial_k\Omega_n
+
i\partial_k\sigma_n.
```


Therefore


**Equation (32)**

```math
\Re\dot X_B
=
-\partial_k\Omega_n,
\qquad
\Im\dot X_B
=
\partial_k\sigma_n.
```


With the convention $e^{ikx+s t}$, the phase is $kx+\Omega t$, so stationary phase indeed gives


```math
v_g=-\partial_k\Omega.
```


### Important interpretation

Do **not** state that $X_B$ is automatically the experimentally measured heat centroid. It is a complex biorthogonal centroid. A physical temperature centroid, energy centroid, or detector-weighted centroid requires a specified measurement functional.

The safe statement is:
- Eq. (28) is an exact non-Hermitian Ehrenfest identity.
- Eq. (31) is the corresponding single-band transport relation.
- The real part reproduces the phase/group-transport term.
- Observable-specific centroids need a measurement model.

This is much more defensible than claiming a universal "quantum-geometric heat velocity."

---

## 12. Why the minimal model has no Berry curvature

The two-state vector is


```math
\mathbf d=(-ick,0,\gamma/2).
```


All states lie in one complex plane of the Bloch-vector representation. Therefore for any two parameters $\lambda^\mu,\lambda^\nu$,


```math
\hat{\mathbf d}\cdot
(
\partial_\mu\hat{\mathbf d}
\times
\partial_\nu\hat{\mathbf d}
)=0
```

as long as the parameter variation does not generate a $d_y$ component.

Consequences:
- The minimal reciprocal Maxwell--Cattaneo model has a singular metric.
- It does **not** have a Berry-curvature-induced anomalous velocity.
- To obtain curvature-driven thermal pumping, the model must be enlarged.

Possible theoretical extensions include:


```math
\mathcal L_{\rm gen}
=
d_0I+d_x\sigma_x+d_y\sigma_y+d_z\sigma_z
```

with $d_y\neq0$, or a larger multicomponent state vector.

Physical mechanisms that could generate this extra structure include nonreciprocal couplings, multiple coupled thermal channels, and spatiotemporal modulation. These should be modeled explicitly before claiming a nonzero curvature effect.

---

## 13. Fourier limit

Take


```math
\tau\to0
```

with $\alpha$ fixed.

Recall


```math
\gamma=\frac1\tau,
\qquad
c^2=\frac{\alpha}{\tau}=\alpha\gamma.
```


Then


```math
\Delta
=
\frac{\gamma}{2}
\sqrt{
1-\frac{4\alpha k^2}{\gamma}
}.
```


For large $\gamma$,


```math
\sqrt{1-\epsilon}
=
1-\frac{\epsilon}{2}
+\mathcal O(\epsilon^2).
```


Hence


```math
\Delta
=
\frac{\gamma}{2}
-\alpha k^2
+\mathcal O(\tau).
```


Therefore


**Equation (33)**

```math
s_+
=
-\alpha k^2+\mathcal O(\tau),
```

whereas


**Equation (34)**

```math
s_-
=
-\frac1\tau+\alpha k^2+\mathcal O(\tau).
```


The $s_-$ mode disappears on the fast relaxation time $\tau$, leaving


**Equation (35)**

```math
\boxed{
\partial_tT=\alpha\nabla^2T.
}
```


The geometric tensor becomes


```math
Q_{kk}
=
-\frac{\alpha\tau}
{(1-4\alpha\tau k^2)^2}
=
-\alpha\tau+\mathcal O(\tau^2),
```

so


**Equation (36)**

```math
\boxed{
Q_{kk}\to0.
}
```


Interpretation: the internal temperature--flux eigenvector geometry disappears when the flux ceases to be an independent dynamical degree of freedom.

---

## 14. Relation to Mandelis (1985)

The source paper by Andreas Mandelis starts from the Fourier heat equation under harmonic excitation, obtains a Fourier--Helmholtz spatial equation, constructs a Lagrangian and Hamiltonian, identifies temperature and heat-flux-related quantities as canonical variables, and maps the problem through a canonical transformation to a thermal harmonic oscillator. It then introduces a Schrödinger-like formalism and uses expectation values/Ehrenfest relations to recover macroscopic thermal-wave quantities.

The present theory should describe that relationship carefully:

### What is shared

Both theories emphasize that heat transport has more structure than a scalar decay law:
- temperature and flux can be treated as coupled dynamical variables;
- spectral modes contain both propagation and attenuation information;
- expectation-value/transport identities can be constructed.

### What is different

Mandelis:


```math
\text{Fourier harmonic field}
\rightarrow
\text{Hamilton--Jacobi canonical transformation}
\rightarrow
\text{thermal harmonic oscillator}.
```


Present theory:


```math
\text{Maxwell--Cattaneo state space}
\rightarrow
\text{non-Hermitian generator}
\rightarrow
\text{left/right eigenprojectors}
\rightarrow
\text{biorthogonal geometry}.
```


Therefore the manuscript should **not** say that Mandelis is simply a Hermitian limit of the present model. The safer statement is:

> The two descriptions meet at the macroscopic Fourier equation in the $\tau\to0$ limit, but the associated geometric objects are different.

This distinction is one of the most important conceptual corrections relative to an overly aggressive initial narrative.

---

## 15. The main theoretical claims that are already rigorous

The current derivation supports the following claims without requiring extra modeling:

1. **Causal thermal transport is a non-Hermitian two-state problem in the longitudinal sector.**

2. **The Maxwell--Cattaneo crossover occurs at a second-order EP**
   

```math
k_c=\frac{1}{2\sqrt{\alpha\tau}}.
```


3. **The biorthogonal momentum-space QGT is exactly**
   

```math
Q_{kk}
   =
   -\frac{\alpha\tau}
   {(1-4\alpha\tau k^2)^2}.
```


4. **The EP singularity is universal**
   

```math
Q_{kk}
   \sim
   -\frac{1}{16(k-k_c)^2}.
```


5. **The divergence is caused by self-orthogonality**
   

```math
1+\zeta_{\rm EP}^2=0.
```


6. **The QGT has a direct modal observable representation**
   

```math
Q_{kk}
   =
   \frac{
   [\partial_k(Z/Cc)]^2
   }{
   [1+(Z/Cc)^2]^2
   }.
```


7. **A non-Hermitian Ehrenfest identity holds**
   

```math
\frac{d}{dt}\langle A\rangle_B
   =
   \langle\partial_tA+[A,\mathcal L]\rangle_B.
```


8. **The strict Fourier limit eliminates both the fast flux mode and this two-state momentum-space geometry.**

These are the safest core results for a first PRB theory manuscript.

---

## 16. Claims that should NOT yet be made without extra derivation

Do not yet claim:

- that the minimal reciprocal model has a nonzero Berry curvature;
- that quantum geometry creates an additional heat current in this model;
- that the biorthogonal centroid is automatically the measured thermal centroid;
- that $Q_{kk}$ is a positive statistical metric;
- that the Mandelis thermal harmonic oscillator is literally the Hermitian limit of the present generator;
- that temperature itself has been quantized.

These points can become later extensions, but the present analytical theory does not establish them.

---

## 17. Best next calculations for the paper

### A. Build a positive experimental susceptibility

The biorthogonal QGT is indefinite. For comparison with measured sensitivities, derive a positive gauge-invariant projector susceptibility, for example from


```math
\operatorname{Tr}
[(\partial_kP)^\dagger(\partial_kP)].
```

Keep it clearly distinct from the biorthogonal QGT.

### B. Add a measurement model

Choose a concrete observable such as:


```math
Z(k,\omega)=q/T,
```

surface temperature response, transmitted thermal amplitude, or phase lag. Derive its sensitivity to $k,\tau,\alpha$ and compare its divergence with the geometric prediction.

### C. Introduce a genuinely noncoplanar thermal generator

To study Berry curvature and geometric pumping, construct a physically justified model with a third generator component. A nonreciprocal two-channel thermal network is probably the cleanest starting point.

### D. Treat inhomogeneity

For slowly varying $\alpha(x)$ and $\tau(x)$, derive an adiabatic local-mode theory. This is the natural setting in which a geometric connection could enter a transport equation.

### E. Test the EP regularization

Any real experiment has finite bandwidth, finite sample size, noise, and constitutive uncertainty. These effects should regularize the mathematical divergence. That regularization itself can become a useful measurable prediction.

---

## 18. Suggested main-text organization

For a full PRB manuscript, a strong order is:

1. **Introduction**
   - historical thermal-wave Hamilton--Jacobi viewpoint;
   - modern non-Hermitian state-space viewpoint;
   - unresolved link between EPs and eigenstate geometry.

2. **Causal thermal generator**
   - Eqs. (1)--(11).

3. **Biorthogonal quantum geometry**
   - projectors;
   - QGT;
   - exact $Q_{kk}$.

4. **Universal EP singularity**
   - Eq. (18);
   - self-orthogonality;
   - thermal impedance relation.

5. **Biorthogonal transport identities**
   - Ehrenfest theorem;
   - group-transport interpretation.

6. **Fourier limit and relation to Mandelis**
   - clarify what is recovered and what is not.

7. **Numerical/experimental consequences**
   - regularized divergence;
   - impedance or temperature/flux susceptibility.

8. **Discussion and outlook**
   - nonreciprocity, curvature, pumping, inhomogeneity.

---

## 19. One-sentence conceptual summary

The strongest defensible message of the current theory is:



```math
\boxed{
\text{The causal temperature--flux state acquires a singular biorthogonal
eigenprojector geometry at the diffusive--propagating exceptional point,
and that geometry is encoded directly in the modal thermal impedance.}
}
```


That is already substantially stronger and more precise than simply saying that "heat transport is non-Hermitian."