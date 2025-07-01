### **Multimedia Engineering**  
#### **3. Machine Learning with Neural Networks**   

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

### **Introduction to Neural Networks**  
**Neural Networks (NNs)** are a type of machine learning model capable of **non-linear transformations** (mappings) of input data to output.  
- **Universal Approximation Theorem**: A sufficiently large NN can approximate any continuous function.  
- **Example**:  
  - Input: \( x_1, x_2 \) → Output: \( y_1, y_2 \).  

---

### **Neural Networks as Functions**  
An NN is essentially a **function** that maps inputs to outputs.  
- **Example 1**: Simple quadratic function \( f(x) = x^2 - 2x + 1 \).  
- **Example 2**: Used car price estimation based on mileage (\( x \)) and year (\( y \)).  
- **Example 3**: Dog/cat classifier (image → numerical input → output probabilities for classes).  

---

### **Modality Transformation**  
NNs can convert between different data modalities:  
- **Image → Text**: Object recognition (e.g., "cat").  
- **Speech → Text**: Speech recognition (e.g., "Yamanashi University").  
- **Text → Text**: Machine translation (e.g., "I am a student").  

---

### **Parameters in Functions**  
For a linear function \( f(x) = wx + b \):  
- **\( w \)**: Weight (slope).  
- **\( b \)**: Bias (intercept).  
- **Goal**: Find \( w \) and \( b \) that best fit the given dataset.  

---

### **Key Terminology**  
- **Model**: A function \( y = f(x) \) with parameters learned from training data.  
- **Training**: Adjusting parameters to minimize error between predictions and true labels.  
- **Trained Model**: A model with optimized parameters for inference.  
- **Inference**: Using the trained model to predict outputs for new inputs.  

---

### **Regression vs. Classification**  
- **Regression**: Predicts continuous values (e.g., stock prices, power consumption).  
- **Classification**: Predicts discrete categories (e.g., image labels, speech recognition).  

---

### **What Machine Learning Can Do**  
1. **Classification**: Identify categories (e.g., image recognition).  
2. **Regression**: Predict numerical values (e.g., sales forecasts).  
3. **Clustering**: Group similar data points.  
4. **Compression**: Reduce data size while preserving information.  

---

### **Neural Network Computation**  
- **Computational Graph**: Represents NN operations as nodes (values) and links (weights).  
- **Bias Term**: An additional node (value = 1) with weight \( b \).  
- **Layers**:  
  - **Input Layer**: Receives data.  
  - **Hidden Layers**: Perform non-linear transformations.  
  - **Output Layer**: Produces predictions.  

---

### **Activation Functions**  
Introduce non-linearity to enable complex mappings:  
- **Sigmoid**: Maps inputs to (0, 1).  
- **ReLU**: Outputs \( x \) if \( x > 0 \); else 0.  
- **Softmax**: Normalizes outputs to probabilities (used in classification).  

---

### **Deep Neural Networks (DNNs)**  
- **DNNs**: NNs with multiple hidden layers.  
- **Why Depth?**: Deeper networks can model more complex functions.  
- **Caution**: Deeper networks require more data and careful tuning to avoid overfitting.  

---

### **Training Process**  
1. **Prepare Dataset**: Split into training and validation sets (e.g., 80:20).  
2. **Design Model**: Choose layers, nodes, and activation functions.  
3. **Define Loss Function**:  
   - **Regression**: Mean Squared Error (MSE).  
   - **Classification**: Cross-Entropy Loss.  
4. **Train**: Adjust parameters using optimization (e.g., gradient descent).  

---

### **Backpropagation**  
- **Forward Pass**: Compute predictions.  
- **Loss Calculation**: Compare predictions to true labels.  
- **Backward Pass**: Update weights using gradients of the loss.  

---

### **Optimizers**  
- **SGD (Stochastic Gradient Descent)**: Basic but effective.  
- **Adam**: Adapts learning rates automatically.  
- **Momentum SGD**: Avoids local minima by adding "inertia".  

---

### **Batch vs. Mini-Batch Training**  
- **Batch**: Uses all data for each update (slow, stable).  
- **Mini-Batch**: Uses subsets (faster, common in practice).  
- **Epoch**: One full pass through the training data.  
- **Iteration**: One update step (e.g., 10 iterations/epoch for 100 data points and batch size 10).  

---

### **Hyperparameters**  
Critical settings that affect training:  
- **Learning Rate**: Step size for weight updates.  
- **Batch Size**: Number of samples per update.  
- **Layer/Node Count**: Model complexity.  

---

### **Exercise**  
1. Explain the NN training process using keywords: *inference, loss, backpropagation*.  
2. List challenges in NN training (e.g., overfitting, hyperparameter tuning).  
3. Submit answers as a PDF with your student ID by the deadline.  

---

### **Key Takeaways**  
- NNs are powerful function approximators.  
- Training involves iterative optimization of parameters.  
- Proper design and tuning are essential for success.  
