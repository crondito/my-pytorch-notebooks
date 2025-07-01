### **Summary of Class 9: Neural Networks for Time-Series Data**  

#### **Class Overview**  
This class introduces **Recurrent Neural Networks (RNNs)** and their variants (**LSTM**, **GRU**) for processing **time-series data** (e.g., sensor readings, speech, text). Key topics include:  
1. **RNN fundamentals** and limitations.  
2. **LSTM/GRU architectures** for long-term dependency modeling.  
3. **Practical applications**: Tennis swing classification, machine translation, and sequence prediction.  
4. **Preprocessing time-series data** (padding, masking, normalization).  

---

### **Key Concepts**  

#### **1. Recurrent Neural Networks (RNNs)**  
- **Purpose**: Process sequential data by maintaining a hidden state that captures temporal dependencies.  
- **Limitation**: Struggles with **long-term dependencies** (e.g., predicting "French" in "I grew up in France...").  
- **Structure**:  
  ```python
  model = tf.keras.Sequential([
      tf.keras.layers.SimpleRNN(64, return_sequences=True),
      tf.keras.layers.Dense(10)  # Example for classification
  ])
  ```  

#### **2. Long Short-Term Memory (LSTM)**  
- **Solves**: RNN’s vanishing gradient problem via **gates** (input, forget, output).  
- **Key Components**:  
  - **Forget Gate**: Decides what to discard from the cell state.  
  - **Input Gate**: Updates the cell state with new information.  
  - **Output Gate**: Controls the hidden state output.  
- **Implementation**:  
  ```python
  model.add(tf.keras.layers.LSTM(128, return_sequences=False))  # Last output only
  ```  

#### **3. Bidirectional LSTMs**  
- **Idea**: Processes sequences **forward and backward** to capture richer context.  
- **Use Case**: Speech recognition, sentiment analysis.  
  ```python
  model.add(tf.keras.layers.Bidirectional(tf.keras.layers.LSTM(64)))
  ```  

#### **4. Encoder-Decoder Models (Seq2Seq)**  
- **Application**: Machine translation, text summarization.  
- **Workflow**:  
  1. **Encoder** (LSTM) compresses input into a context vector.  
  2. **Decoder** (LSTM) generates output sequence from the vector.  

#### **5. Time-Series Data Preprocessing**  
- **Padding**: Uniform sequence length per batch (e.g., for sensor data).  
  ```python
  padded_data = tf.keras.preprocessing.sequence.pad_sequences(data, padding='post')
  ```  
- **Masking**: Ignores padded zeros during training.  
  ```python
  model.add(tf.keras.layers.Masking(mask_value=0.0, input_shape=(None, 3)))
  ```  
- **Normalization**: Scales data to mean=0, std=1.  

---

### **Practical Example: Tennis Swing Classification**  
- **Task**: Classify 10 players’ tennis swings using 3-axis accelerometer data.  
- **Model Architecture**:  
  ```python
  model = tf.keras.Sequential([
      tf.keras.layers.Masking(mask_value=0.0, input_shape=(None, 3)),
      tf.keras.layers.LSTM(64),
      tf.keras.layers.Dense(10, activation='softmax')  # 10 players
  ])
  model.compile(optimizer='adam', loss='sparse_categorical_crossentropy')
  ```  
- **Key Points**:  
  - Input: Variable-length sequences (padded to max length).  
  - Output: Player ID (0–9).  

---

### **Homework Assignment**  
**Task**: Implement the **tennis swing classifier** (target accuracy ≥90%).  

#### **Requirements**:  
1. Use provided sensor data (3-axis accelerometer sequences).  
2. Preprocess data:  
   - Pad sequences to uniform length.  
   - Normalize (mean=0, std=1).  
3. Train an LSTM model and evaluate accuracy.  
4. Submit a Jupyter Notebook (`.ipynb`) with:  
   - Preprocessing code.  
   - Model training/evaluation.  
   - **Filename**: `[StudentID]_tennis_swing.ipynb`.  
5. **Deadline**: June 14 (Friday), 23:59.  

---

### **Additional Notes**  
- **RNNs** are ideal for **ordered data** (time, text).  
- **LSTMs/GRUs** mitigate RNN limitations but are computationally heavier.  
- **Masking** ensures padded values don’t affect training.  

This class bridges theory (RNN variants) and practice (real-world time-series tasks), emphasizing **data preprocessing** and **model design** for sequential data.
