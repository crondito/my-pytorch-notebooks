# Speech scoring and wrong pronunciation detection for non-native Japanese learners based on End-to-End speech recognition

<p align="right">
YANG TINGCHENG, 2023 <br>
MASTER OF ENGINEERING THESIS<br>
Department of Computer Science and Engineering<br>
TOYOHASHI UNIVERSITY OF TECHNOLOGY
</p>

## Introduction

### Background

- **Foreign Residents in Japan:**
    - 3,075,213 foreign residents at the end of 2022 → record high
    - First time exceeding 3 million

- **Japanese Language Education in Japan (as of Nov 2021)**
    - 2,541 education institutions
    - 39,241 Japanese language teachers
    - 123,408 learners

- **Japanese Language Education Overseas (2021 survey)**
    - 3.79M learners, 18,272 institutions, 74,592 teachers
    - Teacher-to-student ratio ≈ 1:50 → insufficient teaching resources
    - Self-study becomes essential

- **Problems with Current Learning Approach**
    - JLPT & J-Test don’t include oral tests → speaking often neglected
    - Learners struggle to judge pronunciation quality during self-study

- **Automated Pronunciation Scoring**
    - Can support learners where teachers are unavailable
    - TOEFL and other tests use Automatic Speech Recognition (<abbr title="Automatic Speech Recognition">ASR</abbr>) for scoring
    - <abbr title="Automatic Speech Recognition">ASR</abbr> also used for phoneme and word-level pronunciation evaluation

- **Wrong Pronunciation Detection**
    - “Goodness of Pronunciation” methods exist but may confuse learners if errors are not detected properly

### Purpose

>**Goal:** Use deep learning to help foreign Japanese learners, especially beginners, improve pronunciation.

#### Main Contributions:

- Develop a ***speech scoring model*** → automatically evaluates pronunciation quality.

    - Uses <abbr title="Measurable characteristics of a speech signal that represent how sounds are produced and perceived">acoustic features</abbr> to generate pronunciation scores.
    - Does not rely on <abbr title="Automatic Speech Recognition">ASR</abbr> or phoneme/word-level labels.
    - Based on <abbr title="A speech recognition system where the model directly converts raw audio input into text output in a single neural network, without using separate components for feature extraction, phoneme modeling, and decoding.">End-to-End ASR</abbr> architecture but adapted for scoring.
    - Tests different model structures to improve performance.

- Build a ***wrong pronunciation detection system*** → identifies specific pronunciation errors.

    - Designed for <abbr title="Learners read a predetermined script, allowing the system to compare spoken audio with the expected text and detect pronunciation errors precisely.">fixed-text</abbr> reading practice.
    - Two proposed methods:
        - Label-based ASR training → train an ASR model with specific wrong pronunciation labels to detect errors automatically.
        - Direct transcription approach → train ASR on data containing wrong pronunciations so the system recognizes mispronunciations explicitly.
    - A detector compares the expected text with the recognized text to identify pronunciation mistakes.

## Related work

- Automatic speech scoring and wrong pronunciation detection are key in pronunciation assessment
- Early assessments relied on manual raters → time-consuming and expensive
- With NLP, machine learning, and deep learning, automatic pronunciation assessment became possible.
