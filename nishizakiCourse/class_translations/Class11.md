### **Summary of Class 11: Speech Signal Classification (Speaker Recognition & Word Classification)**  

#### **Class Overview**  
This class focuses on **applying deep learning to speech signals** for two key tasks:  
1. **Speaker Recognition**: Identifying individuals based on voice.  
2. **Word Classification**: Distinguishing spoken words (e.g., digits "one" to "nine").  

Key techniques: **MFCC feature extraction**, **LSTM networks**, and **sequence processing** with TensorFlow.  

---

### **Key Concepts**  

#### **1. Speaker Recognition Model**  
- **Input**: MFCCs (Mel-Frequency Cepstral Coefficients) extracted from audio clips.  
  - **MFCC Steps**:  
    1. Apply **Hamming window** (32 ms frames, 10 ms stride).  
    2. Compute **FFT** → **Mel filter banks** → **DCT** to get 13–26 coefficients.  
- **Model Architecture**:  
  ```python
  model = tf.keras.Sequential([
      tf.keras.layers.Masking(mask_value=0.0, input_shape=(None, 13)),  # MFCC input
      tf.keras.layers.LSTM(64, return_sequences=False),  # Processes entire sequence
      tf.keras.layers.Dense(num_speakers, activation='softmax')  # Classify speaker
  ])
  ```  
- **Data Handling**:  
  - Pad variable-length sequences to uniform length with `tf.keras.preprocessing.sequence.pad_sequences`.  

#### **2. Word Classification Task**  
- **Dataset**: Google’s *Speech Commands Dataset* (digits "one" to "nine").  
- **Model**: Similar to speaker recognition (LSTM + Dense layers).  
- **Challenge**: Classify words **independent of speaker identity**.  

#### **3. MFCCs for Speech Tasks**  
- **Why MFCCs?**  
  - Capture vocal tract shape (invariant to pitch/speaker).  
  - Compact representation (13–26 coefficients vs. raw spectrograms).  
- **Human Perception**: Mel scale approximates how humans hear frequency differences.  

---

### **Homework Assignment**  
**Task**: Implement a **word classifier** for spoken digits ("one" to "nine").  

#### **Requirements**:  
1. Use the provided *Speech Commands Dataset* (`train/` and `test/` folders).  
2. Preprocess audio:  
   - Extract **MFCCs** (librosa or custom code).  
   - Pad sequences for batch processing.  
3. Train an **LSTM model** (architecture similar to speaker recognition).  
4. Submit a Jupyter Notebook (`.ipynb`) with:  
   - Data loading/preprocessing code.  
   - Model training/evaluation.  
   - **Filename**: `[StudentID]_word_classification.ipynb`.  
5. **Deadline**: July 5 (Friday), 13:10.  

---

### **Additional Notes**  
- **Speaker vs. Word Recognition**:  
  - Speaker ID relies on **vocal tract characteristics** (MFCCs).  
  - Word ID focuses on **phoneme patterns** (same MFCCs but different labels).  
- **Tools**:  
  - `librosa` for MFCC extraction.  
  - TensorFlow’s `pad_sequences` for variable-length audio.  

This class bridges **signal processing** (MFCCs) and **deep learning** (LSTMs), emphasizing practical implementation for speech-based AI tasks.
