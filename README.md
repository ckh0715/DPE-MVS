# DPE-MVS

## About

Dual-Level Precision Edges Guided Multi-View Stereo with Accurate Planarization

The paper has been released and can be found at https://arxiv.org/abs/2412.20328.

If you find this project useful for your research, please cite:
>
    @article{chen2024dual,
        title={Dual-Level Precision Edges Guided Multi-View Stereo with Accurate Planarization},
        author={Chen, Kehua and Yuan, Zhenlong and Mao, Tianlu and Wang, Zhaoqi},
        journal={arXiv preprint arXiv:2412.20328},
        year={2024}
    }

## Dependencies
The code has been tested on Ubuntu 20.04 with Nvidia RTX 3090.

- [Cuda](https://developer.nvidia.cn/zh-cn/cuda-toolkit) >= 10.2
- [OpenCV](https://opencv.org/) >= 3.3.0
- [Boost](https://www.boost.org/) >= 1.62.0
- [cmake](https://cmake.org/) >= 2.8

**Besides make sure that your [GPU Compute Capability](https://en.wikipedia.org/wiki/CUDA) matches the CMakeList.txt!!!** Otherwise you won't get the depth results! For example, according to [GPU Compute Capability](https://en.wikipedia.org/wiki/CUDA), RTX3080's Compute Capability is 8.6. So you should set the cuda compilation parameter 'arch=compute_86,code=sm_86' or add a '-gencode arch=compute_86,code=sm_86'.

## Usage
- Compile
>
    mkdir build & cd build
    cmake ..
    make

- Test
>
    Use script colmap2mvsnet_acm.py to convert COLMAP SfM result to MVS input   
    Run ./DPE $data_folder to get reconstruction results.
    The result will be saved in the folder $data_folder/DPE, and the point cloud is saved as "DPE.ply"

## Acknowledgements
This code largely benefits from the following repositories: [APD-MVS](https://github.com/whoiszzj/APD-MVS), [HPM-MVS](https://github.com/CLinvx/HPM-MVS). Thanks to their authors for opening the source of their excellent works!
