# Adjusted RACE Framework
## CSCI 4130 Group 3
This framework is based on: https://github.com/DeepSoftwareAnalytics/RACE
### Author:
- Jiahao Chen
- Peiyi Jiang (PJ@dal.ca)
- Haoyi Zhang

## Changes - AST Direction
1. Added a unified cross-modal pre-trained model, UniXcoder that are trained using AST.
Reference: https://github.com/microsoft/CodeBERT/tree/master/UniXcoder
2. In the generation step, we feed input source code to UniXcoder encoder and concat the encoding 
output to the encoding output of existing ECMG encoder (codeT5 in current pipeline) on second dimension (column),
and then concat the combined encoding outputs above to retrieved similar commit message embedding before
feeding to the ECMG decoder.

    (Notes: due to the increase of dimension. The memory usage increase by 10%.)

## Next Steps
1. Instead of feeding UniXcoder the source code, we can parse it and exact AST to unlock the power of this model.
2. We can use the encoding output from UniXcoder to calculate the similarity of input code diff and retrieved code diff,
like what we are doing in the existing Exemplar Guider, and then ensemble the existing similarity to get a more
stable and accurate score so that it can better guide the commit message generation.

## Quick Running Instructions

```
conda create --name py38 python=3.8

conda activate py38

pip install -r requirements.txt

language=java

percentage=20

bash run_sample_ast.sh $language $percentage
```
language support in current repo: java, python

## Dataset Instructions
Downloading & Sampling Dataset
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

