# A Fourier-based Semantic Augmentation for Visible-Thermal Person Re-Identification 

Pytorch Code of FSA method for Cross-Modality Person Re-Identification (Visible Thermal Re-ID) on RegDB dataset and SYSU-MM01 dataset.

### Results
Dataset | Rank1  | mAP 
 ---- | ----- | ------  
 RegDB | ~87.23% | ~80.70%  
 SYSU-MM01  | ~73.63% | ~69.25% 

### Usage

Our code extends the pytorch implementation of Cross-Modal-Re-ID-baseline in [Github](https://github.com/mangye16/Cross-Modal-Re-ID-baseline). Please refer to the offical repo for details of data preparation.

###  Training

Train a model by
```bash
python train_ext.py --dataset sysu --lr 0.1 --batch-size 6 --num_pos 4 --fsa_method FSA --lam 0.8 --gpu 0
```

- `--dataset`: which dataset "sysu" or "regdb".

- `--lr`: initial learning rate.

- `--gpu`:  which gpu to run.
  
- `--fsa_method`: which semantic augmentation method to use.


###  Testing

Test a model on SYSU-MM01 or RegDB dataset by using testing augmentation with HorizontalFlip
```bash
python testa.py --mode all --resume 'model_path' --gpu 0 --dataset sysu
```
- `--dataset`: which dataset "sysu" or "regdb".

- `--mode`: "all" or "indoor" all search or indoor search (only for sysu dataset).

- `--trial`: testing trial (only for RegDB dataset).

- `--resume`: the saved model path.

- `--gpu`:  which gpu to run.


###  Citation

Please kindly cite the following paper in your publications if it helps your research:
```
@article{liu2020parameter,
  title={Parameter sharing exploration and hetero-center triplet loss for visible-thermal person re-identification},
  author={Liu, Haijun and Tan, Xiaoheng and Zhou, Xichuan},
  journal={IEEE Transactions on Multimedia},
  volume={23},
  pages={4414--4425},
  year={2020},
  publisher={IEEE}
}
```
```
@article{liu2021strong,
  title={Strong but simple baseline with dual-granularity triplet loss for visible-thermal person re-identification},
  author={Liu, Haijun and Chai, Yanxia and Tan, Xiaoheng and Li, Dong and Zhou, Xichuan},
  journal={IEEE Signal Processing Letters},
  volume={28},
  pages={653--657},
  year={2021},
  publisher={IEEE}
}
```
```
@article{Tan2022AFS,
  title={A Fourier-Based Semantic Augmentation for Visible-Thermal Person Re-Identification},
  author={Xiaoheng Tan and Yanxia Chai and Fenglei Chen and Haijun Liu},
  journal={IEEE Signal Processing Letters},
  year={2022},
  volume={29},
  pages={1684-1688}
}
```

