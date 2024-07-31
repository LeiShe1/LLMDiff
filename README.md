## LLMDiff

This repo is the official implementation of ["LLMDiff: Diffusion Model Using Frozen LLM Transformers For Precipitation Nowcasting"]

## Installation

```bash
python>=3.9
torch>=1.12.1
cuda>=11.3
```

## Dataset

### MovingMNIST

We use [MovingMNIST](https://github.com/mansimov/unsupervised-videos) that contains 10,000 sequences each of length 20 showing 2 digits moving in a $64\times 64$ frame. At the same time, we can use Baidu cloud web disk link to download [MovingMNIST](https://pan.baidu.com/s/18OhkdGs92Pb-UfePNLIsDQ?pwd=4681),password is 4681.

### SEVIR

[Storm EVent ImageRy (SEVIR) dataset](https://sevir.mit.edu/) is a spatiotemporally aligned dataset containing over 10,000 weather events.

To download SEVIR dataset from AWS S3, run:
```bash
cd ROOT_DIR/LLMDiff
python ./scripts/datasets/sevir/download_sevir.py --dataset sevir
```

## LLMDiff Training

Run the following command to train LLMDiff on MovingMNIST.

```bash
cd ./scripts/diff_transformer/moving_mnist
bash train.sh
```

Run the following command to train LLMDiff on SEVIR.

```bash
cd ./scripts/diff_transformer/sevir
bash train.sh
```
