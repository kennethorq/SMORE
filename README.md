# SMORE: Spectrum-based Modality Representation Fusion Graph Convolutional Network for Multimodal Recommendation

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/kennethorq/SMORE">
    <img src="images/smore_logo.png" alt="Logo" width="300" height="150">
  </a>
</div>

## Introduction

This is the Pytorch implementation for our WSDM 2025 paper:

>**[WSDM 2025]** Rongqing Kenneth Ong, Andy W. H Khong (2025). Spectrum-based Modality Representation Fusion Graph Convolutional Network for Multimodal Recommendation
<img src="images/smore_framework.png" width="900px" height="200px"/>

## Enviroment Requirement
- Python 3.7
- Pytorch 1.13

## Dataset  
Download from Google Drive: [Baby/Sports/Clothing](https://drive.google.com/drive/folders/13cBy1EA_saTUuXxVllKgtfci2A09jyaG?usp=sharing)  
The data comprises text and image features extracted from Sentence-Transformers and CNN.  

## How to run
1. Put your downloaded data (e.g. `baby`) under `data` dir.
2. Enter `src` folder and run with  
`python main.py -m SMORE -d baby`  

Other parameters can be specified either via command line or by using the configuration files in `configs/model/SMORE.yaml` and `configs/dataset/*.yaml`.

## Performance Comparison
<img src="images/smore_results.png" width="900px" height="265px"/>

## Best hyperparameters for reproducibility
We present the optimal hyperparameters for SMORE to replicate the results shown in Table 2 of our paper:  

| Datasets  | n_ui_layers | n_layers | image_knn_k | text_knn_k | cl_loss | reg_weight | dropout_rate |
|-----------|-------------|----------|-------------|------------|---------|------------|--------------|
| Baby      | 4           | 1        | 40           | 15          | 0.01       | 1e-04          | 0.1            |
| Sports    | 3           | 1        | 10           | 10          | 0.03       | 1e-04          | 0            |
| Clothing  | 3           | 1        | 40           | 10          | 0.01       | 1e-05          | 0            |


## Citing SMORE
If you find SMORE useful in your research, please consider citing our [paper](www.google.com).
```
To be released in due time.
```
This code is made available solely for academic research purposes.


## Acknowledgement
The structure of this code is inspired by the [MMRec](https://github.com/enoche/MMRec) framework. We acknowledge and appreciate their valuable contributions.