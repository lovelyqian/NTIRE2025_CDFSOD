# NTIRE2025_CDFSOD
NTIRE 2025 Challenge on 1-st Cross-Domain Few-Shot Object Detection @ CVPR 2025

## About the Challenge
In this challenge, we invite researchers and developers to participate in the Cross-Domain Few-Shot Object Detection (CD-FSOD) competition. The task is to develop and improve methods for few-shot object detection, specifically in cross-domain settings.

Participants will test their models on a set of target datasets and aim to achieve the best performance in terms of detection accuracy, model efficiency, and few-shot learning on different domains. The main objective is to push the boundaries of object detection methods in cross-domain scenarios, using very few labeled target images.

This challenge does not impose restrictions on source data selection (e.g., COCO) or pretrained models, allowing participants to leverage diverse knowledge sources to improve performance on the target domain. We will provide multiple novel datasets for validation, while the final evaluation will be conducted on previously unseen test sets. Mean Average Precision (mAP) will be used as the ranking metric.

We will also provide several strong baseline models, while strongly encouraging participants to explore innovative solutions that improve detection accuracy on the target domain while effectively leveraging knowledge from the source domain. This challenge offers a unique opportunity for researchers and practitioners from academia and industry to push the boundaries of cross-domain few-shot object detection.

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
    cd NTIRE2025_CDFSOD
    pip install -r requirements.txt
    pip install -e ./
or take it as a reference based on your original environments.

## The Validation datasets
We take COCO as source data and ArTaxOr, Clipart1k, DIOR, DeepFish, NEU-DET, and UODD as validation datasets.

The target datasets could be easily downloaded in the following links: 
- [Dataset and Weights Link from Google Drive](https://drive.google.com/drive/folders/16SDv_V7RDjTKDk8uodL2ubyubYTMdd5q?usp=drive_link)

After downloaded all the necessary validate datasets, make sure they are organized as follows:
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
```
And the weights should be organized as follows:
```bash
|NTIRE2025_CDFSOD/weights/
|--trained/
|   |--vitl_0089999.pth
|--background/
|   |--background_prototypes.vitl14.pth
```

## Test the baseline model
As the environment is ready, select different baseline to test
### Run CD-ViTO
```
bash main_results.sh
```
### Run DE-ViT-FT
Add --controller to main_results.sh, then
```
bash main_results.sh
```

## Evaluation Criteria & Fairness
To ensure fairness and meaningful benchmarking, participants must adhere to the following guidelines:
- **Mean Average Precision (mAP)** will be the primary ranking metric.
- **Platform**: The challenge will be hosted on [Codalab / EvalAI / Kaggle] (TBD).
- **Submission Format**: Predictions must be submitted in COCO-style JSON annotations.
- **Training Restrictions**:Participants may use any publicly available pretrained models, but no direct training or fine-tuning using the provided test sets is allowed.
- **Statement**:Each submission must include a reproducibility statement, detailing the model’s training strategy and pretrained resources used.

## Provided Resources
- **CD-FSOD Benchmark**: A dataset with distinct source and target domains designed for evaluating cross-domain FSOD models.
- **Baseline Models**: We will provide baseline implementations of DE-ViT and CD-ViTO, along with training scripts and benchmark results.
- **Evaluation Server**: Participants will submit results to an online leaderboard for validation and testing.

The top-ranked participants will be awarded and invited to follow the CVPR submission guide for workshops to describe their solution and to submit to the associated NTIRE workshop at CVPR 2025.

## References
If you feel this codebase and the report paper is useful for you, please cite our baseline work:
```
@inproceedings{fu2025cross,
  title={Cross-domain few-shot object detection via enhanced open-set object detector},
  author={Fu, Yuqian and Wang, Yu and Pan, Yixuan and Huai, Lian and Qiu, Xingyu and Shangguan, Zeyu and Liu, Tong and Fu, Yanwei and Van Gool, Luc and Jiang, Xingqun},
  booktitle={European Conference on Computer Vision},
  pages={247--264},
  year={2025},
  organization={Springer}
}
```

## Origanizers


## Acknowledgement
