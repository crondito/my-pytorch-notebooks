### **Summary of Class 6: "Convolutional Neural Networks (CNN) for Image Processing"**

#### **1. Introduction to CNNs**
- **What is a CNN?**  
  A Convolutional Neural Network (CNN) is a type of deep learning model specialized for processing structured grid data like images. It excels at tasks such as image classification, object detection, and more.  
  - **Key components**:  
    - **Convolutional Layers**: Extract local features (e.g., edges, textures) using filters (kernels).  
    - **Pooling Layers**: Reduce spatial dimensions (e.g., max-pooling retains the most prominent features).  
    - **Fully Connected Layers**: Classify features into output categories (e.g., digit classes in MNIST).  

- **Why CNNs?**  
  - **Hierarchical Feature Learning**:  
    - Early layers detect simple patterns (edges, colors).  
    - Deeper layers combine these into complex structures (e.g., shapes, objects).  
  - **Parameter Efficiency**: Shares weights across spatial locations, reducing parameters compared to dense layers.  

---

#### **2. CNN Operations**
- **Convolution Process**:  
  - **Filter/Kernel**: A small matrix (e.g., 3×3) slid over the input image to compute feature maps.  
  - **Stride**: Step size of the filter. Larger strides shrink output size.  
  - **Padding**: Adds zeros around the input to preserve spatial dimensions (`same` padding).  

- **Pooling**:  
  - **Max Pooling**: Takes the maximum value in a window (e.g., 2×2) to downsample feature maps.  
  - **Average Pooling**: Takes the mean value.  

- **Activation Functions**:  
  - **ReLU** is commonly used to introduce non-linearity.  

---

#### **3. Practical Implementation**
- **TensorFlow/Keras Workflow**:  
  1. **Data Preparation**:  
     - Use `tf.data.Dataset` to load, shuffle, batch, and preprocess images (e.g., normalize pixel values to [0, 1]).  
     - Example:  
       ```python
       train_ds = tf.data.Dataset.from_tensor_slices((x_train, y_train))  
       train_ds = train_ds.shuffle(len(x_train)).batch(32).map(convert_data)  
       ```  
  2. **Model Architecture**:  
     - Stack `Conv2D` and `MaxPooling2D` layers, followed by `Dense` layers.  
     - Example:  
       ```python
       model = Sequential([  
           Conv2D(64, (5, 5), activation='relu', padding='same'),  
           MaxPooling2D((2, 2)),  
           Flatten(),  
           Dense(10, activation='softmax')  
       ])  
       ```  
  3. **Training/Inference**:  
     - Use `model.fit()` for training and `model.predict()` for inference.  

- **GPU Acceleration**:  
  - GPUs speed up CNN training via parallel computation (e.g., matrix multiplications).  

---

#### **4. Assignment: MNIST Digit Recognition**
- **Task**:  
  Train a CNN to classify handwritten digits (0–9) from the MNIST dataset and test it on custom-drawn digits.  

- **Steps**:  
  1. **Create Custom Images**:  
     - Use Paint or similar software to draw digits (0–9) in **black on white background**.  
     - Save as `0.jpg`, `1.jpg`, ..., `9.jpg`.  
  2. **Preprocess Images**:  
     - Resize to 28×28 pixels (MNIST format).  
     - Invert colors (MNIST uses white-on-black).  
     - Normalize pixel values (divide by 255).  
  3. **Model Evaluation**:  
     - Load the trained CNN and predict labels for your images.  
     - Calculate accuracy (correct predictions / total images).  

- **Example Output**:  
  ```plaintext
  Digit 0: Predicted 0 (Correct) 
  Digit 1: Predicted 1 (Correct) 
  ...  
  Accuracy: 90%  
  ```

---

#### **Key Takeaways**
- CNNs automate feature extraction for images, outperforming traditional methods.  
- Critical hyperparameters: filter size, stride, padding, pooling.  
- Use `tf.data` for efficient data pipelines and GPUs for faster training.  
