### **Summary of Class 14: Encoder-Decoder Models for Machine Translation**  

#### **Class Overview**  
This class focuses on **encoder-decoder models** (Sequence-to-Sequence models) for **machine translation**, covering:  
1. **Encoder-Decoder Architecture**: How it processes input sequences (e.g., Japanese) into output sequences (e.g., English).  
2. **Attention Mechanisms**: Enhancing translation by focusing on relevant parts of the input.  
3. **Practical Implementation**: Building a Japanese-to-English translation model using LSTMs.  

Key tools: **LSTMs**, **Attention**, and **Transformer models**.  

---

### **Key Concepts**  

#### **1. Encoder-Decoder Model**  
- **Purpose**: Map input sequences (e.g., Japanese sentences) to output sequences (e.g., English translations).  
- **Components**:  
  - **Encoder**: Converts input into a context vector (e.g., LSTM processes Japanese words).  
  - **Decoder**: Generates output from the context vector (e.g., LSTM produces English words).  
- **Example**:  
  ```  
  Input (JP): "私は学校へ行く" → Encoder → Context Vector → Decoder → Output (EN): "I go to school"  
  ```  

#### **2. Attention Mechanism**  
- **Why Attention?**: Traditional encoder-decoder models lose input details in long sequences. Attention **weights** important words dynamically.  
- **Types**:  
  - **Source-Target Attention**: Links encoder outputs to decoder steps (e.g., "school" → "学校").  
  - **Self-Attention**: Captures relationships within a single sequence (used in **Transformers**).  

#### **3. Transformer Models**  
- **Advantage Over LSTMs**: Parallel processing, no sequential dependency.  
- **Key Features**:  
  - **Multi-Head Attention**: Multiple attention layers for diverse focus points.  
  - **Positional Encoding**: Adds timing info since Transformers lack inherent sequence awareness.  

---

### **Homework Assignments**  

#### **1. Machine Translation Task**  
- **Task**: Train a Japanese-to-English translation model using the provided dataset (5,000 sentences).  
- **Steps**:  
  1. **Preprocess Data**: Tokenize Japanese/English texts, pad sequences.  
  2. **Build Model**:  
     ```python  
     # Encoder  
     encoder_inputs = Input(shape=(None,))  
     encoder_embed = Embedding(vocab_size, 256)(encoder_inputs)  
     encoder_lstm = LSTM(256, return_state=True)  
     encoder_outputs, state_h, state_c = encoder_lstm(encoder_embed)  
     # Decoder  
     decoder_inputs = Input(shape=(None,))  
     decoder_embed = Embedding(vocab_size, 256)(decoder_inputs)  
     decoder_lstm = LSTM(256, return_sequences=True)  
     decoder_outputs = decoder_lstm(decoder_embed, initial_state=[state_h, state_c])  
     outputs = Dense(vocab_size, activation='softmax')(decoder_outputs)  
     ```  
  3. **Train & Evaluate**: Use teacher forcing during training.  
  4. **Submit**: Jupyter Notebook (`.ipynb`) with code and translation examples.  
  - **Deadline**: July 26 (Friday), 13:10.  

#### **2. Final Project (Speech Classification)**  
- **Task**: Improve accuracy (≥50%) on the *Google Speech Commands Dataset* (35 classes).  
- **Tips**:  
  - Combine **CNNs** (for audio features) and **LSTMs** (for temporal patterns).  
  - Experiment with **MFCCs**, **Mel spectrograms**, or data augmentation.  
  - Use **attention** or hyperparameter tuning.  
- **Deadline**: August 10 (Thursday), 23:59.  

---

### **Additional Notes**  
- **Tools**:  
  - **Libraries**: TensorFlow/Keras for LSTMs; Hugging Face for Transformers.  
  - **Data**: Kyoto University’s Japanese-English parallel corpus.  
- **Challenge**: Handling **long sentences** (attention mitigates this).  
- **Ethical Note**: Ensure translations respect cultural nuances.  

This class bridges **traditional seq2seq models** and **modern Transformers**, emphasizing hands-on NLP applications.
