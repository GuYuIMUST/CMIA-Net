# CMIA-Net
Official PyTorch implementation of CMIA-Net for pulmonary embolism classification using cross-modal fusion of CTPA scans and EHR data.

#Overview
<img width="1013" height="551" alt="整体" src="https://github.com/user-attachments/assets/d2de22ed-99ea-46d3-95e1-10f9bd59a8a5" />

#Innovations
1. To address the challenges of varying size of emboli and their complex spatial distributions in 3D CTPA images, we design a Local Pixel Attention (LPA) module for precise capture of fine-grained textures, along with an improved Global Sparse Attention (GSA) mechanism to model long-range dependencies, thereby significantly enhancing the model’s feature extraction capability.
2. We design a dual-branch Bi-TabNet architecture, which is able to capture key features in electronic health records (EHR) tabular data. By strengthening the representation capability of tabular features, it lays a solid foundation for subsequent fusion with imaging features.
3. We design a bidirectional cross-attention module for fusing CTPA imaging features and tabular features. This module effectively aligns and integrates the complementary information from the two modalities, improving the model’s accuracy and robustness in pulmonary embolism diagnosis.
4.Through extensive training and optimization, the proposed model demonstrates excellent performance in pulmonary embolism diagnosis, outperforming existing state-of-the-art methods. Experimental results further show that the proposed approach has significant advantages and strong reliability in real-world clinical applications.

#Main Results
# Main Results

| Modality | Models | AUROC | Acc | F1 score | G-Mean | Specificity | Sensitivity | PPV | NPV |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|    CT   | Our | 0.890 | 0.833 | 0.814 | 0.827 | 0.950 | 0.720 | 0.937 | 0.768 |
|   EHR    | Our | 0.931 | 0.914 | 0.918 | 0.912 | 0.875 | 0.951 | 0.886 | 0.946 |
|   Multimodal    | Our | 0.967 | 0.914 | 0.920 | 0.910 | 0.838 | 0.988 | 0.862 | 0.985 |

#Data Prepare

#Training and Inference

#Evaluation
