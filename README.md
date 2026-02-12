# Analytical Models for Anisotropic Plasmon Polaritons in MoOCl₂

Code accompanying the manuscript:

**"Spatiotemporal Visualization of Long-Range Anisotropic Plasmon Polaritons in Hyperbolic MoOCl₂"**

Atreyie Ghosh, Calvin Raab, Joseph L. Spellberg, Aishani Mohan, Muneeza Munawar, Janek Rieger, and Sarah B. King*

James Franck Institute and Department of Chemistry, The University of Chicago

## Overview

This repository contains the Python code used for analytical electromagnetic calculations in the manuscript. The calculations model plasmon polariton modes in MoOCl₂ thin films using biaxial electromagnetic theory and the transfer matrix method.

## Notebooks

| Notebook | Description | Manuscript Figures |
|----------|-------------|-------------------|
| `Polarization_and_Isofrequency.ipynb` | Booker quartic solver for biaxial k_z, polarization maps, and isofrequency contour (IFC) calculations | Main Fig. 2B–F; SI Fig. S2 |
| `semi_infinite_rpp.ipynb` | Biaxial Fresnel reflection coefficient r_pp(k_x, k_y) for a semi-infinite MoOCl₂/vacuum interface | SI Fig. S4 |
| `Vacuum_MoOCl2_SiO2_Si.ipynb` | Four-layer transfer matrix model (vacuum/MoOCl₂/SiO₂/Si), dispersion calculation, electric field and Poynting vector distributions, group/phase velocity analysis | Main Fig. 3A–E; SI Figs. S3, S5, S9 |

## Directory Structure

```
├── README.md
├── Polarization_and_Isofrequency.ipynb
├── semi_infinite_rpp.ipynb
├── Vacuum_MoOCl2_SiO2_Si.ipynb
└── LiteratureDielectrics/
    ├── MoOCl2/ (Zhao et al. 2020, DFT)
    │   ├── Re X.csv          # ε_x real part
    │   ├── Im X.csv          # ε_x imaginary part
    │   ├── Re Y.csv          # ε_y real part
    │   ├── Im Y.csv          # ε_y imaginary part
    │   ├── Re Z.csv          # ε_z real part
    │   └── Im Z.csv          # ε_z imaginary part
    └── Si_SiO2/
        ├── SiO2.txt           # SiO₂ optical constants (SOPRA database)
        └── Si100.txt          # Si(100) optical constants (SOPRA database)
```

## Dielectric Function Sources

- **MoOCl₂ ε_x(ω), ε_y(ω):**    Drude–Lorentz parametrization from N. Melchioni, A. Mancini, L. Nan, A. Efimova, G. Venturi, A. Ambrosio, Giant Optical Anisotropy in a Natural van der Waals Hyperbolic Crystal for Visible Light Low-Loss Polarization Control. ACS Nano 19, 25413–25421 (2025).
                                Parameters are hardcoded in the `melchioni_dielectric()` function.
- **MoOCl₂ ε_z(ω):**            DFT calculations from J. Zhao, W. Wu, J. Zhu, Y. Lu, B. Xiang, S. A. Yang, Highly anisotropic two-dimensional metal in monolayer MoOCl2. Phys. Rev. B 102, 245419 (2020).
                                Provided as CSV files in `LiteratureDielectrics/MoOCl2/`. The X and Y directions are also included for comparison purposes.
- **SiO₂, Si(100):**            SOPRA optical constants database (https://www.sspectra.com/sopra.html).

## Requirements

```
numpy
matplotlib
scipy
pandas
```

## Units

All calculations use a consistent unit system:
- **Energy:** eV
- **Wavevector:** μm⁻¹
- **Length:** μm
- **Speed of light:** c = ħc = 0.197 eV·μm

## Data Availability

Experimental data displayed in the manuscript is available on Zenodo: https://zenodo.org/10.5281/zenodo.15685600

## License

MIT License

