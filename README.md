# 🛢️ Oil Spill Detection Using Deep Learning  
**A Comparative Study of U-Net, DeepLabV3, and PSPNet on Satellite Imagery**

This project implements deep learning-based oil spill detection from satellite imagery using semantic segmentation. We compare the performance of U-Net, DeepLabV3, and PSPNet on a high-resolution SAR dataset to identify oil-contaminated regions accurately.

---

## 🌍 Motivation  
Oil spills severely impact marine ecosystems and economies. Early detection is crucial for rapid response and environmental protection. Traditional detection via remote sensing struggles under variable weather or ocean conditions. Deep learning offers robust segmentation capabilities for this task, especially using CNNs that extract spatial features effectively.

---

## 📁 Dataset  
- **Source**: Public Kaggle dataset – [`oil-spill`](https://www.kaggle.com/datasets/nabilsherif/oil-spill)
- **Content**: High-resolution SAR satellite images  
- **Annotations**: Ground truth masks for supervised segmentation  
- **Characteristics**:  
  - Diverse weather and sea conditions  
  - Variation in spill shape, size, and noise  
  - Pre-processed and labeled for segmentation tasks

---

## 🧠 Models Compared  

| Model         | Key Technique                    | Strengths                                 |
|---------------|----------------------------------|-------------------------------------------|
| **U-Net**     | Encoder-decoder + skip connections | Fast training, good general recall        |
| **DeepLabV3** | Atrous Spatial Pyramid Pooling   | Highest precision/recall, strong detail   |
| **PSPNet**    | Pyramid Pooling Module           | Multi-scale context, better on large spills|

---

## 📊 Performance Metrics  

| Model        | Precision | Recall  | F1 Score |
|--------------|-----------|---------|----------|
| **U-Net**    | 94.62%    | 94.99%  | 94.75%   |
| **DeepLabV3**| 95.34%    | 95.63%  | 95.43%   |
| **PSPNet**   | 89.32%    | 89.97%  | 89.93%   |

> DeepLabV3 outperformed others in precision and recall, especially with smaller and more complex spill boundaries.

---

## 📈 Training Insights  

- **U-Net**: Fast convergence but slight overfitting after epoch 40  
- **DeepLabV3**: Highest training/validation accuracy (97.3%)  
- **PSPNet**: Stable training; better on large spill regions, but underperforms on finer boundaries  
- All models showed robust learning curves and segmentations.

---
## 🚧 Limitations in Existing Systems  

- ⚠️ **Lack of annotated data**: Training deep learning models needs high-quality labeled datasets, which are often missing.
- ⚠️ **Class imbalance**: Non-spill regions dominate the dataset, biasing predictions.
- ⚠️ **Poor generalizability**: Many models struggle across varied ocean and lighting conditions.
- ⚠️ **Sensitivity to noise**: Cloud cover, artifacts, and rough waters degrade performance.
- ⚠️ **Real-time infeasibility**: Current models may not scale well for large-area real-time detection.

---

## 🕵️ Research Gaps  

- Existing models fail to accurately identify **small, scattered spills** or those embedded in complex backgrounds.
- Lack of **real-time segmentation pipelines** for wide ocean surveillance.
- **Model interpretability** and explainability is limited — especially critical for environmental risk decisions.
- Need for **multi-modal integration** (e.g., combining SAR with AIS, optical, or ocean current data).
- Overreliance on simple metrics — deeper performance evaluation needed beyond accuracy and F1.

---

## 🔭 Future Scope  

- ✅ **Integrate AIS data** (Automatic Identification System) to correlate detected spills with nearby vessel activity.
- ✅ **Use of attention mechanisms** such as CBAM or SE blocks for more focused feature extraction.
- ✅ Expand to **multi-spectral and multi-temporal** datasets for robustness.
- ✅ Explore **real-time inference pipelines** for deployment in maritime monitoring systems.
- ✅ Apply **data augmentation and transfer learning** to generalize better on unseen ocean conditions.

---

## 🛠️ How to Run  

```bash
# 1. Clone the repo:
git clone https://github.com/YOUR_USERNAME/Oil-Spill-Detection.git
cd Oil-Spill-Detection
```

## 📄 Paper  

This project is based on our peer-reviewed research paper:  
**“Oil Spill Detection Using Deep Learning: A Comparison of U-Net, DeepLabV3 & PSPNet”**  
_Accepted at the **16th International IEEE Conference on Communication, Networks and Satellite (Comnetsat), 2024**_

### 📘 Citation (BibTeX)
```bibtex
@inproceedings{oilspill2024,
  title={Oil Spill Detection Using Deep Learning: A Comparison of U-Net, DeepLabV3 \& PSPNet},
  author={Harshit and Devroop Das and Gavish Kumar and G. Saranya},
  booktitle={2024 16th International IEEE Conference on Communication, Networks and Satellite (Comnetsat)},
  year={2024},
  organization={IEEE}
}

