# <img src="docs/catch.png" alt="Image description" style="width:50px;height:50px;"> CATCH: Channel-Aware Multivariate Time Series Anomaly Detection via Frequency Patching

**This code is the official PyTorch implementation of our ICLR'25 paper: [CATCH](https://arxiv.org/pdf/2410.12261): Channel-Aware Multivariate Time Series Anomaly Detection via Frequency Patching.**

[![ICLR](https://img.shields.io/badge/ICLR'25-CATCH-orange)](https://arxiv.org/pdf/2412.10859)  [![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)  [![PyTorch](https://img.shields.io/badge/PyTorch-2.4.1-blue)](https://pytorch.org/)  ![Stars](https://img.shields.io/github/stars/decisionintelligence/CATCH)  [![Visits Badge](https://badges.pufler.dev/visits/decisionintelligence/CATCH)](https://badges.pufler.dev/visits/decisionintelligence/CATCH)

If you find this project helpful, please don't forget to give it a ⭐ Star to show your support. Thank you!

🚩 News (2025.1) CATCH has been accepted by ICLR 2025.

## Introduction

**CATCH**, a framework based on frequency patching, flexibly utilizing the channel correlations to reconstruct all the frequency spectrums in a fine-grained way to achieve remarkable detection accuracy. Technically,  we propose a **Channel Fusion Module** (CFM), which features a patch-wise **mask generator** and the masked-attention mechanism. Driven by a bi-level multi-objective optimization algorithm, the CFM is encouraged to iteratively discover appropriate patch-wise channel correlations and **cluster similar channels in the hidden spaces while isolate the adverse effects from irrelevant channels**, which provides both the **capacity and robustness** of the attention mechanism.

<div style="text-align: center;">
    <img src="docs/overview.png" alt="CATCH" style="zoom:80%;" />
</div>


## Quickstart

### Installation

Given a python environment (**note**: this project is fully tested under python 3.8), install the dependencies with the following command:

```
pip install -r requirements.txt
```

### Data preparation

Prepare Data. You can obtained the well pre-processed datasets from [OneDrive](https://1drv.ms/u/c/801ce36c4ff3f93b/EYJSkiM-_ZlJkvh4Md9JfS4BOppI9lqxJ9QGpR8Sc05fzw?e=qNTd1u). (This may take some time, please wait patiently.) Then place the downloaded data under the folder `./dataset`. 

### Train and evaluate model

- To see the model structure of CATCH,  [click here](./ts_benchmark/baselines/self_impl/CATCH/CATCH.py).
- We provide the experiment scripts for CATCH and other baselines under the folder `./scripts/multivariate_detection`. For example you can reproduce a experiment result as the following:

```shell
sh ./scripts/multivariate_detection/detect_label/MSL_script/CATCH.sh

sh ./scripts/multivariate_detection/detect_score/MSL_script/CATCH.sh
```



## Results

Extensive experiments on 10 real-world datasets and 12 synthetic datasets demonstrate that CATCH achieves state-of-the-art performance. We show the main results of all the 10 real-world datasets, and report the mean results of the 6 types of synthetic datasets:

<div align="center">
<img alt="exp" src="docs/experiment.png" width="100%"/>
</div>


## Setup for Running Baseline Models
If you want to test all baseline models, follow these steps:
#### 1. Install Git
Some models require Git to run. Please ensure that Git is installed on your system. If not, you can install it using the following command:
```shell
sudo apt-get install git
```
#### 2. Download and Extract Environment
Download the environment from [OneDrive](https://1drv.ms/u/c/801ce36c4ff3f93b/Eapc8wI7tqxOqmOPZ66uMG4BgeX8j7AewKq7NekCI0Al2w?e=NdenlL). (This may take some time, please wait patiently.) Then, create a directory my_env (we recommend creating it under `conda/envs/`) and extract the environment into this directory:
```shell
mkdir -p my_env
tar -xzf CATCH.tar.gz -C my_env
```
#### 3. Activate the Environment
```shell
source my_env/bin/activate
```
#### 4. Clean Environment Prefix
You can clear the environment prefix using the following command. Now the environment is the same as one created directly with conda at this path:
```shell
(my_env) $ conda-unpack
```
#### 5. Run Baseline Models
Now you can test all the baseline models. We provide experiment scripts for various baseline models under the folder `./scripts/multivariate_detection`:
```shell
(my_env) $ sh ./scripts/multivariate_detection/detect_label/MSL_script/AnomalyTransformer.sh
```

## Citation

If you find this repo useful, please cite our paper.

```
@inproceedings{wu2024catch,
  title     = {CATCH: Channel-Aware multivariate Time Series Anomaly Detection via Frequency Patching},
  author    = {Wu, Xingjian and Qiu, Xiangfei and Li, Zhengyu and Wang, Yihang and Hu, Jilin and Guo, Chenjuan and Xiong, Hui and Yang, Bin},
  booktitle = {ICLR},
  year      = {2025}
}
```


## Contact

If you have any questions or suggestions, feel free to contact:
- Xingjian Wu (xjwu@stu.ecnu.edu.cn)
- [Xiangfei Qiu](https://qiu69.github.io/) (xfqiu@stu.ecnu.edu.cn)

Or describe it in Issues.

