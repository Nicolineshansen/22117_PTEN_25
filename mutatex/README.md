# MutateX

## MutateX 5BZZ

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutateX_stability_3`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

### Create poslist file
- `nano poslist.txt`
  - **poslist file should contain:**\
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

### Activate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Run MutateX - use nohub to run in the background
- `nohup mutatex 5BZZ_noHETATM_chainA.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`

### (Optional) check status of MutateX calculations
- `tail -f nohup.out`


## MutateX AF structure

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_stability_af`

### Get AlphaFold structure
- `cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/structures/AF_truncated.pdb .`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

### Create poslist file
- `nano poslist.txt`
  - **poslist file should contain:**\
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

### Activate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Run MutateX - use nohub to run in the background
- `nohup mutatex AF_truncated.pdb -p 3 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`

### (Optional) check status of MutateX calculations
- `tail -f nohup.out`
