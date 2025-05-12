# Docking
## Docking of PTEN mutations and PIP3

### Preparation of ligand file
Download .sdf file from this link: https://pubchem.ncbi.nlm.nih.gov/compound/11029524
Export the structure to .mol2 format

### Preparation of mutated PTEN structures
Use the mutagenesis function to mutate the specific residues in the protein and save the file as .pdb format

### Docking using SwissDock server
Go to this website: https://www.swissdock.ch/
Select the 'Docking with AutoDock Vina' module
Upload the ligand file and prepare
Upload the target file and prepare

#### Defining the search space
Use these settings for the 'Search box center': -17, -38, 12 Å
And these settings for the 'Search box size': 9, 11, 11 Å

#### Sample exhaustivity
Set the sample exhaustivity to 1
Start the docking
