### **Multimedia Engineering**  
#### **4. Neural Network Programming Basics**  

---

### **Lecture Outline**  
1. **Introduction**: Overview of multimedia engineering and artificial intelligence.  
2. **Python Programming Basics**.  
3. **Machine Learning with Neural Networks**.  
4. **Neural Network Programming Basics**.  
5. **Image Processing and Neural Networks for Image Input**.  
6. **Convolutional Neural Networks (CNNs) for Image Tasks**.  
7. **Image Processing: Resistor Classification/Regression Models (Using Your Own Data)**.  
8. **Visualizing Training, Overfitting Prevention, and Data Augmentation (Midterm Report)**.  
9. **Neural Networks for Time-Series Data**.  
10. **Sound/Audio Signal Processing Basics**.  
11. **Audio Signal Classification: Speaker Recognition/Word Classification**.  
12. **Natural Language Processing (Morphological Analysis) and Word Embeddings with Neural Networks**.  
13. **Language Models and Automatic Text Generation with Recurrent Neural Networks (RNNs)**.  
14. **Encoder-Decoder Models for Machine Translation**.  
15. **Creating Training Data and Original Tasks (Final Report)**.  

*Note: Content may be adjusted based on student progress and understanding.*  

---

### **Deep Learning Programming**  
#### **Frameworks in Python**  
1. **TensorFlow/Keras** (Google)  
   - Suitable for practical applications.  
   - Simplified usage since Version 2.  
   - Keras is now integrated into TensorFlow.  
2. **PyTorch** (Facebook)  
   - Popular among researchers.  
   - Intuitive and flexible.  
3. **Chainer** (Japanese company)  
   - Discontinued in December 2020 (merged into PyTorch).  

**In this course, we focus on TensorFlow/Keras.**  

---

### **TensorFlow vs. PyTorch: Which to Learn?**  
- **TensorFlow**: Better for commercial applications (e.g., web/mobile apps).  
- **PyTorch**: Preferred for research (easier to implement cutting-edge techniques).  
- **Learning Path**: Beginners should start with TensorFlow → PyTorch.  
- **Key Takeaway**: Proficiency in both frameworks is ideal.  

---

### **Neural Network Training Workflow**  
1. Prepare training dataset.  
2. Design the model.  
3. Define the loss function.  
4. Train the model.  

#### **TensorFlow Implementation**  
- Data formats: `NumPy` or `tf.Tensor` (preferred).  
- Model design:  
  - Sequential API (beginners).  
  - Functional API (intermediate).  
  - Subclassing (advanced).  
- Training: Use `model.fit()`.  

#### **PyTorch Implementation**  
- Data format: Convert `NumPy` to `torch.Tensor`.  
- Model design: Define a class with `forward()` method.  
- Training: Use `Trainer.fit()`.  

---

### **Practice Problem: XOR Circuit with Neural Networks**  
- **Task**: Implement an XOR gate using a neural network (2 inputs, 1 output).  
- **Truth Table**:  
  | Input | Output |  
  |-------|--------|  
  | 0, 0  | 0      |  
  | 0, 1  | 1      |  
  | 1, 0  | 1      |  
  | 1, 1  | 0      |  

#### **Model Architecture**  
- Input layer: 2 nodes.  
- Hidden layer: 2 nodes (ReLU activation).  
- Output layer: 2 nodes (Softmax activation).  

#### **Code Example (TensorFlow)**  
```python
import tensorflow as tf

# Training data
trainx = np.array([[0,0], [0,1], [1,0], [1,1]], dtype=np.float32)
trainy = np.array([0, 1, 1, 0], dtype=np.int32)

# Model design
model = tf.keras.Sequential([
    tf.keras.layers.Dense(2, input_shape=(2,), activation='relu'),
    tf.keras.layers.Dense(2, activation='softmax')
])

# Compile and train
model.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
model.fit(trainx, trainy, epochs=1000, batch_size=4)
```

---

### **Exercise: 4-Bit Counter Neural Network**  
- **Task**: Design a neural network to count the number of `1`s in a 4-bit input.  
- **Output**: One-hot vector (5 classes: 0 to 4).  
- **Example**:  
  - Input: `[1,0,1,1]` → Output: `[0,0,0,1,0]` (3 `1`s).  
- **Requirements**:  
  - Achieve 100% accuracy.  
  - Submit as an `.ipynb` file with student ID in the filename.  

---

### **Additional Notes**  
- **TensorFlow API Documentation**: [Link](https://www.tensorflow.org/api_docs/python/tf?hl=JA)
