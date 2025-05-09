# MutateX self-scan



### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_selfscan`

### Create input file directory
- `mkdir wildtype_models`
  
### Get models from cabsflex
- `cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/wildtype/output_pdbs/model_*.pdb ./wildtype_models`

### Activcate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

### Create output directories
- `mkdir wildtype`

### Run MutateX  - use nohub to run in the background
MutateX is run without a poslist, as we want to scan the whole protein
- `nohup mutatex wildtype_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m mutation_list.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v -s &`

#### (Optional) check status of MutateX calculations
- `tail -f nohup.out`

# MutateX ensemble

## Calculate effects of mutations on stability with MutateX

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_ensemble`

### Create input file directory
- `mkdir wildtype_models`

### Get models from cabsflex
- `cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/wildtype/output_pdbs/model_*.pdb ./wildtype_models`

### Activcate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

### Create output directories
- `mkdir wildtype`

### Create poslist file
- `cat > poslist_2.txt`\
  RA130\
  QA214\
  CA124\
  VA275\
  QA171\
  MA198\
  SA59\
  FA347\
  TA78\
  FA278\
  RA173\
  VA255

### Run MutateX  - use nohub to run in the background


- wildtype
  - `cd wildtype`
  - `nohup mutatex ../wildtype_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`

#### (Optional) check status of MutateX calculations
- `tail -f nohup.out`
