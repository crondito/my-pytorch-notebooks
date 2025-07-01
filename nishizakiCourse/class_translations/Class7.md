### **Summary of Class 7: Resistor Classification and Regression Models**  

#### **Class Overview**  
This class focuses on **image-based classification and regression tasks** using neural networks, specifically applied to **resistor images**. Students will:  
1. Work with their own dataset of resistor images.  
2. Use **`tf.Data`** to dynamically load and preprocess images in batches.  
3. Build **two models**:  
   - A **classification model** to categorize resistors into predefined classes (e.g., 150Ω, 160Ω, etc.).  
   - A **regression model** to directly predict the resistance value (in Ω) from images.  

---

### **Key Concepts**  

#### **1. Dataset Structure**  
- The dataset is organized into folders:  
  - `train/` (training data)  
  - `valid/` (validation data)  
  - `test/` (testing data)  
- Each subfolder (e.g., `train/160/`) contains images of resistors with that resistance value.  

#### **2. Data Loading with `tf.Data`**  
- Instead of loading all images at once, the class uses **dynamic batch loading**:  
  - Get a list of image file paths.  
  - Convert to TensorFlow `Dataset`.  
  - Shuffle, batch, and preprocess (resize, normalize) on the fly.  
- **Example code snippet**:  
  ```python
  train_list = glob.glob('data/train/*/*.png')  # Get file paths
  train_ds = tf.data.Dataset.list_files(train_list)  # Convert to TensorFlow Dataset
  train_ds = train_ds.shuffle(len(train_list)).batch(32).map(process_path)  # Shuffle, batch, preprocess
  ```  

#### **3. Classification Model**  
- **Goal**: Predict the resistor's class (e.g., 150Ω, 160Ω, etc.).  
- **Output Layer**: 14 nodes (one per class) with **softmax activation**.  
- **Loss Function**: Cross-entropy.  
- **Input**: 64x64 RGB images (3 channels).  

#### **4. Regression Model**  
- **Goal**: Directly predict the resistance value (e.g., 620.0 Ω).  
- **Output Layer**: 1 node with **linear activation** (no softmax).  
- **Loss Function**: Mean Squared Error (MSE).  
- **Evaluation Metric**: Mean Absolute Error (MAE).  

#### **5. Label Extraction**  
- **Classification**: Extract class ID from folder name (e.g., "160" → class ID 1).  
- **Regression**: Extract resistance value as a float (e.g., "160" → 160.0).  

---

### **Homework Assignment**  
**Task**: Train and evaluate **both models** (classification and regression) using the provided resistor dataset.  

#### **Requirements**:  
1. Use `data/train` for training and `data/valid` for validation.  
2. Submit a **Jupyter Notebook (`.ipynb`)** with:  
   - Code for both models.  
   - Training process and evaluation.  
3. **File Naming**: Include your student ID in the filename.  
4. **Deadline**: June 7 (Friday), 13:10.  

#### **Key Differences Between Models**:  
| Feature          | Classification Model      | Regression Model          |  
|------------------|---------------------------|---------------------------|  
| **Output Nodes** | 14 (softmax)              | 1 (linear)                |  
| **Loss Function**| Cross-entropy             | Mean Squared Error (MSE)  |  
| **Evaluation**   | Accuracy                  | Mean Absolute Error (MAE) |  
