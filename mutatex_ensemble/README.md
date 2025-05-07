# MutateX ensemble

## Calculate effects of mutations on stability with MutateX

- go to working directory
`cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_ensemble`

- create input file directories
  `mkdir wildtype_models`
  `mkdir C124F_models`
  `mkdir F347Y_models`
  `mkdir Q171E_models`
  `mkdir R130G_models`

- get models from cabsflex
`cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/wildtype/output_pdbs/output_pdbs/model_*.pdb ./wildtype_models`
`cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/C124F/output_pdbs/output_pdbs/model_*.pdb ./C124F_models`
`cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/F347Y/output_pdbs/output_pdbs/model_*.pdb ./F347Y_models`
`cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/Q171E/output_pdbs/output_pdbs/model_*.pdb ./Q171E_models`
`cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex/R130G/output_pdbs/output_pdbs/model_*.pdb ./R130G_models`

- get template files for mMtateX
`cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
`cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
`cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

### Activcate environment ###
`conda deactivate`
`conda activate /home/ctools/protein_structure_course/`

### Run MutateX - use nohub to run in the background
- wildtype
`nohup mutatex wildtype_models/model_*.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`
- C124F mutation
`nohup mutatex C124F_models/model_*.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`
- F347Y mutation
`nohup mutatex F347Y_models/model_*.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`
- Q171E mutation
`nohup mutatex Q171E_models/model_*.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`
- R130G mutation
`nohup mutatex R130G_models/model_*.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`

#### (Optional) check status of MutateX calculations
`tail -f nohup.out`
