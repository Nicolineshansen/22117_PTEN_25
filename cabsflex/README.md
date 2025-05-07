# CABSflex

## Generate ensemble models for flexibility

### Working directory
cd /home/projects/22117_proteins_2025/projects/Group3_project/PTEN/cabsflex

### Activate environment
- `conda deactivate`
- `source /home/ctools/CABS/bin/activate`

### Create output directories
- `mkdir wildtype`
- `mkdir C124F`
- `mkdir F347Y`
- `mkdir Q171E`
- `mkdir R130G`

### Run CABSflex  - use nohub to run in the background
- `cd wildtype`
    - `nohup CABSflex -i ../../structures/AF_truncated.pdb -k 10 -y 30 -a 10 -v 3 -z 10 -A &`
- `cd C124F`
   - `nohup CABSflex -i ../../structures/AF_truncated_C124F.pdb -k 10 -y 30 -a 10 -v 3 -z 10 -A &`
- `cd F347Y`
   - `nohup CABSflex -i ../../structures/AF_truncated_F347Y.pdb -k 10 -y 30 -a 10 -v 3 -z 10 -A &`
- `cd Q171E`
   - `nohup CABSflex -i ../../structures/AF_truncated_Q171E.pdb -k 10 -y 30 -a 10 -v 3 -z 10 -A &`
- `cd R130G`
   - `nohup CABSflex -i ../../structures/AF_truncated_R130G.pdb -k 10 -y 30 -a 10 -v 3 -z 10 -A &`

#### (Optional) check status of MutateX calculations
- `tail -f nohup.out`
