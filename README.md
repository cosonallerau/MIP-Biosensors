# Atomistic Simulation Dataset: Molecularly Imprinted Polymer (MIP) Design for [Target Molecule Name]

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Open Science](https://img.shields.io/badge/Open%20Science-Pre--equilibrated%20Trajectories-success.svg)](#)

## Overview
This repository provides the complete, raw computational dataset used in the rational design of the electrochemical sensor detailed in our publication: **"[Insert Your Exact Paper Title Here]"**.

In the spirit of **Open Science**, we are releasing our high-resolution Density Functional Theory (DFT) outputs and fully equilibrated Molecular Dynamics (MD) trajectories. Researchers can directly utilize these pre-equilibrated `.xtd` and `.xsd` files to perform independent post-processing analyses, extract new physical properties, or use the relaxed structures as starting points for different computational setups, thereby saving significant computational time and resources.

## Value of this Dataset
* **Skip the Thermalization:** The NPT molecular dynamics trajectories provided here are already fully equilibrated at 298 K and 1 atm. You do not need to recalculate the volume relaxation.
* **Ready for Post-Processing:** You can directly import the trajectory files into BIOVIA Materials Studio (or convert them for LAMMPS/GROMACS) to compute MSD, diffusion coefficients, binding energies, or custom radial distribution functions.

## Dataset Structure

* **`/1_DFT_Optimization`**: 
  * Optimized geometries of the template and monomers.
  * Extracted HOMO/LUMO energies and Electrostatic Potential (ESP) grid data mapping interaction sites.
* **`/2_MD_Trajectories`**: 
  * The core of this repository. Contains the fully equilibrated `[Filename].xtd` trajectory files from the NPT ensemble simulations.
  * Forcefield used: COMPASS III.
* **`/3_Thermodynamic_Equilibration`**: 
  * CSV logs proving system stability (Density vs. Time, Potential Energy vs. Time).
* **`/4_RDF_Extraction`**: 
  * Raw coordinate data (Distance vs. g(r)) used to plot the specific non-covalent interactions (e.g., Hydrogen bonding, π-π stacking) discussed in the paper.

## Hardware and Methodology
To ensure high-fidelity thermodynamic equilibration without artificial constraints, all atomistic molecular dynamics simulations contained in this repository were accelerated using an **NVIDIA RTX 6000 Ada / Blackwell architecture GPU (96 GB VRAM)**. Integration time steps were kept strictly at 1.0 fs (or 0.1 fs during initial relaxation) to capture the finest interatomic collision dynamics.

## Usage and License
This dataset is published under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/). 

You are completely free to download, analyze, modify, and build upon this pre-equilibrated computational data for your own research (including commercial purposes). **The only requirement is to properly cite our original publication.**

## Citation Request
If you utilize these trajectories, DFT coordinates, or thermodynamic logs in your research, please cite:

> **[Your Name/Authors]** (2026). *[Paper Title]*. [Journal Name]. DOI: [Insert DOI when available]

## Contact
For inquiries regarding the computational protocols, forcefield specificities, or data conversion assistance, please open an issue in this repository.
