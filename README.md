# SMORE: Spectrum-based Modality Representation Fusion Graph Convolutional Network for Multimodal Recommendation

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/kennethorq/SMORE">
    <img src="images/smore_logo.png" alt="Logo" width="400" height="200">
  </a>
</div>

## Introduction

This is the Pytorch implementation for our WSDM 2025 paper:

>**[WSDM 2025]** Rongqing Kenneth Ong, Andy W. H Khong (2025). Spectrum-based Modality Representation Fusion Graph Convolutional Network for Multimodal Recommendation
<img src="images/smore_framework.png" width="900px" height="250px"/>

## Enviroment Requirement
- Python 3.7
- Pytorch 1.13

## Dataset  
Download from Google Drive: [Baby/Sports/Clothing](https://drive.google.com/drive/folders/13cBy1EA_saTUuXxVllKgtfci2A09jyaG?usp=sharing)  
The data comprises text and image features extracted from Sentence-Transformers and CNN.  

## How to run
1. Place the downloaded data (e.g. `baby`) into the `data` directory.
2. Enter the `src` folder and execute the following command:  
`python main.py -m SMORE -d baby`  

Other parameters can be set either through the command line or by using the configuration files located in `configs/model/SMORE.yaml` and `configs/dataset/*.yaml`.

## Performance Comparison
<div align="center">
    <img src="images/smore_results.png" width="750px" height="300px">
</div>


## Best hyperparameters for reproducibility
We present the optimal hyperparameters for SMORE to replicate the results shown in Table 2 of our paper:  

| Datasets  | n_ui_layers | n_layers | image_knn_k | text_knn_k | cl_loss | reg_weight | dropout_rate |
|-----------|-------------|----------|-------------|------------|---------|------------|--------------|
| Baby      | 4           | 1        | 40           | 15          | 0.01       | 1e-04          | 0.1            |
| Sports    | 3           | 1        | 10           | 10          | 0.03       | 1e-04          | 0            |
| Clothing  | 3           | 1        | 40           | 10          | 0.01       | 1e-05          | 0            |


## Citation
If you find SMORE useful in your research, please consider citing our [paper](https://arxiv.org/abs/2412.14978).
```

```
This code is made available solely for academic research purposes.


## Acknowledgement
The structure of this code is inspired by the [MMRec](https://github.com/enoche/MMRec) framework. We acknowledge and appreciate their valuable contributions.