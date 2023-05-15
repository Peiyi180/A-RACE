# Adjusted RACE Framework
## CSCI 4130 Group 3
This framework is based on: https://github.com/DeepSoftwareAnalytics/RACE
### Author:
- Peiyi Jiang (PJ@dal.ca)
- Haoyi Zhang
- Jiahao Chen

## Changes
1. Add conditions to determine if computer support cuda in the ECMG model. This will enable 
the model to be tested on a machine that doesn't have NVIDIA GPU
2. Decrease the batch number to solve the out of memory error on the Machines 
with inadequate GPU performance
3. Replace default decoder with GPT-2
4. Split data and save 20% data


## Quick Running Instructions
```
conda create --name py38 python=3.8

conda activate py38

pip install -r requirements.txt

language=java

percentage=20

bash run_sample_gpt2.sh $language $percentage

```

language support in current repo: java, python

Original pipeline: `bash run_sample_origin.sh $language $percentage`

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
