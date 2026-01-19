# Phase 2 — Vacuum Structure & State Ambiguity

**Toys 011–020**

---

## Toy 011 — Schwinger Pair Production and Vacuum Instability

This toy evaluates the rate of particle–antiparticle pair production for a charged scalar field placed in a constant external electric field, treating the field as a fixed classical background. The physical quantity of interest is the pair production rate per unit volume, computed using a semiclassical proxy for the Schwinger effect, $\Gamma \sim (qE/2\pi)\exp(-\pi m^2/(qE))$, where $m$ is the particle mass, $q$ its charge, and $E$ the electric field strength. Even though the field theory is otherwise free, the presence of the background field destabilizes the vacuum and allows real particles to emerge.

The purpose of the toy is to illustrate that the quantum field theory vacuum is not an immutable, interaction-free ground state, but instead depends on the environment in which the field is placed. In sufficiently strong classical backgrounds, particle production occurs without any scattering or interactions among quanta, exposing a limitation of the intuition that “nothing happens” in the vacuum. This setup is a stress test of the notion of vacuum stability, emphasizing that vacuum persistence is conditional rather than guaranteed by the absence of explicit interaction terms.

The JSON output lists several values of the external electric field and the corresponding pair production rate density. The important trend is the rapid increase of the rate as $qE$ approaches and exceeds $m^2$, reflected in the exponential sensitivity to the inverse field strength. Absolute numerical values should not be over-interpreted as precise physical predictions, since the formula is used here only as a semiclassical proxy and ignores backreaction and dimensional subtleties. Conceptually, the reported rates encode how the exponential factor in the Schwinger expression governs vacuum decay, linking the sampled JSON values directly back to the dependence of $\Gamma$ on $m^2/(qE)$.

---

## Toy 012 — Haag’s Theorem and the Interaction Picture Obstruction

This toy models the overlap between the vacuum of a free scalar field and the vacuum of an interacting theory as the number of modes is increased. The physical quantity of interest is a proxy for the vacuum overlap $\langle 0_{\text{free}} | 0_{\text{int}} \rangle$, intended to capture how similar the two ground states are when both are expressed in the same formal Hilbert space. Rather than constructing full Hamiltonians, the toy uses an exponential ansatz that depends on the interaction strength and the number of modes, mimicking how adding more degrees of freedom changes the structure of the vacuum.

The purpose of the toy is to illustrate the content of Haag’s theorem as a stress test of the interaction picture. In an interacting quantum field theory, the free and interacting fields cannot be related by a single global unitary transformation acting on one Hilbert space, even if perturbation theory suggests otherwise. By letting the vacuum overlap decay with mode count according to $\langle 0_{\text{free}} | 0_{\text{int}} \rangle \sim \exp(-c\,\lambda^2 N)$, where $\lambda$ is the coupling and $N$ the number of modes, the toy frames this as an orthogonality catastrophe rather than a technical pathology. The point is not to compute a physical overlap, but to expose the limitation of decomposing the theory into “free plus interaction” beyond finite truncations.

The JSON results list several mode counts and the corresponding values of the vacuum overlap proxy. The important trend is the monotonic decrease of the overlap as the number of modes grows, even though for the finite values shown it remains well above zero. These numbers should not be over-interpreted as quantitative measures of unitarity or as evidence that the interaction picture truly holds at finite $N$; they are deliberately schematic. Conceptually, the reported overlaps encode how the exponential dependence on $N$ drives the free and interacting vacua toward orthogonality in the infinite-mode limit, connecting the sampled values directly back to the proxy expression for $\langle 0_{\text{free}} | 0_{\text{int}} \rangle$.

---

## Toy 013 — Vacuum Fluctuations vs Measurement Resolution

This toy illustrates how vacuum fluctuations of a quantum field depend on the resolution of the measurement used to probe them. The setup is a free real scalar field in flat 1+1-dimensional Minkowski spacetime, where instead of attempting to measure the field at a single point, the field operator is smeared over space with a Gaussian profile of width $\sigma$. The quantity of interest is the variance of this smeared field operator, defined schematically as $\langle \phi_f^2 \rangle = \int dk \, (4\pi \omega_k)^{-1} |\tilde f_\sigma(k)|^2$, where $\omega_k$ is the relativistic mode frequency and $\tilde f_\sigma(k)$ encodes the finite spatial resolution of the detector.

The toy exists to expose a limitation of naïve locality in quantum field theory rather than to make a physical prediction. It stresses the conceptual issue that strictly pointlike field observables are ill-defined: as the smearing width $\sigma$ is reduced, higher-momentum modes contribute more strongly, and the variance grows without bound in the limit of perfect resolution. This behavior demonstrates a failure mode of treating local fields as measurable objects and frames smearing as an operational necessity, not an optional technical trick, emphasizing that “local” only has meaning relative to a finite detector resolution.

The JSON output should be read as a set of sample points showing how the smeared field variance depends on $\sigma$ for a fixed ultraviolet cutoff $\Lambda$. The key trend is monotonic growth of the reported `smeared_field_variance` as $\sigma$ decreases, with the flag `pointlike_limit_defined` explicitly indicating that no finite value is assigned at $\sigma \to 0$. The absolute numbers depend on the regulator and discretization and should not be over-interpreted; what matters are the relative changes and the sign of the trend. Conceptually, each value represents a regulated evaluation of the variance integral, and the increasing magnitude directly reflects the enhanced weight of short-distance modes implied by the Gaussian factor in the defining equation.

---

## Toy 014 — Entropy Production from Coarse-Graining under Unitary Evolution

This toy illustrates how entropy-like behavior can emerge in a quantum field theory even when the underlying dynamics are exactly unitary. The setup uses a collection of free scalar field modes as a proxy for a 1+1D quantum field, which are split into an “observed” subset and an “unobserved” subset of momentum modes. The quantity of interest is the von Neumann entropy of the reduced density matrix obtained after tracing out the unobserved modes, modeled here by a simple proxy function $S(t) \sim S_{\max}(1 - e^{-\epsilon t})$, where $t$ is time and $\epsilon$ sets the coarse-graining rate.

The purpose of the toy is to stress-test the apparent tension between unitarity and irreversibility. It demonstrates that entropy increase does not signal a breakdown of unitary quantum evolution but instead reflects an ambiguity introduced by coarse-graining and subsystem choice. By fixing a particular split between observed and unobserved modes, the toy exposes how irreversibility and entropy production are emergent features tied to information loss under tracing, rather than fundamental properties of the dynamics themselves.

The JSON results should be interpreted as a time series showing the monotonic growth of the reduced entropy for the observed modes. The key features to watch are the steady increase of `reduced_entropy` with time and the simultaneous flags indicating preserved global unitarity and local irreversibility. The absolute entropy values and their saturation level depend on the chosen number of observed modes and the proxy model and should not be over-interpreted as physical entropy production rates. Conceptually, each reported value reflects how the coarse-grained entropy tracks the accumulation of entanglement implied by the entropy-growth formula, rather than any non-unitary evolution of the full system.

---

## Toy 015 — UV/IR Mixing as Cutoff Sensitivity of Long-Distance Correlators

This toy illustrates how a nominally long-distance observable in a quantum field theory can retain sensitivity to short-distance structure. The setup is a free real scalar field in flat 1+1-dimensional Minkowski spacetime, where the equal-time two-point correlator is evaluated at a fixed, relatively large spatial separation $x$. The quantity of interest is the regulated correlator $G(x) = \int_{-\Lambda}^{\Lambda} dk \, (4\pi \omega_k)^{-1} \cos(k x)$, with $\omega_k$ the relativistic mode frequency and $\Lambda$ a hard ultraviolet momentum cutoff.

The toy exists to stress-test the intuition that infrared (IR) physics automatically decouples from ultraviolet (UV) details. It exposes a conceptual pressure point: even in a free theory with no interactions, regulating short-distance modes leaves a residual imprint on observables that are otherwise interpreted as long-distance. This is not presented as a claim about physical UV/IR mixing in nature, but as a controlled demonstration that decoupling is a property that must be established, not assumed, and that certain regulated quantities can fail this expectation.

The JSON results should be read as a comparison of correlator values at fixed separation $x$ while the UV cutoff $\Lambda$ is varied. The important feature is that `equal_time_correlator_G` does not settle to a single stable value as $\Lambda$ increases, but instead shifts in magnitude and even slightly in sign structure, despite probing the same large-distance separation. The small absolute values and numerical fluctuations should not be over-interpreted; what matters is the persistence of cutoff dependence itself. Conceptually, each reported number reflects how the cosine-weighted integral over modes continues to sample UV contributions, linking the numerical trend directly back to the structure of the correlator integral.

---

## Toy 016 — State Dependence of Local Energy Density

This toy illustrates how the local energy density of a quantum field depends crucially on the quantum state, even when the underlying theory and spacetime are held fixed. The setup is a free real scalar field in flat 1+1-dimensional Minkowski spacetime, and the quantity of interest is a proxy for the local energy density $\langle T_{tt} \rangle$. The toy compares three states defined on the same background: the vacuum, a thermal state at temperature $T$, and a squeezed state characterized by a squeeze parameter $r$.

The purpose of the toy is to expose the limitation of attributing physical meaning to local observables without specifying a state. It demonstrates that geometry and field content alone do not determine measurable quantities, and that even the notion of “vacuum energy” is ambiguous without further structure such as renormalization or boundary conditions. Framed as a stress test, the toy emphasizes that radically different values of $\langle T_{tt} \rangle$ can arise purely from state choice, underscoring that the vacuum is not unique or intrinsically privileged.

The JSON results should be interpreted as a side-by-side comparison of energy density proxies for different states. The key features are that the vacuum entry leaves `energy_density_T_tt` undefined, reflecting its divergent character without renormalization, while the thermal state yields a modest finite value and the squeezed state produces a much larger one. The absolute magnitudes are regulator-dependent and should not be over-interpreted as physical predictions; what matters is the hierarchy and contrast between states. Conceptually, each value reflects how different occupation numbers enter the same energy-density integral, linking the numerical outcomes directly back to the state dependence implicit in $\langle T_{tt} \rangle$.

---

## Toy 017 — Locality versus Energy Positivity

This toy illustrates how local energy density behaves in quantum field theory when probed at different temporal resolutions. The setup is a free real scalar field in flat 1+1-dimensional Minkowski spacetime, and the quantity of interest is the energy density operator $T_{tt}$ evaluated in a highly localized negative-energy configuration. Two diagnostics are compared: an instantaneous (pointlike) energy density and a temporally smeared, averaged energy density obtained by integrating over a time scale $\tau$, which serves as an operational proxy for a finite-duration measurement.

The toy exists to expose the failure of classical energy conditions and to stress-test the tension between locality and energy positivity in QFT. It demonstrates that while negative local energy densities are allowed, they are not arbitrary: pointlike measurements are ill-defined, and physically meaningful observables require smearing. Quantum energy inequalities impose bounds of the schematic form $\langle \rho \rangle_\tau \ge -C/\tau^2$, showing that irreducible constraints replace classical positivity rather than restoring it.

The JSON results should be read by comparing the constant negative `instantaneous_energy_density` with the $\tau$-dependent `averaged_energy_density`. The important trend is that, as the smearing time increases, the averaged energy density becomes less negative and respects the stated bound, with the flag `qi_respected` remaining true in all cases. The precise numerical values and the chosen constant $C$ should not be over-interpreted; they are proxies illustrating boundedness, not sharp inequalities. Conceptually, the data show how the same underlying negative-energy configuration yields radically different diagnostics depending on whether one interprets the energy density pointwise or through the smeared inequality that gives operational meaning to the equations.

---

## Toy 018 — Measurement-Induced Disturbance from Non-Commuting Local Probes

This toy illustrates how finite-resolution measurements in a quantum field theory disturb each other even when they are spacelike separated. The setup is a free real scalar field in 1+1 dimensions, probed by two Gaussian-smeared field measurements separated by a fixed spatial distance. The quantity of interest is a proxy for the magnitude of the smeared field commutator at spacelike separation, conceptually tied to expressions of the form $$[\phi_\sigma(x),\phi_\sigma(0)] \sim \int dk\,\sin(kx)\,e^{-\sigma^2 k^2}/\omega_k$$ where $\sigma$ is the smearing width and $\omega_k$ is the relativistic mode frequency.

The toy exists to expose a limitation in the naive notion of measurement locality. While microcausality states that sharply localized field operators commute at spacelike separation, operational measurements necessarily involve finite smearing and backreaction. This toy stresses that these two notions are not equivalent: improving resolution amplifies disturbance even as the formal commutator becomes small. The model is not a physical prediction but a stress test of the assumption that locality of operators implies locality of measurements, highlighting the conceptual tension between resolution and disturbance through the scaling $D(\sigma)\propto 1/\sigma^2$.

The JSON results should be read comparatively across smearing widths rather than as absolute values. The `smeared_commutator_magnitude` entries show extremely small numbers that decrease mildly with increasing $\sigma$, signaling approximate operator commutativity at finite resolution. In contrast, the `state_disturbance_proxy` grows rapidly as $\sigma$ decreases, indicating that sharper measurements induce larger backreaction. What matters is this opposing trend, not the precise numerical magnitudes, which depend on cutoffs and discretization. These values should not be over-interpreted as physical observables; they serve only to connect the qualitative behavior of the proxies back to the conceptual equations governing smearing and disturbance.

---

## Toy 019 — Local Operator Algebra vs Global State Reconstruction

This toy demonstrates that agreement on all local observables within a finite region does not fix the global quantum state. The setup uses a free real scalar field in 1+1 dimensions and compares two globally distinct states—a thermal state and a globally squeezed state—constructed to share identical local two-point data inside a region of fixed size. The quantity of interest is the contrast between locally matched correlators and a global diagnostic, conceptually tied to the fact that expectation values like $\langle \phi(x)\phi(y)\rangle$ restricted to $|x|,|y|<R$ do not encode the full state.

The toy exists to expose a conceptual failure mode in state reconstruction from local data. Even complete knowledge of the local operator algebra and its correlators over a finite region leaves the global state underdetermined, much as local curvature data fails to uniquely specify a global spacetime in general relativity. This is framed as a stress test rather than a prediction: two states are engineered to coincide locally while differing sharply in global quantities such as total energy, illustrating that the mapping from local data to global state is not injective, schematically $\{\text{local correlators}\}\nRightarrow \rho_{\text{global}}$.

The JSON results should be interpreted by comparing entries across the two sample points labeled by state. The `local_correlator_value` is identical by construction, confirming local indistinguishability within the region, while the `global_energy_proxy` differs by orders of magnitude between the thermal and squeezed cases. The absolute size of the energy proxy depends on the cutoff and regulator and should not be over-interpreted; what matters is the stark disparity despite matching local data. These values connect back to the underlying principle that global observables integrate information inaccessible to finite-region correlators, highlighting the gap between local agreement and global reconstruction.

---

## Toy 020 — Reeh–Schlieder Proxy: Local Operators with Global Reach

This toy illustrates how operators localized in an arbitrarily small region can generate states with global support in a quantum field theory. The setup uses a free real scalar field in 1+1 dimensions and considers the action of a local operator algebra on the vacuum, probing its overlap with a fixed globally excited target state. The quantity of interest is a proxy for the overlap $\langle \psi_{\text{target}} | O_R | 0 \rangle$, where $O_R$ is supported in a region of size $R$, alongside an associated energy cost required to achieve that overlap.

The toy exists to expose a failure of a strict separation between “local” and “global” degrees of freedom. It stress-tests the intuition that shrinking the support of operators should isolate subsystems, showing instead that nonzero overlap with arbitrary global states persists even as $R \to 0$. This reflects the Reeh–Schlieder phenomenon: local control implies nonlocal reach, but at a steep operational price. The limitation is not about physical feasibility but about conceptual structure, captured by the tension between nonvanishing overlap and a rapidly diverging cost scaling like $C(R)\propto 1/R^2$.

The JSON results should be read as a tradeoff across region sizes. The `state_overlap_proxy` decreases exponentially as the region shrinks, indicating that global state preparation from very small regions becomes increasingly suppressed but never exactly zero. At the same time, the `energy_cost_proxy` grows sharply, signaling the operational burden required to maintain that overlap. The precise numerical values should not be over-interpreted; what matters is the joint trend of nonzero overlap with divergent cost. Together, these proxies connect back to the equations by showing how local operators can approximate global states in principle while becoming prohibitively expensive in practice.

---

