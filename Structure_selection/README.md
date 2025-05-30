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

### Copy the csv file to your computer 
