# Steroid Identification via Substructure Search  

This repository provides a tool for identifying steroids from a list of small molecules using substructure search techniques. It analyzes molecular structures by interpreting their SMILES strings to determine whether a compound qualifies as a steroid based on specific structural criteria.  

## Criteria for Identification  

The following substructure is considered defining features of steroids:

<img src="https://github.com/ZinniaMa/steroid_search/blob/main/pngs/substructure.png" alt="Substructure" width="200">


## Implementation Details  

We utilize the **RDKit** library to process chemical structures. The input for each compound is its SMILES string, which RDKit reads as a `mol` object. The following preprocessing steps are applied before performing the substructure search:  

1. **Aromatic Ring Conversion:** Convert benzene rings to non-aromatic rings.  
2. **Heteroatom Replacement:** Replace heteroatoms (N, O, S) in heterocycles with carbon atoms.  
3. **Bond Type Conversion:** Convert all bonds to single bonds.

After preprocessing, the modified `mol` object is checked for the presence of specified steroid-like substructures. The implementation details can be found in the **`checksubstructures.ipynb`** notebook.  
