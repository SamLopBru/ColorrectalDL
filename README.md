# Tissue Classification in Histological Colorectal Images Using Deep Learning

This project marked our first steps in Deep Learning. The goal was to classify colorectal histological image patches into 8 tissue classes:

- **Debris**
- **Mucosa**
- **Tumor**
- **Adipose**
- **Stroma**
- **Lympho**
- **Empty**
- **Complex**

To achieve this, we trained three state-of-the-art CNN architectures: **InceptionV3**, **ResNet50**, and **VGG19**. Each model was trained using two techniques:

- **Transfer Learning**
- **Fine-Tuning**

### 🔍 Results

The best performance was achieved using **fine-tuned VGG19**, as shown in the confusion matrix below:

![Confusion Matrix](https://github.com/user-attachments/assets/480df9eb-d612-4628-bb1f-cef05ab973c4)

We also calculated several performance metrics:

| Model       | Accuracy | Loss  | F1-Score | Recall | Precision |
|-------------|----------|-------|----------|--------|-----------|
| **VGG19**   | **94.2** | **0.17** | **0.943** | **0.945** | **0.943** |
| ResNet50V2  | 92.8     | 0.26  | 0.928    | 0.932  | 0.930     |
| InceptionV3 | 88.8     | 0.38  | 0.891    | 0.890  | 0.895     |

---

### 🧠 Whole Slide Inference

After training the models with patches, we applied the best one (VGG19) on full histological images using a **sliding window** approach. This allowed us to segment multiple tissue types within a single image.

To reduce prediction noise, an **opening filter** was applied post-inference. The image below shows the results:

- **Column 1:** Original image  
- **Column 2:** Ground truth segmentation  
- **Columns 3+:** Predictions using different sliding window strides (lower stride = smoother segmentation, but higher computation time, following a quadratic relationship)

![Segmentation](https://github.com/user-attachments/assets/e940659e-973c-4daa-bca9-f6f84fdd497c)

---

### 📚 Dataset

We used the dataset:  
**[Collection of textures in colorectal cancer histology](https://zenodo.org/records/53169#.XGZemKwzbmG)**

---

### 👥 Authors

This project was developed by:

- Francisco José Valiente  
- Rubén Martínez

