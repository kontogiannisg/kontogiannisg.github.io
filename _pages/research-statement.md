---
layout: page
permalink: /research-statement
title: research statement
description: Learning from scarce, noisy, and heterogeneous data for respiratory health monitoring on consumer devices.
nav: false
published: false # full statement kept for later; not for publication yet
---

Respiratory disease is assessed largely in clinic visits: auscultation needs a stethoscope and a trained listener, and imaging and blood tests need a hospital. Phones and wearables are with the patient between visits, and their microphones, cameras, and motion sensors can record some of the same signals. My research is on the machine learning needed to make those recordings clinically usable, mostly from audio (cough and lung sounds), with images, physiological time series, and clinical data alongside.

The main obstacle is the data. Clinical datasets in this area are small and imbalanced, recordings are noisy, and the variation introduced by how a signal is acquired (microphone, auscultation site, environment, population) can be as large as the variation due to disease. On a consumer device it also changes with the phone model, the lighting, and how the user holds the device. With few patients per acquisition condition, a model can fit the acquisition instead of the pathology, and benchmark performance says little about behavior on a new device or at a new site. My thesis, _Multimodal Respiratory Health Monitoring on Consumer Devices: Learning from Scarce, Noisy, and Heterogeneous Data_, is organized around this problem.

### Separating acquisition from pathology

In the [Voice-Based Diagnostics](/projects/1_cough_detection/) project, I designed an on-device pipeline for asthma and COPD screening from tracheal and chest-wall recordings made with a phone's built-in microphone placed on the body. The classifier, a ResNet-34 with probabilistic voting, was trained on stethoscope recordings. With percussive-noise removal and frequency-spectrum correction that bring the phone recordings closer to the stethoscope domain, it detected abnormal lung sounds and identified the disease from phone recordings ([JBHI, under review](/publications/#transforming%20smartphones%20into%20stethoscopes)). The limitation is that the correction is designed for a known pair of conditions, and each new device or recording site means designing it again.

A more general approach is to give the model the acquisition factors as input. I conditioned an Audio Spectrogram Transformer on recording metadata, from gated residual fusion to FiLM-style feature modulation adapted to the transformer. On ICBHI, every conditioning variant improved over the unconditioned baseline ([EUSIPCO 2026](/publications/#metadata-conditioned%20audio%20transformers)), which indicates that recording conditions account for error the audio alone does not resolve. Both approaches assume the nuisance factors are known and recorded, which is rarely the case outside a curated benchmark. My current work is on domain adaptation across devices and recording sites, approached as calibration of the spectrum learned from data rather than designed by hand, and on restoration of low-SNR recordings made outside the clinic.

### Learning from small, imbalanced datasets

Respiratory audio datasets are small, imbalanced across conditions, and hard to share. For cough-based classification of asthma, COVID-19, and healthy subjects, I used five VAE variants to generate training data for the minority classes, which reduced the effect of class imbalance on disease classification ([Computers in Biology and Medicine, 2026](/publications/#on-device%20cough%20detection)). The models learn in the time-frequency domain but reconstruct in the time domain, so a synthetic sample is audio that a person can listen to and reject, not only a spectrogram judged by a downstream metric. The full system (cough detection and segmentation in continuous audio, SVM classification with probabilistic fusion across the coughs in a recording) runs in real time on Android phones. I studied the same question for wearable IMU data, testing whether GAN-generated allergic-rhinitis gestures can supplement or replace real data for training a recognizer ([DCOSS-IoT 2024](/publications/#synthetic%20data%20on%20human%20gesture)). Generative augmentation addresses imbalance but not acquisition shift: a generative model trained on one device's recordings reproduces that device's characteristics.

### Multimodal data

Some clinical questions are ambiguous from a single modality. Distinguishing bacterial from viral pneumonia is one: lung sounds, chest X-rays, and inflammatory biomarkers each carry part of the answer. At the University General Hospital of Patras, I am collecting a paired dataset of all three from the same patients, using mobile and web acquisition tools I built for use in the hospital.

In imaging, the same acquisition problem appears with cameras and lighting. In the [EyeAI](/projects/4_eyeai/) project, I developed an attention-gated UNet++ for sclera segmentation from smartphone eye images and quantized it for on-device inference; bilirubin estimation from the segmented sclera runs off-device. With clinicians at the hospital, where the eye images were collected, I also carried out statistical and causal modeling of the image-derived biomarkers against hematological indicators in jaundice patients. A systematic review of AI-based jaundice assessment from ocular images ([IEEE Access, 2026](/publications/#jaundice%20assessment%20from%20ocular)) found the field's main gap to be generalization: most studies were small, single-center, and at high risk of bias, and only one tested its model on an external dataset. In the EU Horizon [SynAir-G](/projects/5_synairg/) project, I work with a third kind of data, modeling temporal and causal relations between indoor air quality and physiological signals from wearables.

### Funding, collaboration, and supervision

This work has been carried out with clinical and industry partners. It was funded through three Pfizer CDI research contracts with the University of Patras (two phases of Voice-Based Diagnostics, and EyeAI) and the EU Horizon SynAir-G project. I co-wrote the proposal for the second Voice-Based Diagnostics phase and was the primary author of the EyeAI proposal. I have co-supervised five student theses, setting the research question and methodology and guiding the experiments, with the students carrying out the implementation. Four are on this theme: supervised domain adaptation for pathological respiratory sounds, respiratory cycle detection and segmentation in lung sounds, blood biomarker quantification from eye images under varying acquisition conditions, and causal modeling of IoT health data.

### Research plan

Over the next three to five years, I want to work on two problems that follow from the above:

- **Learned acquisition calibration.** Replace hand-designed spectrum correction with calibration learned from data, and train representations that are invariant to device, recording site, and population. Test that invariance directly, on held-out devices and sites, rather than infer it from in-distribution accuracy.
- **Multimodal models under missing or degraded inputs.** In practice a patient may have a lung-sound recording but no X-ray, or a recording too noisy to use. The paired pneumonia dataset is a direct testbed for models that use whichever modalities are available and degrade predictably when one is missing.

Both need clinical partners and data from real deployments, and I intend to pursue fellowship funding such as Horizon Europe MSCA Postdoctoral Fellowships alongside project funding.

Across these projects the question is the same: what a model learns from small clinical datasets recorded under conditions that differ from those it will be used in, and how to make it learn the pathology rather than the recording setup. I am looking for postdoctoral positions and research collaborations on this question.
