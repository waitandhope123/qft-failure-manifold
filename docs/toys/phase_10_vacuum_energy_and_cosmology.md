# Phase 10 — Vacuum Energy & Cosmological Implications

**Toys 086–090**

---

## Toy 086 — Casimir-Induced Vacuum Energy Sign Ambiguity

This toy models a simple Casimir-like vacuum energy in a one-dimensional compact space of length $L$, using boundary conditions as the only physical distinction. The quantity of interest is the vacuum energy density as a function of $L$, evaluated for two choices of boundary condition that act as proxies for different quantum field configurations. In this minimal setup the energies scale inversely with size, schematically as $E(L)\propto 1/L$, but with a sign and prefactor determined entirely by the boundary condition.

The toy exists to illustrate that vacuum energy contributions are not generically positive or negative, even in extremely simple settings. By holding the geometry fixed and changing only the boundary conditions, the model exposes a failure mode of intuition in which “vacuum energy” is implicitly assumed to have a definite sign. This is not a physical prediction about real Casimir systems, but a stress test of reasoning: it demonstrates that sign is contingent on global structure and cannot be treated as an invariant diagnostic.

The JSON results should be read as a table over sampled compact lengths, where `energy_periodic` and `energy_antiperiodic` give the two proxy energies and `sign_flip` records whether they differ in sign. The important trend is that the sign difference persists across all sampled $L$, while the magnitudes decrease smoothly like $1/L$; this persistence is the conceptual signal being tested. What should not be over-interpreted are the numerical coefficients or the exact scaling, which are deliberately simplistic. Conceptually, the JSON encodes how the same inverse-length dependence, when paired with different boundary conditions in the defining equations, leads to opposite-sign vacuum energies without invoking any change in local physics.

---

## Toy 087 — Metastable Positive Vacuum Energy Proxy

This toy samples a one-dimensional scalar field $\phi$ with a deliberately tilted double-well potential to illustrate how vacuum energy depends on field location. The quantity of interest is the local vacuum energy density, identified directly with the scalar potential value $V(\phi)=(\phi^2-1)^2+0.2\,\phi$. By scanning $\phi$ over a fixed range and recording $V(\phi)$, the toy constructs a simple proxy for how different field configurations can correspond to positive or negative vacuum energy without invoking dynamical gravity.

The toy exists to expose a common conceptual pitfall: equating positive vacuum energy with stability. The added linear tilt ensures that one local minimum has positive energy while a deeper global minimum lies elsewhere at lower (here negative) energy. This setup is a stress test for intuition rather than a physical prediction, demonstrating that metastability and vacuum sign are logically distinct, and that identifying “de Sitter–like” behavior from $V>0$ alone is an unreliable diagnostic of long-term behavior.

The JSON output should be read as a sampled map from field value to vacuum energy, with each entry reporting a single $\phi$ and its corresponding $V(\phi)$. What matters are the relative trends: the presence of a shallow local minimum at positive energy, the existence of a deeper global minimum with lower energy, and the sign and magnitude differences between them. The absolute numbers, the absence of curvature invariants, and the label “metastable” should not be over-interpreted as statements about real spacetime dynamics; they merely encode how the sampled values of $V(\phi)$ realize the qualitative features implied by the potential and connect the JSON values back to that functional form.

---

## Toy 088 — Dimensional Uplift vs Observable Vacuum Energy

This toy explores how a vacuum energy defined in a higher-dimensional theory can translate into an effective four-dimensional quantity after dimensional reduction. The physical setup is intentionally schematic: a higher-dimensional vacuum energy density $\Lambda_D$ is mapped to an effective four-dimensional value using the simple relation $E_{4D}=\Lambda_D(4/D)$, where $D$ is the total spacetime dimension. The quantity of interest is not geometry or dynamics, but the reported effective vacuum energy that a four-dimensional observer would infer from a higher-dimensional input.

The toy exists to illustrate a limitation in intuition about dimensional uplift and reduction. In many discussions, positive vacuum energy in higher dimensions is implicitly assumed to imply positive, well-defined dark energy in four dimensions. This construction exposes the ambiguity in that assumption by showing that the same positive $\Lambda_D$ can correspond to markedly different effective energies depending on $D$, without any change in sign or “stability” in the higher-dimensional input. It is framed as a stress test of dimensional reasoning rather than a model of real compactification physics.

The JSON results should be interpreted as a grid of mappings from $(\Lambda_D, D)$ to an effective four-dimensional energy. The key trend to notice is the systematic dilution of $E_{4D}$ as the dimension increases: for fixed $\Lambda_D$, the effective energy decreases monotonically with $D$. The absolute magnitudes, the linear scaling, and the absence of curvature data should not be over-interpreted as physical predictions; they simply encode the algebraic rule used by the toy. Conceptually, the listed values are direct numerical realizations of the mapping equation and are meant to highlight how dimensional bookkeeping alone can reshape vacuum energy assignments.

---

## Toy 089 — de Sitter Construction Control Diagnostics

This toy scans a simple effective-field-theory potential for a single positive modulus $L$ to see when a de Sitter–like positive vacuum energy can appear and under what conditions it looks trustworthy. The physical setup is deliberately schematic: Casimir-like, uplift, stabilizing, and counterterm contributions are combined into a single proxy potential $$V(L)=\mathrm{sgn}(bc)\,A/L^4+U_0/L^p-S_0/L^q+(c_0+c_1/L^2).$$ The quantity of interest is the value of $V$ at a candidate extremum $L^\*$, interpreted only as a diagnostic for positive vacuum energy rather than a spacetime solution.

The toy exists to stress-test the gap between “existence” and “control” in de Sitter constructions. It illustrates that positive $V(L^\*)$ can be engineered easily across parameter space, yet typically relies on large cancellations, regulator-sensitive counterterms, or regions where curvature approaches the EFT cutoff. Control is probed using a crude curvature proxy $H^2=V/3$ together with stability and tuning diagnostics, exposing a failure mode where positivity alone is misleading and does not imply a reliable semiclassical regime.

The JSON output should be read as a grid audit over parameter choices, with each entry recording whether a candidate extremum exists, whether it is positive, stable, and controlled. The most important trends are in the summary fractions: while a majority of parameter sets admit positive candidates and many are locally stable, essentially none satisfy positivity, stability, and control simultaneously, and the “good” fraction vanishes in this scan. Individual values such as barrier heights or lifetime proxies are heuristic and should not be over-interpreted; what matters is the pattern that control measures like $\epsilon=H/\Lambda_{\mathrm{uv}}$ and the tuning proxy deteriorate precisely where $V(L^\*)>0$. The numbers simply instantiate the algebraic definitions used in the diagnostics and conceptually tie back to how $V(L)$ feeds into curvature and EFT validity checks.

---

## Toy 090 — EFT Positivity Cone and Breakdown Proxy

This toy scans a simple forward $2\to2$ scattering effective-field-theory expansion and tracks how its low-energy coefficients control both the apparent amplitude and the energy at which the expansion stops being self-consistent. The setup is a deterministic polynomial proxy for the forward amplitude, $A(s,0)=a_2 s^2+a_3 s^3+a_4 s^4$ with $s=E^2$, where the “quantity of interest” is not a cross section but a consistency map: which coefficient triples $(a_2,a_3,a_4)$ look admissible and at what characteristic scale the next terms become comparable to the leading one.

The toy exists to stress-test a common ambiguity in EFT reasoning: “small corrections at low energy” does not guarantee the coefficient choice is compatible with a unitary, analytic, causal UV completion. It demonstrates this by imposing a positivity/analyticity proxy that carves out a cone in coefficient space—$a_2\ge 0$, $a_4\ge 0$, and the curvature-like bound $a_3^2\le \kappa\,a_2 a_4$ (with $\kappa$ controlling how tight the cone is)—so that seemingly innocuous values can fail a UV-completability check even when an EFT expansion parameter is small. The point is a limitation/stress test: the constraints are an illustrative surrogate for dispersion-relation positivity, not a physical prediction about any specific UV theory.

To interpret the JSON, start with the global `observables.summary` counts/fractions, which report how often the scan passes `positivity_ok`, how often an EFT breakdown scale `E_EFT_breakdown` is defined within `E_max`, and how often the additional unitarity proxy at that scale is satisfied. Each entry in `sample_points` gives the chosen coefficients (`coordinates`) and a breakdown estimate defined as the smallest $E$ where either $|a_3|E/a_2>r_{\max}$ or $|a_4|E^2/a_2>r_{\max}$, so smaller `E_EFT_breakdown` means “the series becomes questionable earlier” for that coefficient choice, while `null` typically signals the proxy is undefined (e.g., $a_2\le 0$) or no threshold crossing occurs before `E_max`. Treat `amplitude_abs_at_EEFT` and `unitarity_proxy_ok_at_EEFT` only as diagnostics of this toy’s internal bookkeeping (they depend on the same polynomial $A(s,0)$ and the chosen thresholds), and do not over-interpret the absolute magnitudes as real scattering amplitudes; what matters are patterns like “positivity fails despite low-energy control,” “positivity passes but breakdown occurs early,” or “positivity passes yet the unitarity proxy fails at the inferred breakdown scale,” which conceptually link the scanned JSON values back to the two anchors: the cone inequality for UV-admissibility and the ratio-based definition of $E_{\mathrm{EFT}}$.

---

