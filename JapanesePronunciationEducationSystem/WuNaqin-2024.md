# Summary of Wu Naqin's Master's Thesis

**Pronunciation Error Detection for Non-Native Japanese Speakers Using Attention Mechanisms**

- Wu Naqin - Toyohashi University of Technology, 2023

---

## Main Goal
To improve the detection of pronunciation errors in non-native Japanese speech by leveraging **attention-based End-to-End (E2E) models**—building directly on the work of Yang Tingcheng.

---

## Continuation of Previous Work
- Builds on **Yang Tingcheng's** 2023 work using hybrid CTC/Attention models.
- Focus is shifted to **enhancing detection accuracy** by analyzing **attention weights** during decoding.

---

## Key Contributions

### 1. Attention Weight Analysis
- Investigates attention weights from the **decoder-attention module** in E2E ASR models.
- Key idea: **Wrong pronunciations result in weaker or diffused attention** compared to correct ones.

### 2. Segment-Based Analysis
- Computes average attention scores over:
  - Each grapheme
  - Sliding time windows
- Enables **visualization and measurement** of attention strength per segment.

### 3. Error Judgment Metrics
- Proposes metrics based on:
  - Peak attention weight
  - Mean/max values in attention segment
- Determines thresholds to classify pronunciation as **correct** or **incorrect**.

---

## Experiments

### Dataset
- Same **Chinese learner speech corpus** as Yang Tingcheng.
- 160 words + 28 sentences with common mispronunciations.

### Results
- Attention-based scoring outperforms prior error detection methods.
- Method identifies mispronounced segments with **good precision**.

---

## Conclusions
- Attention weights in E2E ASR models carry **valuable error signals**.
- The method enables **unsupervised mispronunciation detection** without special labels.
- Visualization shows clear attention difference between correct and incorrect utterances.

---

## Future Work
- Extend to **sentence-level analysis**.
- Combine attention with **other speech features** (duration, pitch).
- Explore **self-attention (Transformer) weights** for deeper insight.
---

## Additional Notes from Wu Naqin

Wu Naqin provided further context regarding the research:

- The dataset consists of speech from 50 Japanese learners, covering 160 word segments and 28 sentence segments. However, audio quality is poor due to inconsistent recording conditions and background noise.
- Most research focused on **sentence-level utterances**. Manual annotations (delays, repetitions, pauses) were applied for rough error localization, though they lack precision and may not be directly useful for future work.
- The **scoring model** uses a Transformer encoder that outputs a regression score. While experimental results correlate with teacher scores (e.g., PCC), the limited dataset quality and scale present theoretical concerns.
- For **pronunciation error detection**, attention feature analysis was used instead of relying on ESPnet-based ASR methods.
- Wu acknowledges that the code is rudimentary, partially translated, and still needs debugging. He advises using it as a reference and rebuilding key parts based on one's understanding.
- The original baseline code is available on the lab NAS: `/Kitaoka_lab/home/you`. Wu’s code builds on it but includes modifications.

**Recommendation**: Understand the intent and methods before diving deep into the provided codebase. Wu is available for support if issues arise during implementation.
