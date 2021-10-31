# Baseline


## Usage

### Train
Train the model by 4000 labeled data of CIFAR-10 dataset:

```
python train.py --dataset cifar10 --num-labeled 4000 --arch wideresnet --batch-size 64 --lr 0.03 --expand-labels --seed 5 --out results/cifar10@4000.5
```

Train the model by 10000 labeled data of CIFAR-100 dataset by using DistributedDataParallel:
```
python -m torch.distributed.launch --nproc_per_node 4 ./train.py --dataset cifar100 --num-labeled 10000 --arch wideresnet --batch-size 16 --lr 0.03 --wdecay 0.001 --expand-labels --seed 5 --out results/cifar100@10000
```

## References
- [Official TensorFlow implementation of FixMatch](https://github.com/google-research/fixmatch)
- [Unofficial PyTorch implementation of MixMatch](https://github.com/YU1ut/MixMatch-pytorch)
- [Unofficial PyTorch Reimplementation of RandAugment](https://github.com/ildoonet/pytorch-randaugment)
- [PyTorch image models](https://github.com/rwightman/pytorch-image-models)

## Citations
```
@article{sohn2020fixmatch,
    title={FixMatch: Simplifying Semi-Supervised Learning with Consistency and Confidence},
    author={Kihyuk Sohn and David Berthelot and Chun-Liang Li and Zizhao Zhang and Nicholas Carlini and Ekin D. Cubuk and Alex Kurakin and Han Zhang and Colin Raffel},
    journal={arXiv preprint arXiv:2001.07685},
    year={2020},
}
```