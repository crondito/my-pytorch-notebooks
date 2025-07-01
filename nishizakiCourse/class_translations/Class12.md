### **Summary of Class 12: Fundamentals of Natural Language Processing (Morphological Analysis & Word Embeddings)**  

#### **Class Overview**  
This class introduces **core NLP techniques** for Japanese text processing:  
1. **Morphological Analysis**: Splitting sentences into meaningful units (morphemes).  
2. **Word Embeddings**: Representing words as dense vectors to capture semantic relationships.  

Key tools: **MeCab**, **Word2Vec (CBOW/Skip-gram)**, and neural networks for embedding learning.  

---

### **Key Concepts**  

#### **1. Morphological Analysis**  
- **Goal**: Break text into **morphemes** (smallest meaning-bearing units) with part-of-speech (POS) tags.  
  - Example:  
    ```  
    "私は山梨大学に行きました" →  
    私/代名詞 は/助詞 山梨/固有名詞 大学/名詞 に/助詞 行き/動詞 まし/助動詞 た/助動詞  
    ```  
- **Process**:  
  1. **Dictionary Lookup**: Match morphemes using a lexicon (e.g., MeCab’s IPADIC).  
  2. **Lattice Construction**: Generate possible morpheme paths (e.g., "明日" vs. "あす").  
  3. **Cost-Based Selection**: Use **Viterbi algorithm** to pick the lowest-cost path (combining *connection costs* and *emission costs*).  
- **Tools**:  
  - **MeCab**: Uses CRF for cost optimization.  
  - **Juman++**: Deep learning-based alternative.  

#### **2. Word Embeddings**  
- **Purpose**: Convert words to vectors preserving semantic relationships.  
- **Methods**:  
  - **Word2Vec**:  
    - **CBOW**: Predicts a word from its context.  
    - **Skip-gram**: Predicts context words from a target word.  
  - **Key Property**: Vector arithmetic (e.g., `King - Man + Woman ≈ Queen`).  
- **Implementation**:  
  ```python
  # Using Gensim for Word2Vec
  from gensim.models import Word2Vec
  model = Word2Vec(sentences, vector_size=100, window=5, min_count=1)
  ```  

---

### **Homework Assignment**  
**Task**: Generate word embeddings from Natsume Sōseki’s *"I Am a Cat"* (*Wagahai wa Neko de Aru*).  

#### **Steps**:  
1. **Preprocess Text**:  
   - Use **MeCab** to tokenize the novel into morphemes.  
2. **Train Word2Vec**:  
   - Use `gensim.Word2Vec` to create embeddings (e.g., 100-dimensional vectors).  
3. **Evaluate**:  
   - Check semantic similarity (e.g., `model.similarity("猫", "動物")`).  
4. **Submit**:  
   - Jupyter Notebook (`.ipynb`) with code and results.  
   - **Filename**: `[StudentID]_word_embeddings.ipynb`.  
   - **Deadline**: July 5 (Friday), 17:00.  

---

### **Additional Notes**  
- **Morphological Analysis**: Critical for Japanese NLP due to lack of spaces.  
- **Embeddings**: Enable advanced tasks like text classification, translation, and chatbots.  
- **Ethical Consideration**: Ensure text data usage complies with copyright laws.  

This class bridges **linguistics** (morpheme analysis) and **machine learning** (embeddings), providing foundational skills for NLP pipelines.
