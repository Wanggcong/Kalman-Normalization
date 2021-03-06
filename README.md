# Kalman Normalization

By [Guangrun Wang](https://wanggrun.github.io/), [Jiefeng Peng](http://www.sysu-hcp.net/people/), [Ping Luo](http://personal.ie.cuhk.edu.hk/~pluo/), Xinjiang Wang and [Liang Lin](http://www.linliang.net/).

Sun Yat-sen University (SYSU), the Chinese University of Hong Kong (CUHK), SenseTime Group Ltd.

### Table of Contents
0. [Results](#results)
0. [Introduction](#introduction)
0. [Citation](#citation)
0. [Dependencies](#dependencies)
0. [Usage](#usage)


### Results
+ Under the context of micro-batches(batch size = 2), the validataion curves on CIFAR10:

top line: [Batch Normalization(BN)](https://arxiv.org/abs/1502.03167); mid line: [Group Normalization](https://arxiv.org/abs/1803.08494); bottom line: [Kalman Normalization](https://arxiv.org/abs/1802.03133)
        ![Training curves](https://github.com/wanggrun/Kalman-Normalization/blob/master/results/bn_gn_bkn_micro_batch.png)

+ Under the context of large-batches(batch size = 128), the validataion curves on CIFAR10:

top line: [Batch Normalization(BN)](https://arxiv.org/abs/1502.03167); bottom line: [Kalman Normalization](https://arxiv.org/abs/1802.03133))
        ![Training curves](https://github.com/wanggrun/Kalman-Normalization/blob/master/results/bkn_bn_large_batch.png)


### Introduction

This repository contains the original models described in the paper "Batch Kalman Normalization: Towards Training Deep Neural Networks with Micro-Batches" (https://arxiv.org/abs/1802.03133). These models are those used in [ILSVRC](http://image-net.org/challenges/LSVRC/2015/) and [CIFAR](https://www.cs.toronto.edu/~kriz/cifar.html) 



### Citation

If you use these models in your research, please cite:

	@article{wang2018batch,
		title={Batch Kalman Normalization: Towards Training Deep Neural Networks with Micro-Batches},
  		author={Wang, Guangrun and Peng, Jiefeng and Luo, Ping and Wang, Xinjiang and Lin, Liang},
  		journal={arXiv preprint arXiv:1802.03133},
  		year={2018}
    }


### Dependencies
+ Python 2.7 or 3
+ TensorFlow >= 1.3.0
+ [Tensorpack](https://github.com/ppwwyyxx/tensorpack)
   The code depends on Yuxin Wu's Tensorpack. For convenience, we provide a stable version 'tensorpack-installed' in this repository. 
   ```
   # install tensorpack locally:
   cd tensorpack-installed
   python setup.py install --user
   ```

### Usage
+ To run Group Normalization, use:
  ```
  cd KalmanNorm
  python cifar-gn.py --gpu 0 -n 5 --log_dir gn
  ```
+ To run Batch Normalization under the context of micro-batches, use:
  ```
  cd KalmanNorm
  python cifar-bn-microbatch.py --gpu 0 -n 5 --log_dir  bn-microbatch
  ```
+ To run Kalman Normalization under the context of micro-batches, use:
  ```
  cd KalmanNorm
  python cifar-kn-microbatch.py --gpu 0 -n 5 --log_dir  kn-microbatch
+ To run Batch Normalization under the context of large-batches, use:
  ```
  cd KalmanNorm
  python cifar-bn-largebatch.py   --gpu 0 -n 18 --log_dir  bn-largebatch
+ To run Kalman Normalization under the context of large-batches, use:
  ```
  cd KalmanNorm
  python cifar-kn-largebatch.py   --gpu 0 -n 18 --log_dir  kn-largebatch

