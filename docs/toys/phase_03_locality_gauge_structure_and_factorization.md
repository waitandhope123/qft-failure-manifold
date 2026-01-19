# Phase 3 — Locality, Gauge Structure, & Factorization

**Toys 021–030**

---

## Toy 021 — Failure of Sharp Subsystem Factorization

This toy illustrates what happens when one tries to define a spatial subregion in a quantum field theory using an increasingly sharp boundary. The setup is a free real scalar field in 1+1-dimensional flat spacetime, where a spatial bipartition is imposed by a boundary smoothed over a length scale $\sigma$. The quantities of interest are proxy measures for energy and entanglement entropy localized near that boundary, chosen to scale as $E \sim \Lambda / \sigma$ and $S \sim \log(\Lambda / \sigma)$, where $\Lambda$ is a fixed ultraviolet cutoff.

The toy exists to expose a structural limitation rather than to model physical dynamics. In continuum QFT, local operator algebras are Type III, which means that a sharp tensor product decomposition of Hilbert space into “inside” and “outside” regions does not exist. This toy stress-tests that fact by showing that as $\sigma \to 0$, boundary-localized quantities necessarily diverge, signaling the failure of a well-defined reduced density matrix or sharp subsystem factorization. The divergence is not a prediction but a diagnostic of the ambiguity inherent in attempting to impose a sharp split.

The JSON output should be read as a regulated sequence approaching this failure mode. Each entry lists a boundary smearing $\sigma$, the fixed cutoff $\Lambda$, and the resulting energy and entropy proxies; the important trend is their monotonic growth as $\sigma$ decreases, with energy scaling inversely and entropy logarithmically. The repeated flags indicating that sharp factorization is impossible are the key qualitative result, while the absolute numerical values depend entirely on the chosen proxies and cutoff. These numbers should not be over-interpreted as physical observables; they conceptually reflect the same scaling behavior encoded in the proxy relations and illustrate how the divergences emerge as the boundary is sharpened.

---

## Toy 022 — Gauge Redundancy and the Failure of Strict Locality

This toy demonstrates how gauge redundancy obstructs the notion of strictly local physical observables in a simple U(1) gauge theory in 1+1-dimensional flat spacetime. The setup contrasts a bare charged field, which is not gauge invariant, with a gauge-invariant dressed operator whose definition necessarily extends over a finite spatial region of length $d$, called the dressing length. The quantities of interest are proxies for the spatial extent of the dressed operator and for the electric flux through a boundary implied by Gauss’s law, with the latter scaling as $\Phi \sim q / d$ for charge $q$.

The toy exists to illustrate a conceptual limitation rather than to model measurable dynamics. In gauge theories, Gauss-law constraints tie local charge to flux through boundaries, so any attempt to localize a charged observable forces nonlocal structure or boundary dependence. This is framed here as a stress test of “local subregion physics”: either the dressing is short, leading to large boundary flux and strong boundary sensitivity, or the dressing is long, leading to a delocalized operator. The failure flags emphasize that this is not a removable technicality but a structural feature of gauge-invariant operator construction.

The JSON results should be interpreted as a controlled comparison across dressing lengths. As the dressing length increases, the reported dressed operator extent grows linearly while the boundary flux proxy decreases, illustrating the tradeoff enforced by Gauss’s law. The key signal is the consistent absence of a strictly local operator and the systematic dependence on boundary-related quantities, not the specific numerical values themselves. These numbers should not be over-interpreted as physical predictions; they serve only to connect the qualitative scaling behavior in the proxies back to the conceptual relation between dressing, nonlocality, and boundary flux encoded in the toy.

---

## Toy 023 — Infrared Divergences and Memory Effects

This toy illustrates how infrared (IR) modes obstruct a clean particle-based description in a simple massless scalar field theory in 1+1-dimensional flat spacetime. The setup introduces an explicit IR cutoff $\epsilon$ and a fixed ultraviolet cutoff $\Lambda$, and tracks the accumulation of soft excitations as the cutoff is lowered. The quantity of interest is a proxy for the soft-mode occupation number, motivated by the logarithmic behavior $N_{\text{soft}} \sim \int_{\epsilon}^{\Lambda} dk / k = \log(\Lambda / \epsilon)$, which grows without bound as $\epsilon$ decreases.

The purpose of the toy is to stress-test the notion of well-defined asymptotic states rather than to make a physical prediction. In theories with massless fields, infinitely many low-energy quanta contribute to scattering processes, invalidating a naïve Fock-space picture. This toy exposes that failure mode by showing that both soft occupation and memory-related diagnostics remain sensitive to the IR regulator, reflecting a conceptual ambiguity: global information carried by soft modes cannot be captured by strictly local operators or finite-particle states.

The JSON results should be interpreted as a regulated sequence approaching this infrared obstruction. As the IR cutoff $\epsilon$ is reduced, both the soft-mode occupation and the memory-effect proxy increase logarithmically, and the flag indicating a well-defined asymptotic state remains false throughout. The important feature is the trend and its persistence, not the precise numerical values, which depend on the chosen cutoffs and proxy definitions. These values should not be over-interpreted as observable counts; they conceptually mirror the same logarithmic dependence on $\epsilon$ that appears in the integral expression and illustrate how memory effects track the accumulation of soft modes.

---

## Toy 024 — Finite-Time Unruh Detector Ambiguity

This toy illustrates how the Unruh effect emerges only as an asymptotic property of long-lived detectors rather than an instantaneous signal. The setup is an Unruh–DeWitt detector with energy gap $\Omega$ undergoing uniform acceleration $a$ in flat spacetime, interacting with a quantum field for a finite proper time $\tau_{\max}$. The quantity of interest is a proxy for the detector’s excitation probability and for detailed balance, oriented around the Unruh temperature $T = a / (2\pi)$ that would govern an exactly thermal response in the infinite-time limit.

The toy exists to expose a conceptual limitation in interpreting detector responses as evidence for thermality. Finite-time interactions necessarily violate exact detailed balance, so a detector cannot be said to “see a thermal bath” in a sharp sense at any finite $\tau_{\max}$. This is framed as a stress test of thermality: the familiar relation between excitation and de-excitation rates, $\text{ratio} \sim \exp(-\Omega / T)$, is approached only gradually, highlighting that thermality here is an emergent, asymptotic notion rather than a local or instantaneous physical prediction.

The JSON results should be read as a convergence study in detector runtime. As $\tau_{\max}$ increases, both the excitation probability proxy and the detailed balance ratio increase toward stable values, while the flag for exact thermality remains false at all finite times. The important signal is the monotonic approach toward the thermal ratios, not the small numerical magnitudes themselves, which depend on the chosen gap and acceleration. These values should not be over-interpreted as measured temperatures; they conceptually track how the finite-time response moves closer to the exponential factors associated with the Unruh temperature without ever becoming exact at finite $\tau_{\max}$.

---

## Toy 025 — Renormalization Scheme Dependence

This toy illustrates how intermediate quantities in quantum field theory depend on the chosen renormalization scheme, even when the underlying physics does not. The setup is a scalar $\phi^4$ theory in 1+1-dimensional flat spacetime, where a one-loop correction to the mass is evaluated using two different prescriptions: a momentum cutoff $\Lambda$ and a subtraction at a fixed scale $\mu$. The quantity of interest is the one-loop mass shift, schematically captured by $\delta m^2 \sim \lambda \log(\Lambda / m_0)$, alongside a constructed combination meant to stand in for a scheme-invariant physical mass.

The toy exists to expose the conceptual ambiguity in separating “bare” from “renormalized” quantities. Different schemes reshuffle contributions between parameters and counterterms, so intermediate results such as $\delta m^2$ have no direct physical meaning on their own. This is framed as a stress test of physical interpretation: varying the scheme changes the reported mass correction even though no new physics has been introduced, demonstrating that only specific combinations of parameters are meaningful and that scheme dependence is a feature, not a bug, of the formalism.

The JSON output should be read by comparing how quantities behave as the cutoff $\Lambda$ is varied. The mass correction in the cutoff scheme grows logarithmically with $\Lambda$, while the subtraction-scheme correction remains fixed by construction, illustrating explicit scheme dependence. In contrast, the reported “physical mass squared invariant” changes in a controlled way that reflects the chosen proxy for a scheme-independent combination. The absolute numbers should not be over-interpreted as predictions; what matters is which entries shift under scheme changes and which are intended to remain stable, conceptually linking the logged values back to the logarithmic dependence appearing in the loop expression.

---

## Toy 026 — Running Coupling and Loss of Scale Separation

This toy illustrates how interaction strength in quantum field theory depends on the energy scale at which it is probed, rather than being a fixed constant. The setup follows a single effective coupling $g(\mu)$ defined at a reference scale $\mu_0$, and tracks how it changes as the scale $\mu$ is varied. The quantity of interest is the running coupling itself, modeled by a one-loop proxy relation $g(\mu)^2 = g_0^2 / (1 + 2 \beta_0 g_0^2 \ln(\mu/\mu_0))$, which captures the idea that physics at different scales is governed by different effective parameters.

The toy exists to stress-test the assumption of clean scale separation. A theory that appears weakly coupled at one scale may become strongly coupled or unreliable at another, so statements like “perturbative” or “effective” are inherently scale-dependent. This is framed as a limitation of single-scale descriptions rather than a physical prediction: the running of the coupling exposes how effective field theories have bounded domains of validity, and how extrapolating beyond those domains can silently invalidate approximations without any sharp signal.

The JSON results should be interpreted as a scan over scales rather than as independent measurements. As $\mu$ increases relative to $\mu_0$, the reported coupling decreases in this proxy model, while the perturbativity flag tracks whether $g(\mu)$ remains below a chosen threshold. The important feature is the systematic dependence on $\mu$, not the specific numerical values, which depend on the chosen beta-function proxy and parameters. These values should not be over-interpreted as physical couplings; they conceptually illustrate how the logarithmic running encoded in the equation translates into a loss of global, scale-independent descriptions.

---

## Toy 027 — Entanglement Without Local Observables

This toy illustrates how quantum information can be present even when no local observable has access to it. The setup is an abstract bipartite mode system prepared in a two-mode squeezed state, commonly used as a proxy for entanglement in quantum field theory. The quantity of interest is the entanglement entropy of one subsystem as a function of the squeezing parameter $r$, given by the standard expression $S = (n+1)\log(n+1) - n\log n$ with $n = \sinh^2 r$, while local operators are restricted to act on only one part of the system.

The toy exists to expose a conceptual gap between information and observability. Even though the global state is pure and highly structured, no set of strictly local measurements can reconstruct or even detect that structure in full. This is framed as a stress test of the assumption that “what exists physically must be locally observable”: increasing entanglement increases the amount of encoded information without improving local access, demonstrating that knowledge about the global state is not equivalent to the availability of local observables.

The JSON results should be interpreted by comparing how entanglement entropy grows with $r$ while the local access flags remain uniformly false. The important trend is the monotonic increase of entropy, signaling increasing hidden information, rather than the specific numerical values themselves. These values should not be over-interpreted as operationally measurable entropies; they conceptually connect the squeezing-based entropy formula to the idea that entanglement structure carries information that remains inaccessible to any single-subsystem probe.

---

## Toy 028 — Microcausality Leakage from Smearing

This toy illustrates how exact microcausality is an idealization tied to perfectly local operators, while any physically realizable smeared operator can exhibit small spacelike “leakage.” The setup is a free scalar field in 1+1-dimensional flat spacetime, where field operators are replaced by Gaussian-smeared versions with width $\sigma$, and two such operators are evaluated at a fixed spacelike separation $x$. The quantity of interest is a proxy for the magnitude of the spacelike commutator, intended to vanish only in the sharp limit, with the sharp benchmark represented by $[\phi(x),\phi(0)]=0$ at spacelike separation.

The toy exists to stress-test the intuition that causality is an absolute, resolution-independent statement in operational settings. While the underlying field theory enforces microcausality for strictly local observables, smearing introduces a finite spatial profile that effectively blends nearby points, so commutators can acquire nonzero contributions once a UV-regulated, finite-resolution measurement is modeled. This is not a claim of superluminal signaling; it demonstrates a failure mode of “sharp lightcones” as an interpretive crutch when the observables available to an experimenter are necessarily coarse-grained.

The JSON output should be read by comparing the reported spacelike commutator leakage across smearing widths at fixed separation and cutoff. The key feature is that the sharp-limit commutator is exactly zero while the smeared leakage is nonzero but extremely small, so the relevant information is the presence and scale of the leakage relative to the idealized benchmark. Do not over-interpret the precise magnitudes as universal numbers; they are sensitive to the UV cutoff, discretization step, and the particular smearing profile used in the proxy integral. Conceptually, the leakage values are meant to be understood as the operational residue left when the exact vanishing commutator of ideal local operators is replaced by finite-$\sigma$ smeared operators, tying the JSON back to the microcausality anchor relation.

---

## Toy 029 — Vacuum ambiguity under inequivalent time slicings

This toy illustrates how a free quantum field can exhibit different notions of “particles” when the same spacetime is described using different choices of time. The setup is a mode-space proxy for a free scalar field, where two time slicings are related by a Bogoliubov transformation parameterized by a real squeeze parameter $r$. The quantities of interest are the expected particle number in one slicing when evaluated in the vacuum of the other, $n = \sinh^2(r)$, and the overlap between the two vacuum states, which measures how similar those vacua are.

The toy exists to expose a conceptual limitation rather than to make a physical prediction: the idea of a unique vacuum state is not invariant under changes of time slicing. Even in a free theory with no interactions, different observers or histories can define inequivalent Fock spaces, so that “no particles” in one description corresponds to a many-particle state in another. This acts as a stress test for any reasoning that assumes observer-independent particle content, highlighting that the failure arises from the structure of the Hilbert space rather than from dynamics or backreaction.

The JSON results list sample points at several values of the Bogoliubov parameter $r$, each reporting a particle number expectation and a vacuum overlap. As $r$ increases, the particle number grows rapidly while the overlap $|⟨0|0_r⟩| = 1/\cosh(r)$ decreases, signaling increasingly inequivalent vacua; the regime labels distinguish small-$r$ near-equivalence from large-$r$ Fock-space inequivalence. These trends and signs are what matter: increasing $n$ and decreasing overlap indicate stronger vacuum ambiguity. The absolute numerical values should not be over-interpreted as physical counts, but read as diagnostics tied conceptually to the defining relations for $n$ and the overlap.

---

## Toy 030 — Absence of a local particle number operator

This toy demonstrates that, in quantum field theory, particles are not objects that can be counted locally in space and time. The physical setup is a free scalar field in flat 1+1-dimensional Minkowski spacetime, where one attempts to define a “local particle number” by smearing field observables over a region of width $\sigma$. The quantity of interest is how such a localized proxy compares with a well-defined asymptotic particle number $N_\infty$, illustrating that local measurements access fields rather than particle counts.

The purpose of the toy is to stress-test the particle concept itself by exposing a failure mode: sharpening localization does not improve the definition of particle number but instead destabilizes it. Conceptually, this reflects the fact that particle number is tied to global mode decompositions and asymptotic time evolution, not to local operators. As a diagnostic, the toy contrasts an attempted scaling $N_{\text{loc}} \sim N_\infty/\sigma$ with growing fluctuations, showing that the limitation is structural rather than a matter of approximation or missing dynamics.

The JSON results should be read as diagnostics rather than measurements. Each sample point lists a smearing width $\sigma$, an attempted local particle number (which becomes undefined or small-scale dependent), and a local fluctuation variance that scales as $\text{Var} \sim 1/\sigma^2$. The important trends are that decreasing $\sigma$ increases fluctuations and can render the local particle number undefined, while large $\sigma$ recovers behavior loosely aligned with the asymptotic $N_\infty$. These values should not be over-interpreted as literal particle counts; instead, they conceptually link back to the scaling relations to illustrate why particles emerge only asymptotically and not as fundamental local observables.

---

