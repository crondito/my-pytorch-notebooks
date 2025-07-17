# Summary of Yang Tingcheng Master's Thesis

**Speech Scoring and Wrong Pronunciation Detection for Non-Native Japanese Learners Based on End-to-End Speech Recognition**

- Yang Tingcheng - Toyohashi University of Technology, 2023

## Main Goal

Develop an automated system to score pronunciation and detect specific mispronunciations in Japanese learners’ speech, especially for non-native beginners, using End-to-End (E2E) deep learning models—without needing manual phoneme/word alignment.

---

## Key Contributions

1.	Pronunciation Scoring:

    * A model predicts pronunciation quality scores based on acoustic features.
    * No ASR decoding or phoneme/word alignment is needed—making it simpler and lighter.
    * Uses different architectures: LSTM, BiLSTM, Transformer.

2.	Wrong Pronunciation Detection:

    * Focuses on specific error types (e.g., gemination, long vowels, voiced sounds).
    * Two E2E-based detection methods:
        * Method 1: Label incorrect pronunciations in training transcripts.
        * Method 2: Modify transcripts to reflect actual mispronunciations and detect via mismatch.

---

## Models and Architectures

* For Scoring:
    * Input: acoustic features (MFCC, FBANK, Spectrogram, PLP).
    * Models: 2-layer LSTM, BiLSTM, Transformer Encoder.
    * Loss: Mean Squared Error (MSE).

* For Pronunciation Detection:
    * ASR model: Hybrid CTC/Attention with 12 Conformer encoders and 6 Transformer decoders (built with ESPnet).
    * Evaluated using recall and precision.

---

## Datasets Used

1.	JRF: Japanese Speech Database Read by Foreign Students.
    * Speakers: 141 learners from 26 non-Japanese L1 backgrounds.
    * Issues: Speakers are relatively fluent → low variation, few mispronunciations.

2.	New Dataset:
    * Created by author using 26 Chinese students learning Japanese.
    * Contains 160 words & 28 sentences prone to mispronunciation.
    * Rated by 3 native Japanese teachers in 3 categories:
        * Mispronunciation
        * Smoothness & accent
        * Overall quality

---

## Results:

### Speech Scoring:

* Best model: Transformer Encoder with MFCC input.
* Performance: PCC (Pearson correlation) with teacher scores exceeded inter-teacher PCC → scoring model is on par with human raters.

### Mispronunciation Detection:

* Method 1 (label-based): Recall = 29.4%
* Method 2 (transcript-based): Recall = 64.7%, Precision = 78.6%
    * Performance still limited due to lack of data.

---

## Conclusions

* Transformer-based models effectively predict pronunciation scores, even matching human rater consistency.
* E2E ASR can detect specific mispronunciations with moderate success.
* More diverse and labeled data (especially mispronunciation examples) is crucial for better performance.

---

## Future Work

* Build a larger, well-annotated dataset of foreigner Japanese speech.
* Explore non-ASR acoustic-based methods for mispronunciation detection.
* Improve detection for rare pronunciation errors.
