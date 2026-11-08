# Quantum Dynamics — Numerical Simulations

A one-dimensional numerical study of quantum dynamics, from stationary states to wave-packet propagation and nonlinear Josephson dynamics. This project was developed as an undergraduate (Licence 3) numerical-physics project at Sorbonne Université. **AI was used to create this github repository and to translate the notebook from french to english (note that all the functions name and figures legend in the notebook are still in french)**
## Topics covered

- **Stationary Schrödinger equation:** finite-difference discretization and tridiagonal Hamiltonian diagonalization.
- **Analytical benchmarks:** infinite square well and harmonic oscillator.
- **Time propagation:** explicit Euler and fourth-order Runge–Kutta (RK4), including a comparison of their stability and norm conservation.
- **Wave-packet dynamics:** reflection in an infinite well, two-packet interference, and harmonic motion.
- **Scattering:** reflection and transmission of a Gaussian packet at a potential barrier.
- **Nonlinear dynamics:** Gross–Pitaevskii equation in a double-well potential and Josephson oscillations / macroscopic self-trapping.

## Repository structure

```text
quantum-dynamics/
├── README.md
├── requirements.txt
├── LICENSE
├── notebooks/
│   └── quantum_dynamics.ipynb
└── figures/
    ├── gaussian_packet_infinite_well.gif
    ├── two_packet_interference.gif
    ├── gaussian_packet_harmonic.gif
    ├── potential_barrier_scattering.gif
    ├── josephson_no_interaction.gif
    └── josephson_self_trapping.gif
```

## Getting started

Python 3.10 or later is recommended. Clone the repository and install the dependencies:

```bash
git clone https://github.com/<your-username>/quantum-dynamics.git
cd quantum-dynamics
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
pip install -r requirements.txt
jupyter lab
```

Then open `notebooks/quantum_dynamics.ipynb`.

## Numerical methods

The spatial second derivative is approximated with a second-order central finite difference. The stationary Hamiltonian is a real symmetric tridiagonal matrix, diagonalized with `scipy.linalg.eigh_tridiagonal`. Time evolution is compared using explicit Euler and classical fourth-order Runge–Kutta. The nonlinear double-well model is propagated with an RK4 implementation of the Gross–Pitaevskii equation.

The project uses dimensionless units with $\hbar = 1$ and $\hbar^2/(2m)=1$.

## Selected animations

| Simulation | Animation |
|---|---|
| Gaussian packet in an infinite square well | `figures/gaussian_packet_infinite_well.gif` |
| Two-packet interference | `figures/two_packet_interference.gif` |
| Harmonic potential | `figures/gaussian_packet_harmonic.gif` |
| Potential-barrier scattering | `figures/potential_barrier_scattering.gif` |
| Josephson dynamics without interactions | `figures/josephson_no_interaction.gif` |
| Josephson self-trapping | `figures/josephson_self_trapping.gif` |

## Notes and limitations

This repository preserves the original undergraduate implementation and its numerical choices. In particular, RK4 is not exactly unitary, the finite spatial domain imposes hard-wall boundary conditions, and the model is one-dimensional. The notebook discusses discretization errors and the limitations of the simulations. 

**Reproducibility note:** the notebook contains saved static plots from the original run. Interactive HTML animation outputs have been removed to keep the notebook lightweight; the corresponding animations are provided separately in `figures/`.


## Author

Oscar Fourreau — M1 Fundamental Physics Student at Sorbonne Université.
