# Glossary

### **Acoustic Features**
Characteristics of audio signals (like pitch, tone, or frequency patterns) used to analyze or model speech.

### **ASR (Automatic Speech Recognition)**
Technology that converts spoken language into written text, like when your phone transcribes your voice messages.

### **Attention Mechanism**
A technique in neural networks that allows the model to focus on relevant parts of the input sequence when making predictions, especially important in sequence-to-sequence tasks like ASR.

### **Attention Weights**
Numerical values that represent how much focus the model gives to different parts of the input at each output step. High weights indicate important segments.

### **BiLSTM (Bidirectional Long Short-Term Memory)**
A type of neural network that processes information both forward and backward through a sequence — helpful for understanding context in speech.

### **CTC (Connectionist Temporal Classification)**
A training method for speech models that helps them learn sequences without needing exact timing alignment between audio and text.

### **Conformer**
A hybrid neural network architecture combining convolutional and transformer layers, designed specifically for speech recognition tasks.

### **Decoder Attention**
A component in sequence-to-sequence models that computes attention weights during the decoding process to help determine relevant input features for each output step.

### **End-to-End (E2E) Model**
A model that learns the entire task from input to output directly, without needing intermediate steps like manual labeling or alignment.

### **ESPnet**
An open-source toolkit for building speech processing systems, like speech recognition or synthesis, using deep learning.

### **FBANK (Filter Bank features)**
A type of acoustic feature that represents how energy is distributed across different frequency bands in speech.

### **Gemination**
A pronunciation feature where a consonant is lengthened or "doubled" in sound. Common in Japanese (e.g., the double "k" in "gakkō").

### **Long Vowels**
Vowels that are held longer than normal. In Japanese, vowel length can change meaning (e.g., *obasan* vs *obaasan*).

### **LSTM (Long Short-Term Memory)**
A type of neural network especially good at processing sequences, such as audio or text over time.

### **Mean Squared Error (MSE)**
A common way to measure the accuracy of a model's predictions, based on the average squared difference between predicted and actual values.

### **MFCC (Mel-Frequency Cepstral Coefficients)**
A popular acoustic feature that represents how humans perceive speech sounds, used in many speech recognition systems.

### **Mispronunciation**
An incorrect or non-native way of saying a word or sound.

### **Peak Attention**
The maximum value within an attention segment, indicating the most focused point of attention during prediction.

### **Phoneme**
The smallest unit of sound in a language that can change meaning (e.g., /r/ vs /l/ in English).

### **Precision**
A metric that tells you how many of the things your system detected were actually correct.

### **Recall**
A metric that tells you how many of the real problems your system managed to detect.

### **Segment-Level Analysis**
A method of analyzing parts of speech audio in smaller time units or corresponding to individual graphemes or phonemes.

### **Spectrogram**
A visual representation of the frequencies in sound over time—used to analyze speech patterns.

### **Thresholding**
Setting a cutoff value to determine whether a metric (like attention score) is high or low enough to indicate correctness or error.

### **Transformer**
A type of deep learning model that’s powerful for processing sequences, especially used in language and speech tasks.

### **Voiced Sounds**
Sounds made while the vocal cords vibrate (e.g., "z", "b", "d"). Mispronunciation can happen when these are mistaken for voiceless sounds like "s", "p", or "t").
