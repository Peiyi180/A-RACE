# Adjusted RACE Framework
## CSCI 4130 Group 3
This framework is based on: https://github.com/DeepSoftwareAnalytics/RACE
### Author:
- Peiyi Jiang (PJ@dal.ca)
- Haoyi Zhang
- Jiahao Chen

<div class="warning" style="background-color:#16598f; color:#ffffff; border-radius: 5px; padding: 10px;">
  
**Warning:** This is a demo branch which is not for training.
  
</div>

## Prerequisite
download corresponding bin file matching this branch from google drive

https://drive.google.com/drive/folders/12VWdvEGaUFR3BrDtcB18X7jOZm3htkWe

upload pretrained model to:

encoder bin should be placed at `saved_model/codet5/${lang}/checkpoint-best-bleu/pytorch_model.bin`

ecmg bin should be placed at `saved_model/ECMG/${lang}/checkpoint-best-bleu/pytorch_model.bin`

make sure there is `train.jsonl` in the corresponding language folder

Ex: `dataset/java/contextual_medits/predict/train.jsonl`

For downloading the dataset, refer other branches or instructions bottom

running code on a machine has NVIDIA GPU

## Quick Running Instructions
make some changes and make sure it can be detected by `git diff <file-name>`

`conda create --name py38 python=3.8`

`conda activate py38`

`pip install -r requirements.txt`

`cd demo`

`bash preprocess.sh <file-name>`

`bash inference.sh <language>`

## Dataset Instructions
> Downloading Dataset
> ```
> wget https://zenodo.org/record/7196966/files/dataset.tar.gz
>tar zxvf dataset.tar.gz
> ```
> dataset folder must be at the same level as the run script
>
> Sample data:
> 
> Example command to call split_data.py to sample 10% data for all 5 languages
> 
> `python split_data.py "cpp,csharp,java,javascript,python" 10`
