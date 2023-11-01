# TranSiGen
TranSiGen: Deep representation learning of chemical-induced transcriptional profile

#### Train model
```
python train_TranSiGen_full_data.py --data_path ../dataLINCS2020/processed_data_id.h5
                                    --molecule_path ../data/LINCS2020/idx2smi.pickle
                                    --molecule_feature KPGT
                                    --initialization_model pretrain_shRNA
                                    --split_data_type smiles_split
                                    --n_epochs 300
                                    --n_latent 100
                                    --molecule_feature_embed_dim [400]
                                    --batch_size 64
                                    --learning_rate 1e-3
                                    --beta 0.1
                                    --dropout 0.1
                                    --weight_decay 1e-5
                                    --train_flag True
                                    --eval_metric True

```

#### Infer profile
```
python prediction.py --model_path ../results/trained_models_164_cell_smiles_split/364039/feature_KPGT_init_pretrain_shRNA/best_model.pt
                     --data_path ../data/PRISM/screening_compound.csv
                     --molecule_feature_embed_path ../data/PRISM/KPGT_emb2304.pickle
                     --cell YAPC
                     --seed 100

```
