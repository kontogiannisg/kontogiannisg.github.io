---
published: false # hidden for now; revisit with the research statement
layout: page
title: EyeAI — Ocular Biomarker Analysis
description: On-device sclera segmentation from smartphone eye images, for non-invasive jaundice assessment (Pfizer CDI).
# img: assets/img/projects/eyeai.jpg  # TODO: add a screenshot/figure
importance: 1
category: computer vision
related_publications: true
---

Pfizer CDI research contract with the University of Patras (2024–2025) on ocular
biomarkers from smartphone-captured eye images. I was the primary author of the proposal.

- Dataset curation, annotation workflow and quality control for the ocular images.
- An attention-gated UNet++ for automatic sclera segmentation.
- Quantization and on-device deployment for real-time smartphone inference
  (TensorFlow Lite / ONNX).

The clinical work continues with the University General Hospital of Patras (Dept. of
Internal Medicine), under institutional ethics approval: statistical and causal modeling
of digital biomarkers and hematological indicators in patients with jaundice.

After the contract ended, the project led to a systematic review of AI-based jaundice
assessment from ocular images {% cite kontogiannis2026jaundice %}.
