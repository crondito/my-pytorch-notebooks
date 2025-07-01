### **Multimedia Engineering**  
#### **5. Image Processing and Neural Networks for Image Input**  

---

### **Lecture Outline**  
1. **Introduction**: Multimedia engineering and AI overview.  
2. **Python Programming Basics**.  
3. **Machine Learning with Neural Networks**.  
4. **Neural Network Programming Basics**.  
5. **Image Processing and Neural Networks for Image Input**.  
6. **Convolutional Neural Networks (CNNs) for Images**.  
7. **Practical Application**: Resistor classification/regression using custom data.  
8. **Training Visualization and Overfitting Prevention**.  
9. **Time-Series Data with Neural Networks**.  
10. **Audio/Speech Signal Processing**.  
11. **Natural Language Processing Basics**.  

*Content may adjust based on student progress.*  

---

### **Today’s Topics**  
1. **Image Fundamentals**:  
   - Color spaces (RGB, grayscale, binary).  
   - Image formats (BMP, JPEG, PNG, HEIF).  
   - Video formats (MP4, AVI, MOV).  
2. **Basic Image Processing**:  
   - Grayscale conversion.  
   - Binarization.  
   - Filters (blur, sharpen, edge detection).  
3. **Deep Learning for Images**:  
   - Preprocessing for neural networks.  
   - **MNIST handwritten digit classification**.  

---

### **Image Representation**  
#### **Color Spaces**  
- **RGB**: 24-bit color (8 bits per channel → 16.7 million colors).  
- **Grayscale**: 8-bit (0=black, 255=white).  
- **Binary**: 1-bit (0 or 1).  

#### **Image Formats**  
| Format  | Compression | Colors          | Use Case               |  
|---------|-------------|-----------------|-----------------------|  
| BMP     | None        | 16.7M           | High-quality storage  |  
| JPEG    | Lossy       | 16.7M           | Photos                |  
| PNG     | Lossless    | 16.7M + alpha   | Graphics/transparency |  
| HEIF    | High        | 16-bit depth    | iOS photos            |  

#### **Video Formats**  
- **MP4**: H.264/H.265 + AAC (universal compatibility).  
- **AVI**: Uncompressed (large files).  
- **MOV**: Apple’s format (H.265 + AAC).  

---

### **Image Processing Techniques**  
1. **Grayscale Conversion**:  
   - Convert RGB to luminance: `Y = 0.299R + 0.587G + 0.114B`.  
2. **Binarization**:  
   - Thresholding (e.g., pixel > 127 → white, else black).  
3. **Filters**:  
   - **Blur**: Gaussian or mean filter.  
   - **Sharpen**: Edge enhancement.  
   - **Edge Detection**: Sobel or Canny filters.  

**Python Libraries**:  
- **Pillow**: Basic operations (resize, crop).  
- **OpenCV**: Advanced CV tasks (real-time processing).  

---

### **Deep Learning for Images**  
#### **MNIST Dataset**  
- **Task**: Classify handwritten digits (0–9).  
- **Data**: 70,000 images (28×28 pixels, grayscale).  
- **Preprocessing**:  
  - Flatten images to 784D vectors.  
  - Normalize pixel values to [0, 1] (`x /= 255`).  

#### **Neural Network Architecture**  
```python
import tensorflow as tf

# Define model (Functional API)
input_layer = tf.keras.layers.Input(shape=(28, 28))
flatten = tf.keras.layers.Flatten()(input_layer)
hidden = tf.keras.layers.Dense(512, activation='relu')(flatten)
output = tf.keras.layers.Dense(10, activation='softmax')(hidden)

model = tf.keras.Model(inputs=input_layer, outputs=output)
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
```

#### **Training**  
- **Split**: 60k training, 10k validation.  
- **Output**: 10D probability vector (softmax).  

---

### **Exercises**  
1. **Image Processing**:  
   - Submit a Jupyter notebook (`ipynb`) with grayscale conversion, binarization, and filtering results.  
2. **MNIST Classification**:  
   - Train a model with/without normalization. Compare accuracy.  
   - Include training curves in the notebook.  

---

### **Key Takeaways**  
- **Image Formats**: Choose based on use case (JPEG for photos, PNG for graphics).  
- **Preprocessing**: Normalization is critical for NN performance.  
- **MNIST**: A foundational task for learning image-based deep learning.  

**Next**: Convolutional Neural Networks (CNNs) for advanced image tasks!
