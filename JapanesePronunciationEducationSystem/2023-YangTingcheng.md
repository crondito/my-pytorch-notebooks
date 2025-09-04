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

- Main Contributions:
    - Develop a speech scoring model → automatically evaluates pronunciation quality.
    - Build a wrong pronunciation detection system → identifies specific pronunciation errors.

- Speech Scoring Model:
    - Uses <abbr title="Measurable characteristics of a speech signal that represent how sounds are produced and perceived">acoustic features</abbr> to generate pronunciation scores.
    - Does not rely on <abbr title="Automatic Speech Recognition">ASR</abbr> or phoneme/word-level labels.
    - Based on <abbr title="A speech recognition model that directly maps audio to text using a single integrated neural network.">End-to-End ASR</abbr> architecture but adapted for scoring.
    - Tests different model structures to improve performance.

