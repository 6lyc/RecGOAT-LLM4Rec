# RecGOAT: Graph Optimal Adaptive Transport for LLM-Enhanced Multimodal Recommendation with Dual Semantic Alignment

<img width="2752" height="1394" alt="github_cover" src="https://github.com/user-attachments/assets/9d83cad8-ec19-48ae-83f0-df0854c731fc" />

PyTorch implementation for our paper [RecGOAT: Graph Optimal Adaptive Transport for LLM-Enhanced Multimodal Recommendation with Dual Semantic Alignment](https://arxiv.org/abs/2602.00682).

[Yuecheng Li](https://scholar.google.com/citations?user=t73_KbYAAAAJ), [Hengwei Ju](https://openreview.net/profile?id=~Hengwei_Ju1), [Zeyu Song](https://openreview.net/profile?id=~Ze-Yu_Song2), [Wei Yang](https://weiyang930.github.io/), [Chi Lu](https://scholar.google.com/citations?user=SrvT0voAAAAJ), [Peng Jiang](https://scholar.google.com/citations?hl=en&user=9o5swhQAAAAJ), and [Kun Gai](https://scholar.google.com/citations?user=PXO4ygEAAAAJ).

**[Kuaishou Inc](https://ir.kuaishou.com/)**, Fudan University, and University of Southern California

*We will release the code, data, and LLM-enhanced multimodal data of RecGOAT after the paper is accepted and upon passing company review!*

-----------

<p align="center">
<img width="1021" height="494" alt="image" src="https://github.com/user-attachments/assets/033ff33b-a735-4de2-bbe1-04e8dd45de23" />
</p>

We propose RecGOAT, a novel yet simple dual semantic alignment framework for LLM-enhanced multimodal recommendation, which offers theoretically guaranteed alignment capability. RecGOAT first employs graph attention networks to enrich collaborative semantics by modeling item-item, user-item, and user-user relationships, leveraging user/item LM representations and interaction history. Furthermore, we design a dual-granularity progressive multimodality-ID alignment framework, which achieves instance-level and distribution-level semantic alignment via cross-modal contrastive learning (CMCL) and optimal adaptive transport (OAT), respectively.

-----------

## 📢 News  

- [x] [2026.08.23] 🔥🔥 The codebase of our **RecGOAT** is available!

- [x] [2026.02.03] 🔥🔥 The full paper of our **RecGOAT** is available at [arXiv](https://arxiv.org/abs/2602.00682).
      

## Dependence

To install the dependencies: 

```sh
pip install -r requirements.txt
```

## Usage and Hyperparameter

```bash
# Baby
CUDA_VISIBLE_DEVICES=0 python -u main.py --dataset baby_raw --model lgn_mm --use_multimodal 1 --text_feat ./data/baby_raw/text_feat.npy --image_feat ./data/baby_raw/image_feat.npy --item_knn_k 20 --item_branch_layers 1 --epochs 1000 --recdim 800 --layer 3 --lr 8e-4 --bpr_batch 4096 --topks "[10]" --fusion oat --contrastive_weight 0.032 > ./baby.log 2>&1 &

# Sports
CUDA_VISIBLE_DEVICES=0 python -u main.py --dataset sports_raw --model lgn_mm --use_multimodal 1 --text_feat ./data/sports_raw/text_feat.npy --image_feat ./data/sports_raw/image_feat.npy --item_knn_k 30 --item_branch_layers 1 --epochs 1000 --recdim 600 --layer 3 --lr 8e-4 --bpr_batch 4096 --topks "[10]" --fusion oat --contrastive_weight 0.005 > ./sports.log 2>&1 &

# Electronics
CUDA_VISIBLE_DEVICES=0 python -u main.py --dataset electronics --model lgn_mm --use_multimodal 1 --text_feat ./data/electronics_raw/text_feat.npy --image_feat ./data/electronics_raw/image_feat.npy --item_knn_k 20 --item_branch_layers 1 --epochs 2000 --recdim 200 --layer 3 --lr 8e-4 --bpr_batch 4096 --topks "[10]" --fusion oat --contrastive_weight 0.05 > ./electronics.log 2>&1 &
```

## 👉 TODO 

- [x] Release the code of RecGOAT.

- [ ] Release the LLM-enhanced multimodal data of RecGOAT.

- [ ] ...
      
## Citation  

```BibTex
@article{li2026recgoat,
  title={RecGOAT: Graph Optimal Adaptive Transport for LLM-Enhanced Multimodal Recommendation with Dual Semantic Alignment},
  author={Li, Yuecheng and Ju, Hengwei and Song, Zeyu and Yang, Wei and Lu, Chi and Jiang, Peng and Gai, Kun},
  journal={arXiv preprint arXiv:2602.00682},
  year={2026}
}
```
