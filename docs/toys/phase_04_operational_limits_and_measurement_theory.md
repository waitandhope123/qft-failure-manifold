# Phase 4 — Operational Limits & Measurement Theory

**Toys 031–040**

---

## Toy 031 — Finite Detector Resolution and Operational Lorentz Symmetry Breaking

This toy illustrates how a finite-resolution detector coupled to a free scalar field in 1+1-dimensional Minkowski spacetime produces measurements that depend on the detector’s inertial frame. The physical setup is intentionally minimal: a detector with Gaussian smearing of width $\sigma$ and internal energy gap $\Omega$ is considered in several boosted frames labeled by rapidity $\eta$. The quantity of interest is a proxy for the detector’s response, modeled as a simple function of the boost through the Lorentz factor $\gamma=\cosh\eta$, leading to a response of the form $R(\eta)=\exp(-\Omega\,\sigma\,\gamma)$.

The toy exists to expose a conceptual pressure point rather than to make a physical prediction. While the underlying quantum field theory is exactly Lorentz invariant, any real measurement is performed by an object with finite spatial and temporal resolution, and this operational fact introduces frame dependence. The toy functions as a stress test for the assumption that symmetry of the equations implies symmetry of observations, demonstrating that the limit $\sigma\to 0$ is required before detector responses become invariant and that finite $\sigma$ represents an intrinsic limitation rather than a violation of the theory itself.

The JSON output should be read as a collection of sample points, each corresponding to a different boost rapidity. For each $\eta$, the `ideal_lorentz_invariant_response` remains fixed at unity, representing the pointlike, invariant limit, while the `detector_response_proxy` decreases monotonically with increasing $\gamma$, reflecting stronger suppression in more highly boosted frames. The absolute numerical values are not meaningful predictions and should not be over-interpreted; what matters are the trends and relative changes, which conceptually track how the exponential dependence on $\Omega\sigma\gamma$ translates finite detector resolution into operational symmetry breaking.

---

## Toy 032 — Quantum Anomaly from Non-Commuting Limits

This toy demonstrates how a symmetry that is exact at the level of a classical field theory can fail once the theory is quantized. The setup is a simplified 1+1-dimensional model with a chiral (axial) current that is classically conserved, meaning its divergence vanishes, $\partial_\mu j^\mu = 0$. The quantity of interest is the divergence of this current after quantization, evaluated with an explicit regulator that controls ultraviolet behavior.

The purpose of the toy is to stress-test the assumption that classical symmetries automatically survive quantization. The conceptual issue being illustrated is that regularization and renormalization introduce additional structure, and enforcing symmetry before or after removing the regulator need not give the same result. In this proxy model the regulated quantum divergence approaches a finite, nonzero value as the cutoff $\Lambda$ is taken large, $\partial_\mu j^\mu \sim \tfrac{g}{\pi}(1-e^{-\Lambda})$, exposing a failure mode where the limit $\Lambda\to\infty$ does not commute with classical symmetry enforcement.

The JSON results list several sample points at increasing regulator cutoff values. The `classical_divergence` remains exactly zero at all points, while the `regulated_quantum_divergence` grows toward the fixed `anomaly_coefficient_invariant`, numerically close to $g/\pi$. What matters is the convergence pattern: the regulated quantity saturates to a stable value rather than returning to zero as the regulator is removed. The precise numbers should not be over-interpreted as physical predictions; instead, they illustrate how a regulator-dependent expression leaves behind an invariant remnant that conceptually corresponds to the anomaly encoded in the equations.

---

## Toy 033 — Non-Commuting Limits in Time Evolution and UV Removal

This toy illustrates how taking idealized limits in different orders can lead to qualitatively different outcomes, even in a simple proxy for quantum field theory dynamics. The setup considers a single free scalar mode with an ultraviolet cutoff $\Lambda$ and an observable that decays in time according to $O(t,\Lambda)=\exp(-t/\Lambda)$. The quantity of interest is how this observable behaves when one compares finite-time, finite-cutoff evolution with two limiting procedures that idealize either infinite resolution or infinite time.

The toy exists to expose a failure mode in reasoning rather than to model a physical system. The conceptual issue is that the limits $\Lambda\to\infty$ (removing the UV cutoff) and $t\to\infty$ (long-time evolution) do not commute. Procedure A removes the cutoff first and then evolves, yielding a nearly constant result close to unity, while procedure B evolves for long time at fixed cutoff and only then considers large $\Lambda$, yielding a strongly suppressed value. This demonstrates that idealizations in QFT are order-dependent, and that assuming a unique “correct” ideal limit can mask genuine ambiguities.

The JSON output provides sample points for several cutoff values and times. The `observable_direct` entries show smooth decay with increasing $t$ at fixed $\Lambda$, while the two limit diagnostics highlight the contrast: `limit_A_remove_cutoff_first` stays near one for all times, whereas `limit_B_long_time_first` depends only on $\Lambda$ and can be orders of magnitude smaller. What matters is the persistent separation between these limiting values, not the specific numerical magnitudes. These numbers should not be over-interpreted as predictions; instead, they conceptually connect back to the exponential form of the observable and illustrate how different paths through the $(t,\Lambda)$ plane encode different idealized answers.

---

## Toy 034 — Superselection Sectors and Forbidden Superpositions

This toy illustrates how global symmetries restrict which quantum superpositions are physically meaningful, even when they are mathematically well-defined. The setup considers a quantum system with an exact global U(1) charge, and states labeled by discrete total charge values. The quantity of interest is a proxy for quantum interference between two charge sectors, represented abstractly by a matrix element like $\langle q_1|O|q_2\rangle$, which captures whether coherent superposition between the two states can occur.

The toy exists to expose a limitation in naïve reasoning about Hilbert space structure. While quantum mechanics formally allows linear combinations of any states, superselection rules partition the Hilbert space into disconnected sectors labeled by conserved global charges. The conceptual issue being tested is not dynamical suppression but outright prohibition: transitions and interference between sectors with different total charge are blocked, even though classical mixtures remain allowed. This serves as a stress test for the assumption that all superpositions are physically realizable if no local conservation law is violated.

The JSON output lists pairs of charge labels and the corresponding diagnostics. When `charge_1` equals `charge_2`, the `interference_amplitude` is nonzero and `quantum_superposition_allowed` is true, indicating allowed quantum interference within a single sector. When the charges differ, the interference amplitude vanishes exactly, even though `classical_mixture_allowed` remains true, signaling that probabilistic mixtures should not be confused with coherent superpositions. The absolute values themselves carry no physical prediction; what matters is the strict pattern of zeros and nonzeros, which conceptually reflects how global charge conservation enforces superselection independently of any dynamical details.

---

## Toy 035 — Haag Duality Failure from Boundary Degrees of Freedom

This toy illustrates how Haag duality can fail even in a simple quantum field theory–style setting when boundary degrees of freedom are present. The physical setup is an interval in flat Minkowski spacetime, treated abstractly through proxies for observable algebras rather than explicit operators. For a region of size $R$, the toy tracks two quantities: a naive local observable algebra size and a reconstructed algebra size obtained from the commutant of the complement, with the latter modeled as $C(R)=R+e$, where $e$ denotes a boundary-mode contribution.

The toy exists to expose a conceptual limitation in how locality is often idealized. Haag duality asserts that the algebra of observables in a region should equal the commutant of observables outside that region, but this equality is fragile in the presence of edge modes, global constraints, or gauge redundancies. Rather than making a physical prediction, the model stress-tests the assumption of local completeness by deliberately inserting a boundary contribution that obstructs the identification $A(R)=C(R)$, thereby demonstrating how duality can fail even when the bulk description appears trivial.

The JSON output should be read as a diagnostic table rather than as data to be fitted or extrapolated. For each region size, compare the `local_algebra_dimension_proxy` to the `commutant_algebra_dimension_proxy`: the persistent offset and the `haag_duality_exact: false` flag signal the failure of duality across all sampled scales. The absolute magnitudes are not meaningful on their own, and the linear growth with $R$ should not be over-interpreted as dynamical behavior; what matters is the consistent mismatch and its association with `boundary_modes_present`. Conceptually, the JSON values encode the difference between $A(R)$ and $C(R)$ introduced by the boundary term, illustrating how the equations are reflected in the structured output.

---

## Toy 036 — Cluster Decomposition Failure from Long-Range Entanglement

This toy illustrates how cluster decomposition can fail when correlations persist over large separations. The physical setup is a pair of spatially separated regions in flat Minkowski spacetime, represented through proxy observables rather than explicit field operators. As the separation distance $d$ increases, the toy tracks a connected correlator intended to decay but deliberately retaining a long tail, modeled as $G_c(d)=\exp(-d/\xi)$, where $\xi$ is a correlation length controlling how slowly correlations fade.

The purpose of the toy is to stress-test the assumption that distant experiments are independent. Cluster decomposition asserts that connected correlations vanish at large separation, but long-range entanglement or global constraints can obstruct this factorization. Rather than claiming such behavior is generic or physical, the model exposes a failure mode in which the limit $G_c(d)\to 0$ is too slow to guarantee independence, highlighting that the principle of factorization is conditional rather than automatic.

The JSON results should be interpreted by comparing how different diagnostics behave as separation grows. The steadily decreasing but nonzero `connected_correlator` and the more slowly decaying `mutual_information_proxy`, roughly following $I(d)=\exp(-\sqrt{d/\xi})$, indicate residual correlations even at the largest distances sampled. The exact numerical values and decay shapes should not be over-interpreted as predictions; what matters is the consistent `cluster_decomposition_exact: false` flag and the persistence of mutual information. These trends conceptually connect the reported values back to the decay laws, illustrating how long-range structure prevents clean factorization in the output.

---

## Toy 037 — Failure of a Preferred Global Hamiltonian

This toy illustrates how global time evolution in quantum field theory depends on the choice of time slicing rather than being governed by a unique Hamiltonian. The setup uses a free scalar field represented in mode space, where each mode is labeled by a frequency $w$. Two admissible generators of time evolution are compared: a standard inertial choice with energy $E_{\mathrm{std}}(w)=w$ and an alternative slicing with energy $E_{\mathrm{alt}}(w)=\alpha w^2$, where $\alpha$ parameterizes the slicing choice.

The toy exists to expose a structural ambiguity rather than to model real dynamics. In many presentations, “the Hamiltonian” is treated as a canonical object, but this obscures the fact that time evolution is defined only after a choice of time coordinate. By placing two inequivalent generators side by side, the toy stress-tests the assumption of a preferred notion of energy and shows how different slicings can lead to different spectra without violating internal consistency. This is framed as a limitation of global descriptions, not as a statement that one choice is more physical than another.

The JSON results should be read as a comparison between these choices across mode frequencies. For each frequency, the reported energies differ in magnitude and scaling, while the `unique_time_evolution: false` flag signals the absence of a single invariant generator. The fact that both spectra are nonnegative here should not be over-interpreted as generic vacuum stability; it simply reflects the chosen parameters. Conceptually, the listed values encode how $E_{\mathrm{std}}(w)$ and $E_{\mathrm{alt}}(w)$ realize different time evolutions for the same underlying modes, making the dependence on the defining equations explicit in the output.

---

## Toy 038 — Finite-Volume Artifacts and Non-Uniform Thermodynamic Limits

This toy illustrates how placing a quantum field theory in a finite spatial volume can qualitatively change its behavior even when the local dynamics are simple. The physical setup is a free scalar field living on a spatial circle of length $L$, used as a proxy for finite-volume quantization. Two quantities are tracked as $L$ increases: the spacing of momentum modes, given by $\Delta k = 2\pi/L$, and a proxy for the vacuum energy density that includes finite-size corrections.

The toy exists to stress-test the common assumption that results obtained in infinite volume smoothly approximate those at large but finite volume. Many statements about spectra, entanglement, or symmetry implicitly rely on taking $L \to \infty$, but this limit can be subtle and non-uniform. By keeping finite-volume corrections explicit, the model exposes a failure mode in which qualitative features persist longer than expected, demonstrating that the thermodynamic limit is an assumption rather than a guaranteed property of the theory.

The JSON output should be interpreted by examining how observables change with increasing box length. The decreasing `mode_spacing` reflects the gradual densification of the spectrum, while the `vacuum_energy_density_proxy` slowly approaches its continuum value as finite-size corrections shrink. The persistent `continuum_limit_reached: false` flag indicates that, within the sampled range, the infinite-volume behavior has not been cleanly attained. The exact numerical values and their linear trends should not be over-interpreted; what matters is how they encode the dependence on $L$ implied by the formulas and illustrate the non-uniform approach to the continuum in finite volume.

---

## Toy 039 — Infrared Divergences and Infraparticle Dressing Ambiguity

This toy illustrates how sharp particle states fail to exist for charged excitations coupled to massless fields. The physical setup is a charged scalar interacting with a massless, gauge-like field in flat Minkowski spacetime, represented through proxies rather than explicit dynamics. The quantity of interest is the overlap between a bare Fock particle state and a physically dressed state as an infrared cutoff $\epsilon$ is lowered, modeled by $O(\epsilon)=\exp(-q^2\log(1/\epsilon))$, where $q$ denotes the charge.

The toy exists to expose a limitation of the particle concept in the presence of infrared divergences. In such systems, long-wavelength modes never fully decouple, and the notion of an isolated particle becomes ambiguous. Rather than predicting physical spectra, the model stress-tests the assumption that charged states can be cleanly represented in Fock space, demonstrating how soft dressing is required and how that dressing is inherently non-unique as the infrared cutoff is removed.

The JSON results should be interpreted by tracking how observables behave as $\epsilon$ decreases. The monotonic decline of `particle_state_overlap` toward zero signals the loss of a sharp particle interpretation, while the growth of `dressing_norm_proxy` reflects the increasing weight of soft modes in the dressed state. The precise numerical values and their functional forms should not be over-interpreted; what matters is the consistent `sharp_particle_state: false` flag and the trend toward the infraparticle regime. Conceptually, these values encode how the overlap formula and dressing behavior manifest in the output, illustrating the infrared obstruction rather than quantifying a physical prediction.

---

## Toy 040 — Gauge Invariance Versus Local Charged Operators

This toy illustrates a basic tension in gauge theories between gauge invariance and strict locality. The setup is a simple U(1) gauge theory in flat Minkowski spacetime, where one attempts to define an operator that creates or measures a charged excitation. The quantity of interest is a proxy for how spatially extended such an operator must be once it is made gauge invariant, modeled here as a function of a dressing length $L$ through a simple relation like $N(L)=q\log(1+L)$, where $q$ is the charge.

The toy exists to expose a conceptual failure mode rather than to make a physical prediction. In an exactly gauge-invariant theory, a naïvely local operator that carries charge is not a valid observable, because it fails to respect the gauge symmetry. The only way to restore gauge invariance is to “dress” the operator with gauge fields, and this dressing is inherently nonlocal, extending to infinity or to a boundary. This serves as a stress test for the idea of strictly local observables, demonstrating that locality and gauge invariance cannot be simultaneously maintained for charged operators, even in the simplest setting.

The JSON results should be read as bookkeeping for this tension rather than as measurements. Each sample point lists a dressing length and a corresponding nonlocality proxy that increases monotonically with $L$, while flags consistently indicate that strictly local charged observables are invalid. The important trend is the growth of the nonlocality proxy with increasing dressing length, not its absolute numerical value. These numbers should not be over-interpreted as physical sizes or energies; they merely encode the conceptual link between the dressing required by gauge invariance and the loss of strict locality implied by relations like $N(L)=q\log(1+L)$.

---

