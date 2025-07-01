### **Summary of Class 13: Language Models and RNN-based Text Generation**  

#### **Class Overview**  
This class explores **language models** and their application in **automatic text generation** using **Recurrent Neural Networks (RNNs/LSTMs)**. Key topics include:  
1. **Statistical vs. Neural Language Models**: N-gram models vs. RNN-based approaches.  
2. **Text Generation**: Using LSTMs to predict sequences of words.  
3. **Practical Implementation**: Training a model on *"I Am a Cat"* by Natsume Sōseki.  

---

### **Key Concepts**  

#### **1. Language Models**  
- **Purpose**: Predict the likelihood of a word sequence (i.e., how "natural" a sentence is).  
- **Types**:  
  - **N-gram Models**: Use previous *N-1* words to predict the next word (e.g., bigrams, trigrams).  
  - **Neural Models (RNN/LSTM)**: Capture long-term dependencies via hidden states.  

#### **2. N-gram Models**  
- **Example**:  
  - Bigram: `P("晴れ" | "天気は")` → Probability of "晴れ" following "天気は".  
- **Limitation**: Fails with long-range dependencies (e.g., "Kyoto" influencing a word 10 tokens later).  

#### **3. Neural Language Models (LSTMs)**  
- **Architecture**:  
  - **Embedding Layer**: Converts words to dense vectors.  
  - **LSTM Layer**: Processes sequences, maintaining context.  
  - **Dense Layer**: Predicts the next word (softmax over vocabulary).  
- **Training**:  
  - Input: `["<BOS>", "吾輩", "は"]` → Label: `["吾輩", "は", "猫"]`.  
  - Loss: Cross-entropy between predicted and actual next words.  

#### **4. Text Generation**  
- **Process**:  
  1. Feed a seed phrase (e.g., `"吾輩は"`).  
  2. Predict the next word, append it, and repeat.  
- **Example Output**:  
  ```  
  Seed: "吾輩は" → Generated: "猫である。名前はまだない。"  
  ```  

---

### **Homework Assignment**  
**Task**: Train an LSTM-based language model on *"I Am a Cat"* and generate text.  

#### **Steps**:  
1. **Preprocess Data**:  
   - Tokenize text using **MeCab**.  
   - Create word-ID mappings and padded sequences.  
2. **Build Model**:  
   ```python  
   model = tf.keras.Sequential([  
       tf.keras.layers.Embedding(vocab_size, 64),  
       tf.keras.layers.LSTM(128),  
       tf.keras.layers.Dense(vocab_size, activation='softmax')  
   ])  
   ```  
3. **Train & Generate**:  
   - Train on input-label pairs (e.g., `input="吾輩は"`, `label="猫"`).  
   - Generate text by iteratively predicting next words.  
4. **Submit**:  
   - Jupyter Notebook (`.ipynb`) with:  
     - Preprocessing code.  
     - Model training/generation.  
     - **Improvements**: Adjustments (e.g., hyperparameters, embeddings) and their impact.  
   - **Filename**: `[StudentID]_text_generation.ipynb`.  
   - **Deadline**: July 19 (Friday), 13:10.  

---

### **Additional Notes**  
- **Tools**: Use `TensorFlow/Keras` for LSTMs; `MeCab` for Japanese tokenization.  
- **Challenge**: Balancing creativity (diversity) vs. coherence in generated text.  
- **Applications**: Chatbots, auto-completion, poetry generation.  

This class bridges **traditional NLP (N-grams)** and **modern deep learning (LSTMs)**, emphasizing hands-on text generation.
