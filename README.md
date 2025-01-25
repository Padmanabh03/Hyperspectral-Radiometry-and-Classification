# **Hyperspectral Radiometry and Pixel-Wise Classification**

This project explores radiometric analysis and machine learning techniques for **hyperspectral imaging** using the **WHU-Hi dataset**. The focus is on converting raw hyperspectral data into actionable insights through **radiance and irradiance computations**, **pixel-wise classification**, and **segmentation**.

---

## **Project Highlights**
- Perform **radiometric calibration** to compute radiance and irradiance.
- Analyze **spectral signatures** of individual pixels.
- Classify each pixel into specific land-cover types (e.g., crops, water, or buildings) using **Random Forest**.
- Generate **pixel-wise classification maps** for land-cover segmentation.

---

## **Dataset Overview**
The **WHU-Hi dataset** contains hyperspectral images acquired from UAV-borne sensors. It includes three subsets, each representing different geographical and environmental conditions:
1. **LongKou**: Agricultural scene with six crop types (e.g., corn, cotton).
2. **HanChuan**: Rural-urban area with seven crop types and buildings.
3. **HongHu**: Complex agricultural scene with diverse crops.

### **Data Properties**
- **Spectral Bands**: 270 (400–1000 nm).
- **Spatial Resolution**: Varies between subsets (e.g., 0.043 m/pixel for HongHu).
- **Ground Truth**: Class labels for each pixel.

---

## **Key Features**

### **1. Radiometric Analysis**
- **Radiance**:
  - Converts raw digital numbers (DN) to radiance using calibration parameters.
  - Formula: \( \text{Radiance} = (\text{DN} - \text{offset}) \cdot \text{gain} \).
- **Irradiance**:
  - Computes the total reflected light energy across all spectral bands.
  - Formula: \( \text{Irradiance} = \sum_{i=1}^{B} \text{Radiance}_i \cdot \text{Bandwidth}_i \).

![Spectral Band 50](file-YZAQywxx3sJmbz4cCpyVkj)

**Description**: This image shows the intensity distribution in spectral band 50, highlighting features like water bodies and vegetation.

---

### **2. Spectral Analysis**
- Visualizes the spectral signature of individual pixels to understand material properties.

![Spectral Signature](file-CZSADxHfmnZi2NA8cyeXMU)

**Description**: The spectral signature of a pixel (row 100, column 100) is plotted across 270 bands, showing distinct peaks and troughs corresponding to specific wavelengths.

---

### **3. Pixel-Wise Classification**
- Trains a **Random Forest Classifier** to classify pixels based on their spectral signatures.
- Generates a **confusion matrix** to evaluate performance.

![Confusion Matrix](file-NQdyq9dPvHFrg9z5py9ejM)

**Description**: The confusion matrix shows the classifier's accuracy for each class. The overall accuracy is **98%**, with high precision and recall for most classes.

---

### **4. Pixel-Wise Segmentation**
- Predicts classes for all pixels in the hyperspectral image.
- Generates a classification map to visualize spatial distribution.

![Classification Map](file-RrqvdYSzbj8w4iPXTVJnhi)

**Description**: This map displays the predicted land-cover types, revealing distinct spatial patterns for different classes (e.g., crops, water).

---

## **Performance Metrics**
- **Precision**: Measures how many predicted pixels are correct.
- **Recall**: Measures how many actual pixels are correctly identified.
- **F1-Score**: Harmonic mean of precision and recall.

### **Classification Report**
| Class | Precision | Recall | F1-Score | Support |
|-------|-----------|--------|----------|---------|
| 1     | 0.99      | 0.99   | 0.99     | 10459   |
| 2     | 0.91      | 0.93   | 0.92     | 2512    |
| 3     | 0.98      | 0.81   | 0.89     | 921     |
| 4     | 0.97      | 0.99   | 0.98     | 18905   |
| 5     | 0.92      | 0.78   | 0.85     | 1270    |
| 6     | 0.99      | 1.00   | 1.00     | 3588    |
| 7     | 1.00      | 1.00   | 1.00     | 19965   |
| 8     | 0.95      | 0.94   | 0.95     | 2177    |
| 9     | 0.96      | 0.91   | 0.94     | 1566    |

**Overall Accuracy**: 98%  
**Macro Avg F1-Score**: 94%  
**Weighted Avg F1-Score**: 98%

---

## **Applications**
1. **Precision Agriculture**:
   - Monitor crop health, detect diseases, and optimize farming practices.
2. **Environmental Monitoring**:
   - Analyze land-cover changes and monitor urban expansion.
3. **Remote Sensing**:
   - Detect natural disasters and study their impacts.
4. **Material Analysis**:
   - Identify unique spectral properties of different materials.

---

