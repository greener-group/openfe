# Alchemical free energy calculations with custom potentials in OpenFE

This is a fork of Open Free Energy's `openfe` package, which we have modified to calculate relative binding free energies (RBFEs) with our Garnet force field. 

## Introduction

Garnet is a graph neural network that assigns force field parameters for diverse molecules, incl. proteins and small molecules, using continuous atom typing [1]. We have shown that the Garnet force field can be used to estimate relative binding free energies (RBFEs) with alchemical free energy calculations [1].

We have modified the `openfe` RBFE protocol to be Garnet-compatible. Our adaption follows OpenFE’s RBFE protocol closely, but substitutes the Lennard-Jones potential and the Gapsys soft-core potential with a double exponential potential and a related soft-core potential. These modifications are necessary, since Garnet was trained to predict force field parameters for the double exponential potential. 

OpenFE’s RFBE protocol can be run by following a few steps and requires minimal user intervention, aside from protein and ligand structure preparation. We provide instructions for running RBFE calculations with Garnet using our `openfe` fork at: 
https://github.com/greener-group/garnet/tree/main/validation/rbfe/README.md

We refer to the OpenFE GitHub [2], documentation [3] and Industry Benchmarking Project paper [4,5] for details on the code and its execution. 

## Installation

```
git clone https://github.com/greener-group/openfe.git
cd openfe
conda env create -f environment.yml
conda activate openfe_garnet
python -m pip install --no-deps .
```

## Notes

- We are currently running `openfe-v1.8.0`.
- You should be using the code on the branch `custom_potentials`, which is the default.

## References

1. Garnet paper: Blanco-González, Schulze, Rovers, Greener. Training a force field for proteins and small molecules from scratch. arXiv. 2026. DOI: https://doi.org/10.48550/arXiv.2603.16770

2. OpenFE GitHub: https://github.com/OpenFreeEnergy/openfe

3. OpenFE documentation: https://docs.openfree.energy/en/latest/

4. OpenFE Industry Benchmarking Project paper: Baumann, Horton, Henry, et al. Large-scale collaborative assessment of binding free energy calculations for drug discovery using OpenFE. ChemRxiv. 18 December 2025. DOI: https://doi.org/10.26434/chemrxiv-2025-7sthd

5. OpenFE Industry Benchmarking Project GitHub: OpenFE Industry Benchmarking Project Github: https://github.com/OpenFreeEnergy/IndustryBenchmarks2024