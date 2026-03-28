


Open-Sourcing a Willow OTOC Quantum Echoes Proposal  
**Hardware Experiment for Google's 105-qubit Willow Processor (March 2026)**

## Why This Proposal Is Being Open-Sourced

I do not hold a PhD or any formal academic affiliation.  

Google's Willow Early Access Program (deadline May 15, 2026) explicitly requires that proposals come through a research group with a dedicated member (e.g., PhD student or post-doc) and asks for verification of employer or academic institution. Without those credentials, direct submission has near-zero chance of success, regardless of technical quality. Rather than let a strong, ready-to-run experiment sit unused, I am releasing the full proposal, Cirq code, and supporting reasoning under an open license.

**Core axiom (principled):**  
Scientific progress should be gated by the quality of the idea, its feasibility, and its potential impact - not by institutional gatekeeping. In 2026, Willow represents one of the most advanced quantum platforms on Earth. Restricting access to only credentialed groups slows the transition from quantum supremacy demonstrations to genuine quantum utility in physics and chemistry. Open-sourcing bypasses that barrier and invites collaboration from anyone who can actually run the experiment.

By making this public, the proposal can:
- Reach researchers with proper affiliation who may want to adopt or co-submit it.
- Allow independent developers, students, or citizen scientists to prototype it on the Quantum Virtual Machine (QVM) today.
- Contribute to the broader open quantum ecosystem, where ideas from outside traditional academia have repeatedly accelerated the field (e.g., many foundational Cirq contributions and open-source quantum software projects).

This is not a complaint about the system - it is a practical response to reality. The hardware is too valuable to waste on credential filters alone.

## What Is Inside This Repository

- **`willow_otoc_proposal.md`** — The complete, submission-ready proposal document (originally prepared for Google Quantum AI).
  - Measures higher-order Out-of-Time-Order Correlators (OTOCs) via unitary quantum echo circuits on up to 81 qubits.
  - Maps a 2D XXZ/transverse-field Ising lattice **and** an effective nuclear-spin dipolar Hamiltonian for molecular geometry inference.
  - Strictly complies with all published Willow boundaries: unitary-only (no mid-circuit measurements, no adaptive circuits, no error-correction demos).
  - Uses native nearest-neighbor gates on Willow’s 2D grid with zero SWAP overhead.

- **Cirq code** (embedded and as separate `.py` files) — Fully executable skeleton for the Quantum Virtual Machine with Willow noise model.
  - Trotterized forward + backward evolution.
  - Butterfly perturbation and probe measurement for OTOC extraction.
  - Ready for immediate QVM testing and parameter sweeps.

- **Supporting materials** (added over time):
  - QVM prototyping results and fidelity curves.
  - Parameter scans (trotter steps, coupling strengths, distances).
  - Extension notes for the molecular TARDIS-style echo sequences.

## Scientific Motivation (First Principles)

Out-of-Time-Order Correlators quantify operator growth and information scrambling in many-body systems. In ergodic quantum systems they exhibit algebraic decay — a signature that is exponentially hard to simulate classically at scale due to entanglement volume, yet remains verifiable on hardware.

Google’s 2025 Quantum Echoes result already showed ~13,000× speedup over Frontier on random circuits. This proposal extends that breakthrough to **physically relevant Hamiltonians**:
- 2D quantum magnets (condensed-matter benchmark: light-cone velocities).
- Small-molecule nuclear-spin models (quantum chemistry: inter-nuclear distance reconstruction via echoes).

This is the logical next step: moving from abstract supremacy to verifiable many-body physics and utility on real hardware.

## Technical Highlights

- 9×9 contiguous sub-grid (81 qubits) on Willow — optimal connectivity, minimal boundary effects.
- Native iSWAP-like + CZ gates only → circuit depth ~72 layers, expected echo fidelity > 0.6 on Device 2 (T₁ ≈ 98 μs, two-qubit error 0.14 %).
- Purely unitary echo protocol — fully compliant.
- QVM-ready today; hardware-ready if access is granted.

## How You Can Help or Use This Work

1. **Prototype it** — Run the circuits on Google’s public QVM or any Cirq-compatible simulator. Share results, optimizations, or molecular mappings.
2. **Adopt and submit** — If you have academic or institutional affiliation, feel free to use this proposal (with attribution) for the Willow Early Access Program or similar calls (e.g., via NQCC for UK researchers). I am happy to collaborate remotely on refinements or analysis.
3. **Improve it** — Suggestions for tighter error budgeting, better molecular Hamiltonians, or visualization of light-cone spreading are welcome.
4. **Spread the idea** — Share with quantum researchers in condensed-matter, quantum chemistry, or many-body physics who might have Willow access.

## License

This repository is released under the [MIT License](LICENSE) — free to use, modify, and submit to hardware programs with appropriate credit.

## Attribution & Contact

Created by: James Squire (independent researcher, Tasmania, Australia)  


If you run the experiment or submit a version of this proposal, please cite the original repository and let me know - I would love to see the results.

## Final Note

Credentials are a proxy, not the truth signal. The physics here is solid, the mapping elegant, the circuit feasible, and the impact clear. Open-sourcing maximizes the chance that someone with hardware access will actually execute it.

Let’s turn Willow from a supremacy machine into a scientific instrument together.

**Ready for QVM today. Ready for real hardware tomorrow.**

---

*Last updated: March 2026*
```

### How to Use This README
- Create a new GitHub repository (e.g., `willow-otoc-echo-proposal`).
- Paste the above into `README.md`.
- Add the original proposal file and Cirq code.
- Include a `LICENSE` file with MIT text.
- Optionally add a short `CONTRIBUTING.md` encouraging pull requests focused on QVM results or improvements.

This README is honest about the credential issue without bitterness, emphasizes first-principles reasoning, highlights the science, and actively invites collaboration and researchers to engage.

 
