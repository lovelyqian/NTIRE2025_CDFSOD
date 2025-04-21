# NTIRE2025_CDFSOD
NTIRE 2025 Challenge on **1-st Cross-Domain Few-Shot Object Detection @ CVPR 2025** 🔥🔥

Link: https://codalab.lisn.upsaclay.fr/competitions/21851

[**News!**] 25-03-01: We release the [testing datasets](https://drive.google.com/drive/folders/1Pewv7HYacwD5Rrknp5EiAdw8vMbaaFAA?usp=sharing)! 

[**News!**] 25-03-27: The ranking of teams has been released. Check the results [here](https://docs.google.com/spreadsheets/d/1ft1SV9E1k5J4OgUB6omaxRdqTvCn_uLsNlon2AB0llQ/edit?usp=sharing)!

[**News!**] 25-04-01: Our challenge paper is accepted by NTIRE25 workshop @ CVPR2025. 🎉

[**News!**]: [Arxiv Paper](https://arxiv.org/pdf/2504.10685) of the technical report will be released！📖 

[**News!**]: Codes of the proposed methods from our participants have be released！ 🎈 

**Links to the proposed solutions:** 🏆
- Winners of open-source CD-FSOD:
    - Team MoveFree: https://github.com/KAIJINZ228/Few_Shot_GD
    - Team AI4EarthLab: https://github.com/jaychempan/ETS
    - Team IDCFS: https://github.com/Pumpkinder/GLIP-CDFSOD

- Winners of closed-source CD-FSOD:
    - Team X-Few: https://github.com/johnmaijer/X-Few-_CD-FSOD

- Others:
    - Team FDUROILab_Lenovo: https://github.com/omnipotent13/cfsod_challenge
    - Team RLG: https://github.com/lch216/cdfsod-project
    - Team TongjiLab: https://github.com/Sun-HR02/ProtoDINO/tree/main
    - Team HUSTLab: https://github.com/Weston111/cdfsod
    - Team FSV: https://github.com/yuqing-yang/CDFSOD-FSV
    - Team IPC: https://github.com/Linzeyin/NTIRE2025_CDFSOD_tta

## About the Challenge
In this challenge, we invite researchers and developers to participate in the **Cross-Domain Few-Shot Object Detection (CD-FSOD)** competition. The task is to develop and improve methods for few-shot object detection, specifically in cross-domain settings.

![benchmark](./image/benchmark.png)

Participants will test their models on a set of target datasets and aim to achieve the best performance in terms of **Mean Average Precision (mAP)** on different domains. The main objective is to push the boundaries of object detection methods in cross-domain scenarios, using very few labeled target images.

This challenge does not impose restrictions on **source data selection** (e.g., COCO) or pretrained models, allowing participants to leverage diverse knowledge sources to improve performance on the target domain. We will provide multiple novel datasets for validation, while the final evaluation will be conducted on previously unseen test sets. The **mAP** will be used as the ranking metric.

We will also provide several strong baseline models, while strongly encouraging participants to explore innovative solutions that improve detection accuracy on the target domain while effectively leveraging knowledge from the source domain. This challenge offers a unique opportunity for researchers and practitioners from academia and industry to push the boundaries of cross-domain few-shot object detection.


## The Environments
The evaluation environments we adopted are recorded in the following section. Below are the system requirements and setup instructions for reproducing the evaluation environment.

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

## The Validation Datasets
We take COCO as source data and ArTaxOr, Clipart1k, and DeepFish as validation datasets.

The target datasets could be easily downloaded in the following links: 
- [Dataset and Weights Link from Google Drive](https://drive.google.com/drive/folders/16SDv_V7RDjTKDk8uodL2ubyubYTMdd5q?usp=drive_link)

## The Test Datasets
03-01: we just released the datasets for testing!

**The testing datasets could be easily downloaded in the following links:**
- **[Dataset Link from Google Drive](https://drive.google.com/drive/folders/1Pewv7HYacwD5Rrknp5EiAdw8vMbaaFAA?usp=sharing)**

After downloading all the necessary validation datasets, make sure they are organized as follows:

```bash
|NTIRE2025_CDFSOD/datasets/
|--clipart1k/
|   |--annotations
|   |--test
|   |--train
|--ArTaxOr/
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
As the environment is ready, select a different baseline to test
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
- **Mean Average Precision (mAP)**: mAP will be the primary ranking metric.
- **Platform**: The challenge will be hosted on [Codalab](https://codalab.lisn.upsaclay.fr/competitions/21851).
- **Submission Format**: Predictions must be submitted in COCO-style JSON annotations.
- **Training Restrictions**: Participants may use any publicly available pretrained models, and use the few-labeled supports (1shot/5shot/10shot) for finetuning the models.  However, manually search for more support images is strictly **forbidden**. 
- **Statement**: Each submission must include a reproducibility statement, detailing the model’s training strategy and pretrained resources used.

## Provided Resources
- **CD-FSOD Benchmark**: A dataset with distinct source and target domains designed for evaluating cross-domain FSOD models.
- **Baseline Models**: We will provide baseline implementations of DE-ViT and CD-ViTO, along with training scripts and benchmark results.
- **Evaluation Server**: Participants will submit results to an online leaderboard for validation and testing.

**The top-ranked participants will be awarded and invited to follow the CVPR submission guide for workshops to describe their solution and to submit to the associated NTIRE workshop at CVPR 2025.**

## References
please consider citing our baseline work:
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

and our technical report:
```
@inproceedings{fu2025ntire, 
  title={NTIRE 2025 challenge on cross-domain few-shot object detection: methods and results},
  author={Fu, Yuqian and Qiu, Xingyu and Ren, Bin and Fu, Yanwei and Timofte, Radu and Sebe, Nicu and Yang, Ming-Hsuan and Van Gool, Luc and others},
  booktitle={CVPRW},
  year={2025}
}
```

and if you are looking for related works for cross-domain few-shot learning, please consider also: 
```
@inproceedings{fu2023styleadv,
  title={Styleadv: Meta style adversarial training for cross-domain few-shot learning},
  author={Fu, Yuqian and Xie, Yu and Fu, Yanwei and Jiang, Yu-Gang},
  booktitle={Proceedings of the IEEE/CVF conference on computer vision and pattern recognition},
  pages={24575--24584},
  year={2023}
}

@inproceedings{fu2021meta,
  title={Meta-fdmixup: Cross-domain few-shot learning guided by labeled target data},
  author={Fu, Yuqian and Fu, Yanwei and Jiang, Yu-Gang},
  booktitle={Proceedings of the 29th ACM international conference on multimedia},
  pages={5326--5334},
  year={2021}
}

```
## Organizers
For inquiries, please contact the challenge organizers: 

Yuqian Fu (yuqian.fu@insait.ai)

Xingyu Qiu (xyqiu24@m.fudan.edu.cn)

Bin Ren (bin.ren@unitn.it)

Yanwei Fu (yanweifu@fudan.edu.cn)

Radu Timofte (radu.timofte@uni-wuerzburg.de)

Nicu Sebe (niculae.sebe@unitn.it)

Ming-Hsuan Yang (mhyang@ucmerced.edu)

Luc Van Gool (luc.vangool@insait.ai)

For more details about the NTIRE Workshop and challenge organizers, visit: [NTIRE 2025](https://cvlai.net/ntire/2025/).

## Others
For more details, e.g., the important dates, the submission, the final scoring method, please see our [codalab](https://codalab.lisn.upsaclay.fr/competitions/21851).
