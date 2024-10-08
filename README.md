This repo is made by [Yanwu Xu](http://xuyanwu.github.io) and contains the officially unofficial impelementation for [Semi-Implicit Denoising Diffusion Models (SIDDMs)](https://papers.nips.cc/paper_files/paper/2023/hash/3882ca2c952276247fe9a993193b00e4-Abstract-Conference.html) and [UFOGen: You Forward Once Large Scale Text-to-Image Generation via Diffusion GANs](https://openaccess.thecvf.com/content/CVPR2024/papers/Xu_UFOGen_You_Forward_Once_Large_Scale_Text-to-Image_Generation_via_Diffusion_CVPR_2024_paper.pdf). SIDDMs stands for the fundamental work of UFOGen. Both works are done as research intern at Google. This repo is just for reference, which are both originally implemented via JAX and will not gauranttee the reproducibility for the original papers due to the limited resources and different training settings.

This repo won't be maintained due to some leagal issue and my current working role.

## SIDDMs
In the folder of SIDDMs, there are the code for repoducing the simulation of 5x5 Mixture of Gaussian.

## UFOGen
In the folder of UFO_DiT, it contains the initial try on the few-steps (4-steps) conditional Imagenet generation, where the Generator and the Discriminator will both be loaded from the pretrained checkpopint
from the [fast-DiT repo](https://github.com/chuanyangjin/fast-DiT). Once your start finetuning, the model would generate some reasonbale results in 500 iterations. Please follow the steps to download the pretrained checkpoint for XL/2 and 256x256 resolution. Before running the UFOGen finetuning, you need
to embed the 256x256 imagenet with StableDiffusion Autoencoder. The [kaggle imagenet256x256](https://www.kaggle.com/datasets/dimensi0n/imagenet-256) is suggested. The running env is identical as fast-DiT.

Recommended hardware, 8xA100s with 80G mem.

Once everything is ready, you can run the finetuning with the run.sh script in the UFO_DiT folder.

If you found this repo useful, please cite the following papers.

## Citation

```
@inproceedings{NEURIPS2023_3882ca2c,
 author = {xu, yanwu and Gong, Mingming and Xie, Shaoan and Wei, Wei and Grundmann, Matthias and Batmanghelich, Kayhan and Hou, Tingbo},
 booktitle = {Advances in Neural Information Processing Systems},
 editor = {A. Oh and T. Naumann and A. Globerson and K. Saenko and M. Hardt and S. Levine},
 pages = {17383--17394},
 publisher = {Curran Associates, Inc.},
 title = {Semi-Implicit Denoising Diffusion Models (SIDDMs)},
 url = {https://proceedings.neurips.cc/paper_files/paper/2023/file/3882ca2c952276247fe9a993193b00e4-Paper-Conference.pdf},
 volume = {36},
 year = {2023}
}
```
```
@InProceedings{Xu_2024_CVPR,
    author    = {Xu, Yanwu and Zhao, Yang and Xiao, Zhisheng and Hou, Tingbo},
    title     = {UFOGen: You Forward Once Large Scale Text-to-Image Generation via Diffusion GANs},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2024},
    pages     = {8196-8206}
}
```
