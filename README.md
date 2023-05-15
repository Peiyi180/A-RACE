# Adjusted RACE Framework
## CSCI 4130 Group 3
This framework is based on: https://github.com/DeepSoftwareAnalytics/RACE
### Author:
- Haoyi Zhang
- Peiyi Jiang (PJ@dal.ca)
- Jiahao Chen

## Changes - Dataset Direction
1. xxxx

## Next Steps
1. xxx

## Quick Running Instructions
```
conda create --name py38 python=3.8

conda activate py38

pip install -r requirements.txt

language=go

bash run.sh $language
```
for python and java:

langauge=java # or python

bash run_sample_origin.sh $language

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
> Example command to call split_data.py to sample 17342 data for python and java
> 
> `python split_data_v2.py "python,java"`


