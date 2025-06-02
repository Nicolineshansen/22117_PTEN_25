# Structure selection

## PDBminer is used to extract all structures of human PTEN from PDB and AlphaFoldDB.

### Working directory
`cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN`

### Activate environment
- `conda deactivate`
- `source /home/ctools/CABS/bin/activate`

### Make directory
- `mkdir structure_selection`

### Run PDBminer
#### "nohup" is used to run PDBminer in the background. The uniprot accession code of human PTEN is P60484, which is used in the command.
- `cd structure_selection`
- `nohup PDBminer -u P60484 -n 2 -f csv &`

### Selection criteria
#### Filter away all structures solved by NMR (column G = Solution NMR) and all structures in complex with other proteins (column L = "protein complex"). Choose the structure with the combination of the lowest resolution and lowest R-free, which in this case is PDB structure 5BZZ.
