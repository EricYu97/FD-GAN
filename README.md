# FD-GAN
## FD-GAN: Generative adversarial Networks with Fusion-discriminator for Single Image Dehazing(AAAI'20)
[Yu Dong](https://github.com/WeilanAnnn).  [Yihao Liu](https://github.com/DoctorYy)

In this paper, we propose a fully end-to-end algorithm FD-GAN for image dehazing. Moreover, we develop a novel Fusion-discriminator which can integrate the frequency information as additional priors and constraints into the dehazing network. Our method can generate more visually pleasing dehazed results with less color distortion. Extensive experimental results have demonstrated that our method performs favorably against several state-of-the-art methods on both synthetic datasets and real-world hazy images.

![Input](https://github.com/WeilanAnnn/FD-GAN/blob/master/153.jpg)![Output](https://github.com/WeilanAnnn/FGAN/blob/master/153_model5.png)

## Prerequisites
1. Ubuntu 18.04
2. Python 3
3. NVIDIA GPU + CUDA CuDNN (CUDA 8.0)

## Installation
1. conda install pytorch=0.3.0 torchvision cuda80 -c pytorch
2. Install python package:numpy,scipy,PIL,skimage

## Demo using pre-trained model
Since the proposed method uses hdf5 file to load the traning samples, the **generate_testsample.py** helps you to creat the testing or training sample yourself.

If your images are real:
```
python demo.py --dataroot ./facades/'your folder name' --netG ./testmodel/netG_epoch_real.pth
```
If your images are synthetic:
```
python demo.py --dataroot ./facades/'your folder name' --netG ./testmodel/netG_epoch_synthetic.pth
```
To obtain the best performance on synthetic and real-world datasets respectively, we provide two models from different  iterations in one  training procedure. In addition, please use netG.train() for testing since the batch for training is 1.

## Datasets
