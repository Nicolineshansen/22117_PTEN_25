# MutateX

## MutateX 5BZZ (crystal structure)

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutateX_stability_3`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

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


### Activate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Run NACCESS
- `naccess 5BZZ_noHETATM_chainA.pdb`

#### Get output for NACCESS
- `grep 130 5BZZ_noHETATM_chainA.rsa`
- `grep 214 5BZZ_noHETATM_chainA.rsa`
- `grep 124 5BZZ_noHETATM_chainA.rsa`
- `grep 275 5BZZ_noHETATM_chainA.rsa`
- `grep 171 5BZZ_noHETATM_chainA.rsa`
- `grep 198 5BZZ_noHETATM_chainA.rsa`
- `grep 59 5BZZ_noHETATM_chainA.rsa`
- `grep 347 5BZZ_noHETATM_chainA.rsa`
- `grep 78 5BZZ_noHETATM_chainA.rsa`
- `grep 278 5BZZ_noHETATM_chainA.rsa`
- `grep 173 5BZZ_noHETATM_chainA.rsa`
- `grep 255 5BZZ_noHETATM_chainA.rsa`

### Run MutateX - use nohub to run in the background
- `nohup mutatex 5BZZ_noHETATM_chainA.pdb -p 4 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`

### (Optional) check status of MutateX calculations
- `tail -f nohup.out`


## MutateX AlphaFold structure

### Go to working directory
- `cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/mutatex_stability_af`

### Get AlphaFold structure
- `cp /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/structures/AF_truncated.pdb .`

### Get template files for MutateX
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutation_list.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/repair_runfile_template.txt .`
- `cp /home/projects/22117_proteins_2025/lecture4/mutatex_templates/mutatex/templates/foldxsuite5/mutate_runfile_template.txt .`

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

### Activate environment
- `conda deactivate`
- `conda activate /home/ctools/protein_structure_course/`

### Run NACCESS
- `naccess AF_truncated.pdb`

#### Get output for NACCESS
- `grep 130 AF_truncated.rsa`
- `grep 214 AF_truncated.rsa`
- `grep 124 AF_truncated.rsa`
- `grep 275 AF_truncated.rsa`
- `grep 171 AF_truncated.rsa`
- `grep 198 AF_truncated.rsa`
- `grep 59 AF_truncated.rsa`
- `grep 347 AF_truncated.rsa`
- `grep 78 AF_truncated.rsa`
- `grep 278 AF_truncated.rsa`
- `grep 173 AF_truncated.rsa`
- `grep 255 AF_truncated.rsa`

### Run MutateX - use nohub to run in the background
- `nohup mutatex AF_truncated.pdb -p 4 -x /home/ctools/foldx/foldx -m mutation_list.txt -q poslist.txt -f suite5 -R repair_runfile_template.txt -M mutate_runfile_template.txt -c -L -l -v  &`

### (Optional) check status of MutateX calculations
- `tail -f nohup.out`
