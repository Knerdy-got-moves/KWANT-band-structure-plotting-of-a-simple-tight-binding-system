# KWANT Band Structure Plotting of Simple Tight-Binding Systems

A computational physics project for simulating and visualizing electronic band structures, effective mass, and density of states (DOS) in tight-binding models using the KWANT Python library.

## Overview

This project implements quantum transport simulations for two fundamental condensed matter physics systems:

1. **1D Tight-Binding Wire** - A simple one-dimensional quantum wire
2. **2D Honeycomb Lattice** - A graphene-like structure exhibiting Dirac physics

The simulations calculate and visualize:
- Electronic band structures
- Effective mass dispersion
- Density of states (DOS)
- Band gap characteristics

## Physics Background

### Tight-Binding Models

Tight-binding models are essential tools in condensed matter physics for describing electronic structures in crystalline materials. They use the Linear Combination of Atomic Orbitals (LCAO) principle to model electron hopping between adjacent lattice sites.

Key concepts explored:
- **Bloch's Theorem**: Describes wavefunctions in periodic potentials
- **Effective Mass**: Quantifies how electrons respond to external forces in a crystal
- **Density of States**: Number of available electron states per unit energy
- **Dirac Points**: Special points in momentum space where bands touch (honeycomb lattice)

### Applications

These models are fundamental to understanding:
- Graphene and 2D materials
- Topological insulators
- Quantum Hall effects (Anomalous and Spin Quantum Hall Effects)
- Electronic transport in nanoscale systems

## Requirements

### Python Dependencies

```bash
kwant
numpy
matplotlib
scipy
```

### Installation

```bash
pip install kwant numpy matplotlib scipy
```

Or using conda:

```bash
conda install -c conda-forge kwant numpy matplotlib scipy
```

## Project Structure

```
.
├── Code for bandstructure and bandstructure related calculations of Simple 1D tight-binding wire
├── Code for 2D plot of kx, ky in a 2D Honeycomb lattice, its DOS and its effective mass, and its band gap
├── Code for 3D plot of Dirac band-structure of 2D Honeycomb lattice
├── Band_structure_of_a_simple_tight_binding_model/
│   ├── main.tex                    # LaTeX source with detailed theory
│   ├── *.png                       # Generated plots
│   └── ...
├── KWANT_band_structure_plotting_of_a_simple_tight_binding_system.pdf
└── README.md
```

## Usage

### 1D Tight-Binding Wire

Simulates a simple 1D quantum wire with nearest-neighbor hopping.

```bash
python "Code for bandstructure and bandstructure related calculations of Simple 1D tight-binding wire"
```

**Outputs:**
- Band structure plot: Energy vs. momentum
- Effective mass plot: m* vs. momentum
- Density of states plot

**Physics Parameters:**
- Lattice constant: `a = 1`
- Hopping parameter: `t = 1.0`
- Wire width: `W = 10` sites

### 2D Honeycomb Lattice (2D Plots)

Generates 2D band structure plots for a honeycomb lattice along kx and ky directions.

```bash
python "Code for 2D plot of kx, ky in a 2D Honeycomb lattice, its DOS and its effective mass, and its band gap"
```

**Outputs:**
- Honeycomb lattice visualization
- Band structure: E vs. kx
- Band structure: E vs. ky
- Effective mass: m* vs. kx
- Effective mass: m* vs. ky
- Density of states
- **Band gap calculation** (numerical verification of ~0 gap for graphene)

**Key Results:**
- Maximum energy difference in middle bands
- Maximum energy difference in other bands
- Band gap: ~2.96×10⁻¹⁶ (numerically zero, confirming gapless Dirac physics)

### 2D Honeycomb Lattice (3D Visualization)

Creates a 3D surface plot of the Dirac cone band structure.

```bash
python "Code for 3D plot of Dirac band-structure of 2D Honeycomb lattice"
```

**Outputs:**
- 3D band structure surface plot showing the characteristic Dirac cones
- Axes: kx, ky (momentum space) and E (energy)

## Theory

### 1D Wire Dispersion Relation

For a 1D tight-binding wire with on-site energy E₀ and hopping parameter t:

```
E(k) = E₀ - 2t cos(ka)
```

### Honeycomb Lattice Dispersion

For a honeycomb lattice with sublattices A and B:

```
E±(k) = ± √[3 + 2cos(√3 kx a) + 4cos(√3 kx a/2)cos(3 ky a/2)]
```

The ± gives the conduction and valence bands which touch at the K and K' points (Dirac points).

### Effective Mass

The effective mass is calculated from the band curvature:

```
m* = ℏ² (∂²E/∂k²)⁻¹
```

Implemented numerically using a central difference scheme with step size h = 0.01.

## Key Features

- **Accurate Physics**: Implements proper tight-binding Hamiltonians
- **Visualization**: Clear matplotlib plots for all quantities
- **Numerical Methods**: Central difference for derivatives, KPM for DOS
- **Flexibility**: Easy to modify lattice parameters and system size
- **Educational**: Well-commented code suitable for learning

## Results and Visualizations

The project generates multiple plots saved in the `Band_structure_of_a_simple_tight_binding_model/` directory:

| Plot | Description |
|------|-------------|
| `simple BS tight binding wire.png` | 1D wire band structure |
| `1D Wire Effective mass.png` | Effective mass for 1D wire |
| `1D DOS.png` | Density of states for 1D wire |
| `HC Lattice.png` | Honeycomb lattice structure |
| `X dirn HC BS.png` | Honeycomb bands along kx |
| `Y dir HC BS.png` | Honeycomb bands along ky |
| `HC 3D BSplot.png` | 3D Dirac cone visualization |
| `Eff Mass HC x.png` | Effective mass along kx |
| `Eff Mass HC y.png` | Effective mass along ky |
| `DOS HC.png` | Honeycomb lattice DOS |

## Documentation

A comprehensive PDF report (`KWANT_band_structure_plotting_of_a_simple_tight_binding_system.pdf`) is included, containing:

- Detailed theoretical derivations
- LCAO method explanation
- Bloch theorem application
- Step-by-step calculation methods
- Analysis of all results
- Complete bibliography

## References

1. **KWANT**: Groth, C. W., Wimmer, M., Akhmerov, A. R., & Waintal, X. (2014). *Kwant: a software package for quantum transport*. New Journal of Physics, 16(6), 063065.

2. **Haldane Model**: Haldane, F. D. M. (1988). *Model for a Quantum Hall Effect without Landau Levels*. Physical Review Letters, 61(18), 2015.

3. **SSH Model**: Su, W. P., Schrieffer, J. R., & Heeger, A. J. (1979). *Solitons in Polyacetylene*. Physical Review Letters, 42(25), 1698-1701.

4. **Honeycomb Lattice**: Fan, R., Sun, L., Shao, X., Li, Y., & Zhao, M. (2023). *Two-dimensional Dirac materials: Tight-binding lattice models and material candidates*. ChemPhysMater, 2(1), 30-42.

## Author

**Rishi Paresh Joshi**
Student ID: 2111093
National Institute of Science Education and Research (NISER), Bhubaneswar
November 2023

## License

This project is provided for educational and research purposes.

## Acknowledgments

- KWANT development team for the excellent quantum transport library
- NISER, Bhubaneswar for academic support
- Open Solid State Notes and various textbooks referenced in the theory

## Links

- [KWANT Official Documentation](https://kwant-project.org/doc/1/)
- [KWANT GitHub Repository](https://github.com/kwant-project)
- [Bloch's Theorem - Wikipedia](https://en.wikipedia.org/wiki/Bloch's_theorem)

---

*For detailed theoretical background, derivations, and analysis, please refer to the included PDF documentation.*
