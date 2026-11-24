---
layout: page
title: Voice-Based Diagnostics (VBD)
description: On-device cough detection and asthma/COPD classification from smartphone-recorded cough and lung sounds (Pfizer CDI, VBD-1 and VBD-2).
# img: assets/img/projects/cough.jpg  # TODO: add a screenshot/demo GIF
importance: 1
category: audio & respiratory ai
related_publications: true
---

Two Pfizer Collaborative Development Initiative (CDI) research contracts with the
University of Patras (VBD-1, 2022–2023; VBD-2, 2023–2024) on respiratory screening from
audio recorded with a smartphone's built-in microphone. All models run on-device, in real
time, on commodity Android phones. I co-authored the VBD-2 proposal.

My work covered two lines:

- **Cough analysis.** Real-time cough event detection and segmentation from continuous
  audio; classification of detected coughs as asthma, COVID-19 or healthy with parallel
  SVMs and probabilistic cough-level fusion; and generative augmentation with five VAE
  variants that operate in the time-frequency domain and reconstruct in the time domain,
  so synthetic samples remain acoustically verifiable.
- **Smartphone auscultation.** 10-second tracheal and chest-wall recordings, with
  percussive noise removal and frequency-spectrum correction to reduce domain shift across
  auscultation sites and devices; normal/abnormal lung-sound classification and asthma vs.
  COPD identification with a ResNet-34 and probabilistic voting.

Publications from this work: {% cite kapetanidis2024respiratory %} (VBD-1);
{% cite KONTOGIANNIS2026111784 kontogiannis2026stethoscope %} (VBD-2).
