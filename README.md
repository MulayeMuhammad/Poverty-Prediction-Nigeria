# Predicting Poverty Levels from Satellite Imagery in Nigeria using Deep Neural Networks

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.0%2B-orange)](https://www.tensorflow.org/)
[![Deep Learning](https://img.shields.io/badge/Deep%20Learning-CNN-red)](https://github.com/MulayeMuhammad/Poverty-Prediction-Nigeria)
[![Status](https://img.shields.io/badge/Status-In%20Progress-yellow)](https://github.com/MulayeMuhammad/Poverty-Prediction-Nigeria)

## 🌍 Project Overview

Poverty remains a major challenge in many developing countries, and access to detailed, up-to-date information is crucial for guiding public policies and humanitarian interventions. Nigeria, as Africa's largest economy, faces significant disparities in living standards, particularly in rural areas.

This project leverages **Deep Learning** and **satellite imagery** to develop an automated system for predicting and mapping poverty levels across different regions of Nigeria, providing a cost-effective alternative to traditional household surveys.

---

## 🎯 Objectives

1. **Predict poverty levels** from satellite imagery using Deep Neural Networks (DNN) and Convolutional Neural Networks (CNN)
2. **Identify the most affected areas** by poverty across Nigeria
3. **Provide detailed insights** for strategic decision-making
4. **Reduce costs** associated with traditional surveys while increasing analysis accuracy
5. **Create a scalable tool** that can be applied to other countries or regions

---

## 🚀 Why This Matters

### Problem Statement
Traditional poverty assessment methods rely on:
- **Expensive household surveys** conducted every few years
- **Limited geographic coverage** due to accessibility constraints
- **Time-consuming data collection** processes
- **Outdated information** by the time analysis is complete

### Our Solution
By combining satellite imagery with machine learning:
- ✅ **Near real-time monitoring** of poverty indicators
- ✅ **Complete geographic coverage** including remote areas
- ✅ **Cost-effective** compared to traditional surveys
- ✅ **Scalable** to other regions and countries
- ✅ **Objective and consistent** measurements

---

## 📊 Dataset

### Satellite Imagery
- **Source**: Kaggle - [Satellite Images to Predict Poverty in Africa](https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica)
- **Dataset**: Nigeria Archive (`nigeria_archive`)
- **Coverage**: Multiple regions across Nigeria
- **Format**: Georeferenced satellite images with GPS coordinates
- **Features captured**: Infrastructure, natural environment, urban development, vegetation, roads, buildings, nighttime lights
- **Image Format**: High-resolution satellite imagery

### Poverty Data
- **Source**: Integrated with satellite imagery dataset
- **Labels**: Poverty levels/indicators from survey data
- **Annotation**: Images are georeferenced and linked to poverty statistics
- **Coverage**: Representative sample across Nigerian regions

### Data Annotation Process
Images are named according to their geographic coordinates (latitude, longitude). These coordinates are cross-referenced with official poverty statistics from the National Bureau of Statistics to assign each image a specific poverty level, creating an annotated dataset that combines:
- Visual representation of the environment (satellite images)
- Corresponding poverty level labels

---

## 🏗️ Architecture

### Model Overview

```
Input: Satellite Image (RGB)
    ↓
Convolutional Layers (Feature Extraction)
    ↓
Pooling Layers (Dimensionality Reduction)
    ↓
Fully Connected Layers (Classification)
    ↓
Output: Poverty Level Prediction
```

### Technical Stack

**Deep Learning Framework**:
- TensorFlow / Keras
- PyTorch (if applicable)

**CNN Architecture**:
- Custom CNN architecture
- Transfer Learning with pre-trained models (VGG16, ResNet50, InceptionV3)
- Data augmentation techniques

**Libraries & Tools**:
```python
- tensorflow / keras    # Deep learning
- numpy                 # Numerical computations
- pandas                # Data manipulation
- matplotlib / seaborn  # Visualization
- scikit-learn          # ML utilities
- opencv-cv2            # Image processing
- rasterio / gdal       # Geospatial data
- geopandas             # Geographic data frames
```

---


## 🔬 Methodology

### 1. Data Collection & Annotation
- Collect satellite imagery with GPS coordinates
- Cross-reference coordinates with National Bureau of Statistics poverty data
- Assign poverty level labels to each image
- Create train/validation/test splits

### 2. Image Preprocessing
```python
- Normalization (0-1 scaling)
- Resizing to uniform dimensions
- Data augmentation (rotation, flipping, brightness adjustment)
- Color space conversion (if needed)
```

### 3. Model Development
- Design CNN architecture for image classification
- Implement transfer learning with pre-trained models
- Fine-tune hyperparameters
- Apply regularization techniques (dropout, L2)

### 4. Training
```python
- Loss function: Categorical Crossentropy (multi-class) or Binary Crossentropy
- Optimizer: Adam / SGD with momentum
- Learning rate scheduling
- Early stopping based on validation loss
- Model checkpointing
```

### 5. Evaluation
- Accuracy, Precision, Recall, F1-Score
- Confusion Matrix analysis
- ROC-AUC curves (if binary classification)
- Spatial analysis of predictions

### 6. Deployment & Mapping
- Generate poverty maps for Nigeria
- Identify high-poverty regions
- Create interactive visualizations
- Export results for policy makers

---


### Deliverables
1. ✅ Trained CNN model for poverty prediction
2. ✅ Comprehensive poverty maps of Nigeria
3. ✅ Analysis report with regional insights
4. ✅ Reusable pipeline for future updates

---


---

## 💡 Key Features

### 1. Automated Poverty Assessment
- No need for expensive field surveys
- Real-time or near real-time monitoring capability
- Consistent and objective measurements

### 2. Geographic Coverage
- Complete coverage of Nigeria including remote areas
- High spatial resolution analysis
- Region-specific insights

### 3. Cost-Effectiveness
- Significantly cheaper than traditional surveys
- Can be updated frequently
- Scalable to other countries

### 4. Policy Impact
- Targeted resource allocation
- Evidence-based decision making
- Monitoring of poverty reduction programs

---

## 🗺️ Sample Visualizations

### Poverty Distribution Map
<img src="figure1.png" width="600" alt="Income and Democracy Cross-Section">

---



## ⚠️ Important Notes

### Large Files
The `data/satellite_images/` directory contains large satellite image files that are **not included in this repository** due to GitHub's file size limitations.

**To access the dataset**:

1. **Download from Kaggle**:
   ```bash
   # Visit: https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica
   # Download the nigeria_archive folder
   ```

2. **Using Kaggle API** (Recommended):
   ```bash
   # Install Kaggle API
   pip install kaggle
   
   # Configure Kaggle credentials (from kaggle.com/account)
   mkdir -p ~/.kaggle
   # Place your kaggle.json in ~/.kaggle/
   
   # Download dataset
   kaggle datasets download -d sandeshbhat/satellite-images-to-predict-povertyafrica
   unzip satellite-images-to-predict-povertyafrica.zip -d data/
   ```

3. **Place the data**:
   ```bash
   # Extract nigeria_archive to:
   data/satellite_images/
   ```

**Dataset Citation**:
```
Sandesh Bhat. (2021). Satellite Images to Predict Poverty in Africa. 
Kaggle. https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica
```

### .gitignore Configuration
```
# Large data files
data/satellite_images/*.tif
data/satellite_images/*.tiff
data/satellite_images/*.img

# Model checkpoints
models/*.h5
models/*.keras

# Temporary files
*.pyc
__pycache__/
.ipynb_checkpoints/
```

---


---

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 📞 Contact

**Moulaye Ahmed Mohammed Brahim**

- 🌐 Portfolio: [mulayemuhammad.github.io/Moulaye_DS_Portfolio](https://mulayemuhammad.github.io/Moulaye_DS_Portfolio/)
- 💼 LinkedIn: [Moulaye Ahmed MUHAMMAD](https://www.linkedin.com/in/moulaye-ahmed-muhammad/)
- 🐙 GitHub: [@MulayeMuhammad](https://github.com/MulayeMuhammad)
- 📧 Email: mulayemuhammad@gmail.com
- 🐦 Twitter: [@MuhammadMoulaye](https://twitter.com/MuhammadMoulaye)

---

## 🙏 Acknowledgments

- **Kaggle** for providing the [Satellite Images to Predict Poverty in Africa](https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica) dataset
- **Sandesh Bhat** for compiling and sharing the Nigeria satellite imagery dataset
- **National Bureau of Statistics of Nigeria** for poverty statistics used in data annotation
- **INSEA** (Institut National de la Statistique et de l'Économie Appliquée) for academic support
- Open-source community for excellent deep learning tools

---

## 📚 References

1. Jean, N., et al. (2016). "Combining satellite imagery and machine learning to predict poverty." *Science*, 353(6301), 790-794.
2. Yeh, C., et al. (2020). "Using publicly available satellite imagery and deep learning to understand economic well-being in Africa." *Nature Communications*, 11(1), 1-11.
3. Head, A., et al. (2017). "Can human development be measured with satellite imagery?" *ICTD*, 1-11.
4. Bhat, S. (2021). "Satellite Images to Predict Poverty in Africa." Kaggle Dataset. https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica

---



<p align="center">
  <strong>Building a data-driven approach to poverty alleviation in Africa 🌍</strong>
</p>

<p align="center">
  Made with ❤️ by <a href="https://github.com/MulayeMuhammad">Moulaye Ahmed</a>
</p>
