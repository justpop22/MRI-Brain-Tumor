# Brain MRI Segmentation using U-Net

This repository contains a deep learning project for Brain MRI Segmentation to identify lower-grade gliomas (LGG) using the U-Net architecture.

The model is built using TensorFlow and Keras, and it is trained on the brain tumor segmentation dataset available on Kaggle.

📌 Project Overview
  - Objective: Perform semantic segmentation on brain MRI slices to accurately outline glioma tumor regions.
  - Architecture: Custom U-Net model implemented in TensorFlow/Keras.
  - Input Data: 3-channel brain MRI slices ($256 \times 256$ pixels).
  - Output: Binary segmentation masks identifying the presence and location of tumors.

📊 Dataset:
 The project utilizes the LGG MRI Segmentation Dataset.
  - Source: [Kaggle - LGG MRI Segmentation](https://www.kaggle.com/datasets/mateuszbuda/lgg-mri-segmentation)
  - Content: Brain MRI slices from 110 patients along with their corresponding manually-segmented tumor masks.

🛠️ Project Workflow
1. Library Configuration:
   The notebook imports foundational libraries for computer vision, data manipulation, evaluation, and deep learning:
     - Framework: TensorFlow & Keras
     - Image Processing: OpenCV & Numpy
     - Data & Visualization: Pandas, Matplotlib, and Seaborn
     - Metrics: Scikit-Learn
2. Data Pipeline & DataFrame Creation:
   The dataset is processed by pairing each MRI scan with its corresponding target segmentation mask. A Pandas DataFrame is generated containing the exact paths of the images, their masks, and a binary classification label (1 for tumor present, 0 for no tumor) based on the pixel values of the mask.

📈 Exploratory Data Analysis (EDA):
   1. Class Distribution:
        The dataset contains a mix of MRI slices that contain tumors and slices that do not.
   2. Visualizing Samples:
        The script samples random slices of both Tumor (Label: 1) and Non-Tumor (Label: 0) classes to inspect the quality of the scans and the ground truth masks before feeding them into the network.

🧠 Model Architecture (U-Net):
The model leverages a traditional U-Net design optimized for medical image segmentation, consisting of:
  1. Contracting Path (Encoder): Successive blocks of convolutional layers, batch normalization, and max-pooling to extract structural features.
  2. Expanding Path (Decoder): Up-sampling (transposed convolutions or bilinear upsampling) concatenated with corresponding high-resolution features from the encoder to localized spatial structures.
  3. Loss Function & Callbacks: Optimized using Adam with training monitored via validation performance, employing callbacks like EarlyStopping, ModelCheckpoint, and ReduceLROnPlateau.

# OutPut
<img width="1043" height="500" alt="BrainTumor" src="https://github.com/user-attachments/assets/186dc794-0b11-48d9-989d-5e4a28d10a5e" />
