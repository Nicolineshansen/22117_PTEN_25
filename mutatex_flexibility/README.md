# MutateX self-scan



### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_selfscan`

- 


- `nohup mutatex wildtype_models/model_0.pdb -p 4 -x /home/ctools/foldx/foldx -m mutation_list.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v -s &`

# MutateX ensemble

## Calculate effects of mutations on stability with MutateX

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_ensemble`

### Create input file directory
- `mkdir wildtype_models`

### Get models from cabsflex
- `cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/wildtype/output_pdbs/model_*.pdb ./wildtype_models`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`


### Activcate environment ###
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Create output directories
- `mkdir wildtype`

### Create poslist file
cat 

### Run MutateX  - use nohub to run in the background


- wildtype
  - `cd wildtype`
  - `nohup mutatex ../wildtype_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`
- C124F mutation
  - `cd C124F`
  - `nohup mutatex ../C124F_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`
- F347Y mutation
  - `cd F347Y`
  - `nohup mutatex ../F347Y_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`
- Q171E mutation
  - `cd Q171E`
  - `nohup mutatex ../Q171E_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`
- R130G mutation
  - `cd R130G`
  - `nohup mutatex ../R130G_models/model_*.pdb -p 4 -x /home/ctools/foldx/foldx -m ../mutation_list.txt -q ../poslist.txt -f suite5 -R ../repair_runfile_template.txt -M ../mutate_runfile_template.txt -c -L -l -v  &`

#### (Optional) check status of MutateX calculations
- `tail -f nohup.out`
