# EvoClustRNA  
A clustering routines of evolutionary conserved regions (helical regions) for RNA fold prediction.  

## test_run.sh 

```
# evoClustRNA clustering procedure  
evoClustRNA.py -a rp13finalX_noSSperSeq_ref.sto -o out/ -i ~/EvoClustRNA/test_data/rp13/evox/structures -m mapping_ref.txt -f  
# *.matrix was created which took almost 10 mins  

# cluster the matrix
evoClust_autoclustix.py  rp13finalX_noSSperSeq_ref_mapping_refX.matrix  
# rp13finalX_noSSperSeq_ref_mapping_refX_n1c166_cf9.00.out was created  

# copy the best cluster medoids from structures to reps_ns  
evoClust_get_models.py -i evox/structures/ *.out -n tar -u  
# rep_ns/ and reps_motifs_ns(empty) were created.  

# compare to the reference structure  
evoClust_calc_rmsd.py -a rp13finalX_noSSperSeq_ref.sto -t target_13_solution_0_renumber_puzzle_ref.pdb -m mapping_ref.txt -o rmsd_motif.    csv -n rp13 reps_ns/*.pdb  
# rmsd_motif.csv and rmsd_motif.png were created.  
```


