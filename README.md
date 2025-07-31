# Machine Learning–Accelerated Discovery of Earth-Abundant Bimetallic Electrocatalysts for the Hydrogen Evolution Reaction

## Overview

This repository contains the computational data and results for the discovery of earth-abundant bimetallic HER electrocatalysts using machine learning and density functional theory.

**Key Achievement**: Identification of four synthesis-ready catalysts (Fe₂Sb₄, Cu₆Sb₂, Cu₆Sn₂, Ni₂Sb₂) with platinum-like performance at significantly lower cost.

## Methodology

- **Chemical Space**: 14 elements (Ir, Pt, Ru, Ni, Co, Fe, Mn, Ta, Ti, Nb, Mo, Cu, Sn, Sb)
- **ML Model**: EquiformerV2 within AdsorbML framework
- **DFT Validation**: VASP with RPBE functional
- **Screening Scale**: ~560,000 initial adsorption sites → 361 final candidates

## Data Files

### Core Results
- `361_slab_DFT_optimized_energy.csv` - Final 361 candidates after DFT optimization
- `500_slab_EqV2_SP_DFT.csv` - 500 configurations with ML and DFT validation
- `AllBulks.pkl` - All 439 bulk structures
- `ASCIrank.csv` - Activity-Stability-Cost Index rankings
- `EquiformerV2_H_ads_prediction.csv` - ML adsorption energy predictions
- `InDomainBulk.pkl` - In-domain bulk structures (OC20)
- `OutOfDomainBulk.pkl` - Out-of-domain bulk structures (reoptimized)

### Analysis Data
- `performance_comparison.csv` - Activity-Stability-Cost Index rankings

## Structure Files

### Compressed Archives (ZIP format)
- `MLrelaxedTrajMinHadsData.zip` - ML-relaxed trajectories and minimum H adsorption data
- `VASP_InputandOutputFiles.zip` - VASP input and output files for DFT calculations
- `VolcanoPlot-VASP_configurations.zip` - Structures used in volcano plot analysis
- `Out_Of_Domain_Vasp.zip` - VASP input and output files for fully optimized out-of-domain bulk systems

## File Formats

- **CSV files**: Comma-separated with headers, energies in eV
- **PKL files**: Python pickle format containing bulk structure data
- **ZIP files**: Compressed archives containing VASP structure files and trajectories

## Usage

Load data using standard tools:
```python
import pandas as pd
import pickle

# Load final candidates
candidates = pd.read_csv('data/361_slab_DFT_optimized_energy.csv')

# Load bulk structures
with open('data/AllBulks.pkl', 'rb') as f:
    bulks = pickle.load(f)
```

Structure files in ZIP archives are in VASP POSCAR format, compatible with ASE, pymatgen, VESTA.

## Notebooks

Analysis notebooks for data exploration and visualization:
- `demo_InDomain_H_ads.ipynb` - In-domain hydrogen adsorption analysis
- `SurfaceEnergy_ASCat_demo.ipynb` - Surface energy Calculations and Surface reconstruction detection
- `Material_Screening.ipynb` - Screens bimetallics and classifies them as in- or out-of-domain (OC20)

## Citation

If you use this dataset, structures, or analysis from our manuscript, please cite:

```bibtex
@article{oguz2025ml,
  title={Machine Learning–Accelerated Discovery of Earth-Abundant Bimetallic Electrocatalysts for the Hydrogen Evolution Reaction},
  author={Oguz, Ismail Can and Khossossi, Nabil and Brunacci, Marco and Bucak, Haldun and Er, Süleyman},
  journal={ChemRxiv},
  year={2025},
  doi={10.26434/chemrxiv-2025-0whpn},
  url={https://chemrxiv.org/engage/chemrxiv/article-details/6874f7ed23be8e43d62848a8}
}
```

**Preprint**: [Machine Learning–Accelerated Discovery of Earth-Abundant Bimetallic Electrocatalysts for the Hydrogen Evolution Reaction](https://chemrxiv.org/engage/chemrxiv/article-details/6874f7ed23be8e43d62848a8)

## Contact

**Corresponding Author**: Süleyman Er (s.er@differ.nl)  
DIFFER – Dutch Institute for Fundamental Energy Research
