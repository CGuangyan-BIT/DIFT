# Full Transformer Framework for Rpbust Point Cloud Registration with Deep Information Interaction

![DIFT-architecture](DIFT_arch.png)

This repository contains python scripts for training and testing [Deep Interactive Full Transformer (DIFT)]

Deep Interactive Full Transformer (DIFT) is a full Transformer framework for point cloud registration, which achieves superior performance compared with current state-of-the-art learning-based methods in accuracy and robustness. DIFT consists of the following three main modules:

- a Point Cloud Structure Extractor for modeling global relation.
- a Point Feature Transformer for improving the discrimination of features.
- a GMCCE for correspondence confidence evaluation.

## Configuration

This code is based on PyTorch implementation, and tested on:

- Ubuntu 18.04
- CUDA 11.1
- pytorch 1.8.1
- python 3.7.10

You can install the python requirements on your system with:
```bash
cd DIFT
pip install -r requirements.txt
```
  
## Training

You can run the relevant commands under the /DIFT path to train the DIFT model in a specific environment, the network parameters will be saved in the /models folder. Specifically, we use the ModelNet40 dataset for this work, which will be automatically downloaded if necessary.

Train the DIFT on the clean, low noise partial, high noise partial point clouds as
  
```bash
sh experiments/1_train_clean.sh
```
  
```bash
sh experiments/1_train_low_noise_partial.sh
```
  
```bash
sh experiments/1_train_high_noise_partial.sh
```
  
## Evaluation

We provide
- pretrained models on ModelNet40 on clean, low noise partial, high noise partial point clouds. You can download it from this link [weight](https://drive.google.com/file/d/1z2TSNtoK2-zQ_bkcBYk4XwEqZOpdN2GZ/view?usp=sharing). Unzip and place it in the **/DIFT** folder, such that there are three pretrained models under the **/DIFT/models** path;
- three files **1_eval_clean.sh**, **1_eval_low_noise_partial.sh**, **1_eval_high_noise_partial.sh** to evaluate the DIFT model on clean, low noise partial, high noise partial point clouds in /experiments folder;
- three files **1_eval_clean_vis.sh**, **1_eval_low_noise_partial_vis.sh**, **1_eval_high_noise_partial_vis.sh** to visualize the DIFT registration process on clean, low noise partial, high noise partial point clouds in **/experiments** folder;
  
You can run the relevant commands under the **/DIFT** path to evaluate the DIFT model in a specific environment. If you want to evaluate your training results, you can change the model path in the sh file directly
  
Evaluate the DIFT on the clean, low noise partial, high noise partial point clouds as
  
```bash
sh experiments/1_eval_clean.sh
```
  
```bash
sh experiments/1_eval_low_noise_partial.sh
```
  
```bash
sh experiments/1_eval_high_noise_partial.sh
```

You can run the relevant commands under the /DIFT path to visualize the DIFT registration process in a specific environment as


```bash
sh experiments/1_eval_clean_vis.sh
```

```bash
sh experiments/1_eval_low_noise_partial_vis.sh
```
  
```bash
sh experiments/1_eval_high_noise_partial_vis.sh
```