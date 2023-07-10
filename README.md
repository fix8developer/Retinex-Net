# RetinexNet

> This is a Tensorflow implement of RetinexNet
> Deep Retinex Decomposition for Low-Light Enhancement.

### Requirements

1. Python
2. Tensorflow >= 1.5.0
3. numpy, PIL

### Testing  Usage

- [X] To quickly test your own images with our model, just change the arguments in jupyter notebook cell (``7.2 - Testing the model``)

```shell
    --use_gpu=1 \                           # use gpu or not
    --gpu_idx=0 \
    --gpu_mem=0.5 \                         # gpu memory usage
    --phase=test \
    --test_dir=/path/to/your/test/dir/ \
    --save_dir=/path/to/save/results/ \
    --decom=0                               # save only enhanced results or together with decomposition results
```

The results will be saved under ``./test_results/``.

### Training Usage

First, download training data set from [google Drive](https://drive.google.com/file/d/157bjO1_cFuSd0HWDUuAmcHRJDVyWpOxB/view). Save training pairs of LOLdataset under `./data/our485/`, and synthetic pairs under `./data/syn/`.

- [X] Then, just change the arguments in jupyter notebook cell (``7.1 - Training the model``).

```shell
    --use_gpu=1 \                           # use gpu or not
    --gpu_idx=0 \
    --gpu_mem=0.5 \                         # gpu memory usage
    --phase=train \
    --epoch=100 \                           # number of training epoches
    --batch_size=16 \
    --patch_size=48 \                       # size of training patches
    --start_lr=0.001 \                      # initial learning rate for adm
    --eval_every_epoch=20 \                 # evaluate and save checkpoints for every # epoches
    --checkpoint_dir=./checkpoint           # if it is not existed, automatically make dirs
    --sample_dir=./sample                   # dir for saving evaluation results during training
```

#### Tips:
1. The model is quite small, so it will take just minutes to finish the training procedure if you are using GPU. For people who are using CPU, it is also affordable.
2. The enhancement performance is highly dependent on training parameters. So if you change the default parameters, you might get some weird results.

### Reference :rocket:
* [Research paper with code](https://daooshee.github.io/BMVC2018website/).
