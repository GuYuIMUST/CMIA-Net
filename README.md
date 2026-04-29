# BiLGC-Net
Official PyTorch implementation of BiLGC-Net for pulmonary embolism classification using cross-modal fusion of CTPA scans and EHR data.

# Overview
<img width="1013" height="551" alt="整体" src="https://github.com/user-attachments/assets/d2de22ed-99ea-46d3-95e1-10f9bd59a8a5" />
The full implementation will be released after the associated paper is accepted.

# Innovations
1.3D Image Processing:Extracts complex emboli features using LPA (Local Pixel Attention) and GSA (Global Sparse Attention).

2.EHR Tabular Modeling: Employs a dual-branch Bi-TabNet to capture key clinical features.

3.Multimodal Fusion: Integrates imaging and tabular data via a bidirectional Cross-Modal Interaction Attention (CMIA) module.

# Main Results

| Models | AUROC | Acc | F1 score | G-Mean | Specificity | Sensitivity | PPV | NPV |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| RadFusion | 0.946 | 0.890 | 0.902 | 0.891 | 0.900 | 0.882 | 0.924 | 0.847 |
| PECon | 0.943 | 0.900 | 0.913 | - | - | - | - | - |
| PE-MVCNet | 0.941 | 0.902 | 0.906 | 0.935 | 0.932 | 0.939 | 0.899 | 0.932 |
| Ours | 0.967 | 0.914 | 0.920 | 0.910 | 0.838 | 0.988 | 0.862 | 0.985 |

# Pre-requisties
· Windows
· Python >= 3.10
· CUDA == 12.8
· PyTorch >= 2.0

# Getting started to evluate
# Data preprocess
1.Image Data:The preprocessing of the image data can follow this link https://github.com/marshuang80/penet In short,using
create create_hdf5.py to make an hdf5 file.

2.Tabular Data:The preprocessing of the tabular data can follow this link:https://github.com/LeavingStarW/PE-MVCNET/tree/main.In short,using LinearSVC for dimensionlity reduction on EHR data,then applying TabNet to generate embeddings.

# Evaluation
To run the evaluation,please execute the following command:
```
bash
sh test.sh
```

To find the optimal threshold for the best results,please run:
```
python best_threshold.py
```

# Training
To train the model from scratch,execute:
```
bash
sh train.sh
```

# Data
The data we used is form Standford University Medical Center dataset.You can download it from https://stanfordaimi.azurewebsites.net/datasets/3a7548a4-8f65-4ab7-85fa-3d68c9efc1bd.The tabular data we use can be downloaded from https://github.com/LeavingStarW/PE-MVCNET/blob/main/ehr_nosub_1.csv,where the preprocessed tabular data is already provided.
