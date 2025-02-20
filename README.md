# NTIRE2025_CDFSOD
NTIRE 2025 Challenge on 1-st Cross-Domain Few-Shot Object Detection @ CVPR 2025

## About the Challenge
In this challenge, we invite researchers and developers to participate in the Cross-Domain Few-Shot Object Detection (CD-FSOD) competition. The task is to develop and improve methods for few-shot object detection, specifically in cross-domain settings.

Participants will test their models on a set of target datasets and aim to achieve the best performance in terms of detection accuracy, model efficiency, and few-shot learning on different domains. The main objective is to push the boundaries of object detection methods in cross-domain scenarios, using very few labeled target images.

## The Environments
The evaluation environments adopted by us is recorded in the following part.Below are the system requirements and setup instructions to reproduce the evaluation environment.

### Required Environment Setup
We suggest using Anaconda for environment management. Here's how to set up the environment for the challenge:

- **Step 1**: conda environment create:
  ```bash
    conda create -n cdfsod python=3.9
    conda activate cdfsod
- **Step 2**: install other libs:
  ```bash
    pip install -r requirements.txt

or take it as a reference based on your original environments.

## The Validation datasets
We take COCO as source data and ArTaxOr, Clipart1k, DIOR, DeepFish, NEU-DET, and UODD as validation datasets.

The target datasets could be easily downloaded in the following links: 
- [Dataset Link from Google Drive](https://drive.google.com/drive/folders/16SDv_V7RDjTKDk8uodL2ubyubYTMdd5q?usp=drive_link)

After downloaded all the necessary validate dataset, make sure they are organized as follows:
```bash
|NTIRE2025_CDFSOD/datasets/
|--clipart1k/
|   |--annotations
|   |--test
|   |--train
|--DIOR/
|   |--annotations
|   |--test
|   |--train
|--......