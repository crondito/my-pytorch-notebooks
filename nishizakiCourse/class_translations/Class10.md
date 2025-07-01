### **Summary of Class 10: Fundamentals of Audio Signal Processing**  

#### **Class Overview**  
This class introduces the **basics of audio signal processing**, covering:  
1. **Sound physics** (waveforms, sampling, Fourier transforms).  
2. **Human voice production and perception**.  
3. **Digital audio formats** (WAV, MP3, PCM).  
4. **Feature extraction** (MFCCs, spectrograms) for speech recognition.  
5. **Practical analysis** using Python (FFT, spectrograms).  

Key tools: **Fast Fourier Transform (FFT)**, **Mel-Frequency Cepstral Coefficients (MFCCs)**, and audio libraries like `librosa`.  

---

### **Key Concepts**  

#### **1. Sound as a Wave**  
- **Sound**: Air pressure variations captured as **waveforms** (amplitude vs. time).  
- **Sampling**: Analog → digital conversion via:  
  - **Sampling rate** (e.g., 44.1 kHz for CD quality).  
  - **Bit depth** (e.g., 16-bit for CD audio).  
- **Nyquist Theorem**: Sampling rate must be ≥2× the highest frequency (e.g., 40 kHz to capture 20 kHz sounds).  

#### **2. Human Voice Production**  
- **Vocal Tract**: Airflow → vocal cord vibration → resonance in mouth/nose → sound.  
- **Pitch**: Measured in Hz (e.g., 100–150 Hz for male voices).  
- **Audible Range**: 20 Hz–20 kHz (narrows with age).  

#### **3. Digital Audio Formats**  
| **Format**  | **Type**       | **Example Use**          |  
|-------------|----------------|--------------------------|  
| WAV         | Uncompressed   | High-fidelity audio      |  
| MP3         | Compressed     | Music streaming          |  
| PCM         | Raw data       | Telephony (8 kHz, 8-bit) |  

#### **4. Feature Extraction**  
- **FFT**: Converts time-domain signals to frequency-domain **spectrograms**.  
- **MFCCs**: Compact representation of vocal tract shape (13–26 coefficients).  
  - Steps:  
    1. Apply **Hamming window** to audio clips (25 ms frames).  
    2. Compute **FFT** → **power spectrum**.  
    3. Apply **Mel filter banks** (mimics human hearing).  
    4. **Discrete Cosine Transform (DCT)** to get MFCCs.  

#### **5. Practical Analysis**  
- **Python Tools**:  
  ```python
  import librosa
  y, sr = librosa.load("audio.wav", sr=16000)  # Load audio (16 kHz)
  mfccs = librosa.feature.mfcc(y=y, sr=sr, n_mfcc=13)  # Extract MFCCs
  ```  
- **Spectrogram**: Visualizes frequency content over time.  

---

### **Homework Assignment**  
**Task**: Analyze a recorded vowel sound (`/a/, /i/, /u/, /e/, /o/`) and submit:  
1. A **Jupyter Notebook** with:  
   - Audio loading code.  
   - FFT/MFCC analysis.  
   - Spectrogram plots.  
2. **Recorded WAV file** (16 kHz, 16-bit, mono) of your voice saying vowels.  

#### **Requirements**:  
- **Filename**: `[StudentID]_audio_analysis.ipynb`.  
- **Deadline**: June 28 (Friday), 13:10.  

---

### **Additional Notes**  
- **Voice Evaluation Dataset**: Upcoming project to label speech samples for "impression" (e.g., clarity, confidence).  
- **Ethical Note**: Avoid loud volumes to prevent hearing damage.  

This class bridges **theory** (sound physics) and **practice** (feature extraction for AI speech systems), emphasizing hands-on analysis with Python.
