# Satellite Imagery Data - Download Instructions

Due to file size limitations, satellite imagery is not included in this repository.

## 📥 Download from Kaggle

**Dataset**: [Satellite Images to Predict Poverty in Africa](https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica)

### Method 1: Manual Download

1. Visit: https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica
2. Click "Download" button
3. Extract the `nigeria_archive` folder
4. Place it in `data/satellite_images/`

### Method 2: Kaggle API (Recommended)

```bash
# 1. Install Kaggle API
pip install kaggle

# 2. Get your Kaggle API credentials
# - Go to https://www.kaggle.com/account
# - Scroll to "API" section
# - Click "Create New API Token"
# - Download kaggle.json

# 3. Setup credentials
mkdir -p ~/.kaggle
mv ~/Downloads/kaggle.json ~/.kaggle/
chmod 600 ~/.kaggle/kaggle.json

# 4. Download dataset
cd <project-root>
kaggle datasets download -d sandeshbhat/satellite-images-to-predict-povertyafrica

# 5. Extract
unzip satellite-images-to-predict-povertyafrica.zip -d data/

# 6. Organize
mv data/nigeria_archive/* data/satellite_images/
```

## 📊 Dataset Specifications

- **Format**: JPEG/PNG satellite images
- **Coverage**: Nigeria
- **Size**: ~[X] GB (compressed)
- **Images**: Georeferenced with GPS coordinates
- **Features**: Infrastructure, roads, buildings, vegetation, urban/rural areas

## 🗂️ Expected Directory Structure

After download, your structure should look like:

```
data/
├── satellite_images/
│   ├── image_001.jpg
│   ├── image_002.jpg
│   ├── ...
│   └── coordinates.csv (if included)
├── poverty_data/
│   └── poverty_stats.csv
└── labeled_images/
    └── ...
```

## ⚠️ Important Notes

1. **Total size**: The full dataset may be several GB
2. **Storage**: Ensure you have sufficient disk space
3. **Git**: These files are excluded in `.gitignore`
4. **Citation**: Always cite the dataset when publishing results

## 📝 Citation

```
Sandesh Bhat. (2021). Satellite Images to Predict Poverty in Africa. 
Kaggle. https://www.kaggle.com/datasets/sandeshbhat/satellite-images-to-predict-povertyafrica
```

## 📧 Questions?

If you encounter issues downloading the data, contact:
- Email: mulayemuhammad@gmail.com
- GitHub: [@MulayeMuhammad](https://github.com/MulayeMuhammad)
