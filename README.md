# Audio-Visual Speech Enhancement System for Hearing Impaired and Deaf Users in Multi-Speaker Environments

> Isolating and enhancing a target speaker's voice in noisy multi-speaker environments using synchronized audio and visual information.

---

# Overview

The **Cocktail Party Problem** is one of the most challenging problems in speech processing. Humans can naturally focus on one person's speech in a noisy environment, while computers still struggle when multiple speakers talk simultaneously.

This project aims to build an **Audio-Visual Speech Enhancement and Speaker Separation System** that combines both **audio signals** and **visual speech cues (lip movements)** to isolate and enhance a selected speaker's voice.

Unlike traditional speech enhancement systems that rely only on audio, this system uses facial and lip movement information to improve robustness under noisy conditions.

The project is designed primarily for:

- Hearing-impaired users
- Deaf users (through transcription)
- Noisy meeting environments
- Online conferences
- Educational settings
- Research on multimodal speech processing

---

# Project Objectives

The system is designed to:

- Separate speech from **2–5 simultaneous speakers**
- Enhance the selected speaker's voice
- Suppress environmental noise
- Utilize lip movements to improve separation quality
- Handle situations where visual information is partially or completely unavailable
- Automatically fall back to audio-only processing when necessary
- Provide an intuitive interface for selecting the desired speaker
- Optionally generate live speech transcription

---

# Proposed Workflow

The system follows the complete pipeline below.

```
Input Video
        │
        ▼
Audio Extraction
        │
        ▼
Face Detection
        │
        ▼
Face Tracking
        │
        ▼
Lip Region Extraction
        │
        ▼
Audio Feature Extraction
        │
        ▼
Visual Feature Extraction
        │
        ▼
Audio-Visual Fusion
        │
        ▼
Speech Separation
        │
        ▼
Missing Visual Cue Detection
        │
 ┌──────┴─────────┐
 │                │
 ▼                ▼
AV Processing   Audio-only Processing
 │                │
 └──────┬─────────┘
        ▼
Separated Speaker Streams
        │
        ▼
Speaker Selection Interface
        │
        ▼
Enhanced Audio Output
        │
        ▼
(Optional)
Speech-to-Text
```

---

# System Workflow

The expected user workflow is:

1. User uploads a video containing multiple speakers.
2. The system extracts the audio stream.
3. Faces are detected in every frame.
4. Speakers are tracked across the video.
5. Lip regions are extracted.
6. Audio and visual features are synchronized.
7. A multimodal speech separation model isolates each speaker.
8. Bounding boxes are displayed around detected speakers.
9. The user selects the desired speaker.
10. Only the selected speaker's enhanced voice is played.
11. Optional real-time transcription is generated.

---

# Features

- Multi-speaker speech separation
- Audio-visual speech enhancement
- Lip-reading assisted enhancement
- Speaker selection interface
- Face detection and tracking
- Automatic missing visual cue handling
- Audio-only fallback
- Noise suppression
- Modular architecture
- Optional speech transcription

---

# Expected Inputs

- MP4 videos
- Webcam input (future)
- Multi-speaker recordings
- Real-world noisy environments

---

# Outputs

Primary Output

- Enhanced speech of the selected speaker

Secondary Outputs

- Speaker bounding boxes
- Speaker IDs
- Optional captions
- Clean separated audio streams

---

# Research Inspiration

The implementation is inspired by the following research works.

- Looking to Listen at the Cocktail Party
- MuSE (Multi-modal Target Speaker Extraction with Visual Cues)
- RAVSS
- Audio-Visual Speech Enhancement Using Multimodal Deep CNNs
- Lip Reading Driven Deep Learning for Speech Enhancement
- Real-Time Audio-Visual Speech Enhancement Using Pre-trained Visual Representations
- Deep Audio-Visual Speech Recognition
- Audio-Visual Speech Enhancement and Separation Survey

This project **does not reproduce any single paper**.

Instead, it combines ideas from multiple works into one practical end-to-end application.

---

# Implementation Philosophy

The implementation follows the methodology proposed in the project presentation and literature survey while integrating reliable open-source components.

Rather than reproducing research models from scratch, the project:

- uses pretrained visual feature extractors
- uses proven audio separation backbones
- develops the overall pipeline independently
- integrates all modules into one complete application

The engineering effort focuses on building a deployable system instead of replicating individual research architectures.

---

# Technology Stack

## Programming Language

- Python 3.11+

## Deep Learning

- PyTorch

## Computer Vision

- OpenCV
- MediaPipe

## Audio Processing

- Librosa
- FFmpeg
- SoundFile

## Machine Learning

- NumPy
- SciPy

## Speech Processing

- ConvTasNet-based separation backbone
- Pretrained visual encoder
- Audio-Visual Fusion

## Transcription (Optional)

- Whisper

## User Interface

- Streamlit (prototype)
- Future desktop/web interface

---

# Repository Structure

```
Cocktail-party/

│
├── app/
│   ├── ui/
│   ├── backend/
│   └── inference/
│
├── models/
│   ├── visual_encoder/
│   ├── separator/
│   └── checkpoints/
│
├── preprocessing/
│   ├── audio/
│   ├── video/
│   └── synchronization/
│
├── utils/
│
├── datasets/
│
├── outputs/
│
├── notebooks/
│
├── docs/
│
├── requirements.txt
│
└── README.md
```

---

# Current Development Status

Current Phase

- Literature Survey
- System Design
- Pipeline Planning

Upcoming

- Dataset preparation
- Face detection module
- Lip extraction module
- Audio preprocessing
- Speech separation integration
- Speaker selection interface
- Complete application deployment

---

# Future Enhancements

- Real-time webcam processing
- Mobile application
- Hearing aid integration
- Speaker diarization
- Emotion recognition
- Multi-language transcription
- Edge deployment
- GPU optimization

---

# Getting Started

Clone the repository.

```bash
git clone https://github.com/Akashj-aj/Cocktail-party.git
cd Cocktail-party
```

Install dependencies.

```bash
pip install -r requirements.txt
```

Run the application.

```bash
python app.py
```

*(Commands will be updated as development progresses.)*

---

# Motivation

The project explores how combining visual speech cues with audio processing can overcome limitations of traditional speech enhancement systems. By integrating multimodal deep learning techniques with practical engineering, the goal is to develop a robust system capable of functioning in realistic multi-speaker environments while improving accessibility for hearing-impaired users.

---

# License

To be decided.

---

# Acknowledgements

This project is inspired by recent advances in multimodal speech processing and audio-visual deep learning research. We acknowledge the contributions of the open-source community and the authors of the referenced research papers whose work serves as the foundation for this implementation.

---

*"Accessibility, robustness, and practical deployment are the guiding principles of this project."*
