# Phase 6 — Entanglement Wedges & Information Localization

**Toys 051–060**

---

## Toy 051 — Entanglement wedge mismatch under local access

This toy constructs two different pure quantum states of a three-qubit system labeled A, B, and C, and then restricts attention to the joint subsystem AB. The physical setup is deliberately minimal: one state is GHZ-like across all three qubits, while the other is a Bell-entangled pair on AB tensored with a product state on C. The quantity of interest is the reduced density matrix on AB, obtained by tracing out C, conceptually written as $\rho_{AB}=\mathrm{Tr}_C(\rho_{ABC})$.

The toy exists to illustrate a limitation of local state reconstruction rather than to make a physical prediction. In quantum field theory language, it stresses the idea that access to all local observables in a region does not, in general, fix the global quantum state, because different global states can project to the same or confusingly similar local data. This example exposes that ambiguity as a pressure point: comparing two candidate global states via a norm like $\|\rho_{AB}^{(1)}-\rho_{AB}^{(2)}\|$ highlights how expectations about local indistinguishability can fail or become subtle in concrete constructions.

The JSON output should be read as a diagnostic rather than a verdict. The key number is `reduced_state_difference_norm`, reported for subsystem AB and summarized as `local_indistinguishability_norm`; its nonzero magnitude (about $7\times10^{-1}$) signals a measurable difference between the reduced states in this toy implementation. The sign is irrelevant and the absolute scale only matters relative to zero: values near zero would indicate practical local agreement, while larger values indicate distinguishability. This should not be over-interpreted as a universal measure of entanglement or reconstructability; it simply connects back to the reduced-state comparison implied by $\rho_{AB}=\mathrm{Tr}_C(\rho_{ABC})$ and demonstrates how local diagnostics can mislead about global structure.

---

## Toy 052 — Non-additivity of entanglement under naive region splitting

This toy examines how quantum entanglement behaves when a composite system is divided into smaller regions. The setup is a four-qubit pure state where qubits A and B define a region R, and qubits C and D form its complement, with entanglement arranged across the AB–CD split. The quantity of interest is the von Neumann entropy of reduced states, defined for a density matrix $\rho$ as $S(\rho)=-\mathrm{Tr}(\rho\log\rho)$, which serves here as a measure of entanglement between a region and its complement.

The purpose of the toy is to demonstrate that entanglement entropy is not additive under naive subdivision of a region into parts. One might expect that the entropy of region AB could be recovered as the sum of entropies of A and B individually, but this assumption encodes a hidden factorization that generally fails. The example is a stress test for subsystem bookkeeping: it exposes how boundary correlations and shared entanglement invalidate the relation $S(AB)=S(A)+S(B)$ even in a finite, fully controlled model, mirroring conceptual issues that arise in continuum quantum field theory.

The JSON results report the entropies $S(AB)$, $S(A)$, and $S(B)$ along with the derived quantity $S(A)+S(B)-S(AB)$. The important feature is the positive nonzero value of this gap, indicating clear non-additivity rather than numerical noise or sign conventions. The absolute magnitude should not be over-interpreted as a universal measure of correlation strength; it simply reflects the specific state chosen. Conceptually, these numbers connect back to the entropy definition by showing that tracing out different complements leads to reduced states whose entropies cannot be recombined as if the subsystems were independent.

---

## Toy 053 — Measurement-algebra–dependent state distinguishability

This toy compares two orthogonal pure states of a two-qubit system and asks whether they can be told apart given different levels of measurement access. The physical setup is simple: the states differ only by a relative phase, making them perfectly distinguishable when probed globally but potentially identical when viewed through a restricted lens. The quantity of interest is the trace distance, defined for density matrices $\rho$ and $\sigma$ as $D(\rho,\sigma)=\tfrac{1}{2}\|\rho-\sigma\|_1$, which operationally measures how well two states can be distinguished by allowed measurements.

The toy exists to stress that “being different quantum states” is not an absolute statement but depends on the measurement algebra one is allowed to use. Conceptually, it illustrates a failure mode where global orthogonality does not translate into local distinguishability, exposing an ambiguity that arises whenever measurements are restricted to subalgebras, such as local or coarse-grained observables. This is framed as a limitation test: the example demonstrates how operational notions of difference collapse when access is reduced, rather than asserting anything about fundamental physical reality.

The JSON output reports two trace distances: `trace_distance_global`, computed from the full two-qubit density matrices, and `trace_distance_single_qubit`, computed after tracing down to a single qubit. The key trend is the sharp contrast between a value near one globally and exactly zero locally, summarized by the `global_vs_local_gap`. The sign and exact numerical precision should not be over-interpreted; what matters is the qualitative separation between global and local values. These numbers connect back to the trace-distance definition by showing that restricting $\rho$ to reduced states erases the distinguishing features present in the full $\rho_{AB}$, making the states operationally identical under the limited measurement algebra.

---

## Toy 054 — Non-commutativity of continuum and late-time limits

This toy uses a damped harmonic oscillator with a simple ultraviolet cutoff as a proxy for more complex quantum field theoretic systems. The model evolves a single occupation-like variable forward in time with damping and a cutoff-dependent source term, and then inspects its late-time value. The quantity of interest is the asymptotic value reached by this variable, loosely analogous to a late-time expectation value, governed schematically by an equation of the form $\dot n=-\gamma n+\text{cutoff}$.

The purpose of the toy is to demonstrate that taking different limits in different orders can lead to inequivalent outcomes. Here, one can either evolve to late times at fixed cutoff and then remove the cutoff, or remove the cutoff first and then evolve to late times; these two procedures do not agree. This is framed explicitly as a stress test for limit-taking intuition: it exposes how “the limit theory” is ambiguous when continuum, infinite-time, or infinite-volume limits fail to commute, rather than asserting any physical prediction about real oscillators.

The JSON results list, for each cutoff value, the late-time observable obtained by taking the time limit first, the corresponding value obtained by taking the cutoff to zero first, and their difference. What matters is the clear trend that the difference grows with the cutoff and does not vanish, summarized by the reported `max_difference`. The absolute numerical values and their dependence on discretization parameters like `dt` or `t_max` should not be over-interpreted. Conceptually, these numbers illustrate that the late-time solution of $\dot n=-\gamma n+\text{cutoff}$ depends on whether the source term is removed before or after the long-time limit, directly tying the JSON values back to the idea of non-commuting limits.

---

## Toy 055 — Vacuum selection by boundary conditions

This toy compares how the vacuum of a simple quantum field changes when different boundary conditions are imposed. The setup is a single free scalar field mode on a one-dimensional finite interval of length $L$, with either periodic or Dirichlet boundary conditions fixing the allowed momenta. The quantity of interest is the zero-point (vacuum) energy, modeled as a sum over mode frequencies via $E_0=\tfrac{1}{2}\sum_k |k|$.

The toy exists to illustrate that the vacuum is not uniquely determined by local equations of motion alone. Even though the field dynamics are identical in the bulk, changing the boundary conditions alters the mode spectrum and therefore selects an inequivalent vacuum state. This is framed as a limitation test: it exposes how statements about “the vacuum” implicitly depend on global or asymptotic choices, rather than being intrinsic predictions of the local field theory.

The JSON output reports the vacuum energies computed with periodic and Dirichlet boundaries and their difference. What matters is the clear separation between these energies and the nonzero `vacuum_energy_gap`, which signals that the two boundary conditions lead to inequivalent ground states in this toy model. The absolute magnitude of the energies should not be over-interpreted, since they depend on the cutoff in mode number and lack any renormalization. Conceptually, the values reflect the different sets of allowed $k$ entering $E_0=\tfrac{1}{2}\sum_k |k|$, making the boundary dependence of the vacuum explicit without claiming physical universality.

---

## Toy 056 — Gauge fixing and apparent observable dependence

This toy models a very simple constrained quantum system to illustrate how gauge choices can affect computed quantities. The setup uses a two-level state that is represented in two different but gauge-related bases, implemented as unitary rotations acting on the same underlying vector. The quantity of interest is the expectation value of a naively defined operator, evaluated as $\langle O\rangle=\langle\psi|O|\psi\rangle$, which is treated here as a would-be observable.

The toy exists to expose a common failure mode in gauge theories: quantities that look physical can inherit gauge artifacts if they are not constructed to be gauge-invariant. Although the two states used in the comparison are related by a gauge transformation and represent the same physical situation, the chosen operator does not respect that symmetry. Framed as a stress test, this example demonstrates that gauge fixing is not merely a technical convenience, because intermediate or careless choices can contaminate results and lead to spurious distinctions.

The JSON output reports expectation values computed in two different gauges and their difference, summarized as the `gauge_dependence_gap`. The important feature is the nonzero gap between `expectation_gauge_A` and `expectation_gauge_B`, indicating sensitivity to the gauge choice rather than any change in the physical state. The sign and exact magnitude should not be over-interpreted; they depend on the specific rotation angle and operator used. Conceptually, these numbers tie back to $\langle O\rangle=\langle\psi|O|\psi\rangle$ by showing that when $O$ is not gauge-invariant, its expectation value varies under gauge transformations even though the underlying state is the same.

---

## Toy 057 — No invariant split between system and environment

This toy constructs a simple three-qubit pure state and asks how much entropy a “system” appears to have when different choices are made for what counts as the system versus the environment. The physical setup is a maximally entangled GHZ-type state shared by three qubits, and the quantity of interest is the von Neumann entropy of reduced density matrices obtained by tracing out different subsets. Concretely, the entropy $S(\rho) = -\mathrm{tr}(\rho \log \rho)$ is computed once for a single qubit treated as the system and once for a two-qubit block treated as the system.

The toy exists to expose a conceptual limitation rather than to make a physical prediction. In quantum field theory and related open-system formalisms, there is no invariant or preferred way to factor a global Hilbert space into “system” and “environment,” and many interpretive claims silently assume such a split. This example functions as a stress test of that assumption: it demonstrates that reduced states and their entropies are properties of a chosen factorization, not intrinsic attributes of the global state, even when the total state is fixed and pure.

The JSON output reports the entropies associated with the two different splits and their difference. Here, `entropy_system_A` and `entropy_system_AB` are both approximately $0.693$, indicating that the single-qubit system and the two-qubit system are equally mixed in this particular state, so the reported `difference` and `split_dependence_gap` vanish. What matters is not the numerical equality itself but the fact that these values are defined only relative to the chosen split; one should not over-interpret them as absolute measures of disorder or information. Conceptually, the numbers illustrate how the same global state can support different reduced descriptions, and how those descriptions connect back to the entropy formula through the act of tracing out different degrees of freedom.

---

## Toy 058 — Renormalization vs physical scale ambiguity

This toy implements a minimal model of a running coupling to show how an interaction strength depends on the scale at which it is defined. The physical setup is abstract “scale space,” where the same process is evaluated at different renormalization scales $\mu$, and the quantity of interest is the effective coupling assigned to that scale. The toy uses a simple proxy relation $g(\mu) = g_0 / (1 + \beta \log(\mu/\mu_0))$, where $g_0$ is a reference coupling defined at a reference scale $\mu_0$, and $\beta$ controls how rapidly the coupling changes.

The purpose of the toy is to illustrate a conceptual ambiguity rather than to model real renormalization group flow. In quantum field theory, parameters like “the coupling” or “the mass” are not intrinsic numbers attached to a theory but bookkeeping devices tied to a chosen scale. This toy acts as a stress test for the idea that one can quote a single parameter value without specifying context, demonstrating that different but equally valid scale choices lead to different numerical couplings even though no physical content has changed.

The JSON results list `running_coupling` values evaluated at several scales and summarize their minimum and maximum. The important feature is the monotonic trend: the coupling decreases as the scale increases for the chosen parameters, reflecting the logarithmic dependence in the defining equation. The absolute numbers should not be over-interpreted as predictions, bounds, or physical constants; they only illustrate scale dependence within the toy formula. Conceptually, each JSON entry corresponds to plugging a different $\mu$ into the same running-coupling expression, reinforcing that the variation arises from the choice of scale, not from a change in the underlying model.

---

## Toy 059 — Time-ordering vs causal ordering ambiguity

This toy considers a two-level quantum system equipped with two non-commuting observables and evaluates simple correlators in opposite operator orders. The physical setup is deliberately minimal: a fixed quantum state and two Pauli operators acting on it, with the quantity of interest being the expectation value of ordered products. The comparison is between $\langle A B \rangle$ and $\langle B A \rangle$, meant to stand in for differently time-ordered correlators.

The toy exists to illustrate a limitation in how correlation functions are interpreted in relativistic quantum theories. For non-commuting operators, the numerical value of a correlator depends on how operators are ordered in time, yet in relativistic settings the notion of “earlier” and “later” can depend on the chosen frame. This example functions as a stress test of the idea that there is a single, invariant object called “the correlator,” exposing how ordering prescriptions are an extra piece of structure rather than a derived physical necessity.

The JSON output reports the two ordered expectation values and their difference. In this specific setup, both `time_order_A_then_B` and `time_order_B_then_A` evaluate to zero, so the reported `difference` and `ordering_gap` vanish. This numerical coincidence should not be over-interpreted as the absence of an ambiguity; it reflects the special choice of state and operators rather than a general principle. Conceptually, the values correspond to inserting different operator orderings into the expectation value formula, and the toy highlights that equality or inequality of these numbers is contingent, while the dependence on ordering is structural.

---

## Toy 060 — Canonical vs path-integral mismatch

This toy compares two ways of computing the partition function of a one-dimensional quantum harmonic oscillator at inverse temperature $\beta$. The physical setup is the same in both cases—a single oscillator with frequency $\omega$ on a Euclidean time circle—but the quantity of interest, the partition function $Z(\beta)$, is obtained using different formalisms. One is the exact canonical expression $Z_{\mathrm{can}} = 1/(2\sinh(\beta \omega/2))$, while the other is a deliberately coarse discrete approximation meant to stand in for a Euclidean path integral with a finite number of time slices.

The toy exists to demonstrate a formalism-level ambiguity rather than to test thermodynamics. In principle, canonical quantization and path-integral quantization are formally equivalent, but that equivalence holds only after specifying measures, regulators, and discretization schemes. This example functions as a stress test of the assumption that “the path integral” is a single well-defined object: by introducing an explicit dependence on the number of slices $N$, it exposes how operational results can differ unless those extra choices are fixed and controlled.

The JSON results report, for each value of `N_slices`, both the canonical partition function and the discretized path-integral proxy, along with their `relative_error`. The key trend is that the relative error decreases as $N$ increases, illustrating convergence toward the canonical value as discretization is refined. The absolute values of the errors and the specific $1/N^2$ scaling should not be over-interpreted as physical predictions; they are built into the toy by construction. Conceptually, each entry shows how inserting the same parameters into two nominally equivalent expressions yields different numbers until the discretization choice is pushed toward a limit, tying the JSON values back to the partition-function formulas as an illustration of formalism dependence.

---

