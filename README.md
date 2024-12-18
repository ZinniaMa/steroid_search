# Steroid Identification via Substructure Search  

This repository provides a tool for identifying steroids from a list of small molecules using substructure search techniques. It analyzes molecular structures by interpreting their SMILES strings to determine whether a compound qualifies as a steroid based on specific structural criteria.  

> **Note:** This repository currently uses the [**Rhea dataset**](https://www.rhea-db.org/) as an example for demonstration purposes.  


## Criteria for Identification  

The following substructure is considered defining features of steroids:

<img src="https://github.com/ZinniaMa/steroid_search/blob/main/pngs/substructure.png" alt="Substructure" width="200">


## Core Idea  

Given the challenge of enumerating all possible steroid backbone structures, we simplify the target compounds by reducing them to their core features. The simplification process removes less relevant structural details, revealing the essential **four-ring structure** characteristic of steroids. This approach enables more robust and efficient substructure-based identification.  


## Implementation Details  

We utilize the **RDKit** library to process chemical structures. The input for each compound is its SMILES string, which RDKit reads as a `mol` object. The following preprocessing steps are applied before performing the substructure search:  

1. **Aromatic Ring Conversion:** Convert benzene rings to non-aromatic rings.  
2. **Heteroatom Replacement:** Replace heteroatoms (N, O, S) in heterocycles with carbon atoms.  
3. **Bond Type Conversion:** Convert all bonds to single bonds.

After preprocessing, the modified `mol` object is checked for the presence of specified steroid-like substructures. The implementation details can be found in the [**`checksubstructures.ipynb`**](https://github.com/ZinniaMa/steroid_search/blob/main/checksubstructures.ipynb) notebook.  
