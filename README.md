## LLMDiff

This repo is the official implementation of ["LLMDiff: Diffusion Model Using Frozen LLM Transformers For Precipitation Nowcasting"]

## Installation
Code should preferably be run on a machine with large memory (A100)

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

[LLaMa's pre-training weight](https://pan.baidu.com/s/1GEwgDgjB2H_FJyC9i_PMiQ?pwd=4681) is required here (password is 4681), which can be downloaded using Baidu cloud disk or the following code
```bash
python down_load_llama.py
```

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
