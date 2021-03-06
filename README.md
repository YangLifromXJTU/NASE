# NASE
Codes for paper "NASE: Learning Knowledge Graph Embedding for Link Prediction via Neural Architecture Search".<br>
Xiaoyu Kou, Bingfeng Luo, Huang Hu, Yan Zhang.<br>
In CIKM 2020
### [arXiv](https://arxiv.org/abs/2008.07723)

## Prerequisites

- Linux
- Python 3.6
- PyTorch >= 1.2.0

## Getting Started

### Installation

Clone this repo.

```bash
git clone https://github.com/KXY-PUBLIC/NASE.git
cd NASE
```

Please install dependencies by

```bash
pip install -r requirements.txt
```

### Dataset

- FB15K-237 and WN18RR are two well-known KG benchmark datasets.
- Medical-E, Medical-C and Military are three less common datasets to better compare the dataset adaptation ability of each system. 

## Requirement

* pytorch: 1.4.0
* python: 3.5.2
* numpy: 1.16.4

## Searching Examples:

For example, searching on FB15k-237 datasets:
```
mkdir log/
CUDA_VISIBLE_DEVICES=0 nohup python -u search.py --dataset=FB15k-237  --epochs=800 --model_name=NASE --layers=1 --do_margin_loss=1 --embedding_size=200 &> log/search_NASE_fb.out &
```

Searching on Medical-E datasets:

```
CUDA_VISIBLE_DEVICES=0 nohup python -u search.py --dataset=Medical-E  --epochs=800 --model_name=NASE --layers=2 --do_margin_loss=1 --embedding_size=100 &> log/search_NASE_Medical-E.out &
```

## Training Examples:

For example, training on FB15k-237 datasets:
```
CUDA_VISIBLE_DEVICES=0 nohup python -u train.py --dataset=FB15k-237  --epochs=1000 --model_name=NASE --arch=arc_1 --lr=1e-3 --embedding_size=400 &> log/NASE_FB15k-237_arc_1.out &
```

Training on WN18RR datasets:

```
CUDA_VISIBLE_DEVICES=0 nohup python -u train.py --dataset=WN18RR  --epochs=1000 --model_name=NASE --arch=arc_2 --lr=1e-2 --embedding_size=200 &> log/NASE_WN18RR_arc_2.out &
``` 

Training on Medical-E datasets:

```
CUDA_VISIBLE_DEVICES=0 nohup python -u train.py --dataset=Medical-E  --epochs=1000 --model_name=NASE --arch=arc_3 --lr=1e-2 --embedding_size=200 &> log/NASE_Medical-E_arc_3.out &
``` 

Training on Medical-C datasets:

```
CUDA_VISIBLE_DEVICES=0 nohup python -u train.py --dataset=Medical-C  --epochs=1000 --model_name=NASE --arch=arc_1 --lr=1e-2 --embedding_size=200 &> log/NASE_Medical-C_arc_1.out &
``` 

Training on Military datasets:

```
CUDA_VISIBLE_DEVICES=0 nohup python -u train.py --dataset=Military  --epochs=1000 --model_name=NASE --arch=arc_2 --lr=1e-2 --embedding_size=200 &> log/NASE_Military_arc_2.out &
``` 

## Cite

Please cite our paper if you use this code in your own work:

```
@article{kou2020nase,
  title={NASE: Learning Knowledge Graph Embedding for Link Prediction via Neural Architecture Search},
  author={Kou, Xiaoyu and Luo, Bingfeng and Hu, Huang and Zhang, Yan},
  journal={arXiv preprint arXiv:2008.07723},
  year={2020}
}
```