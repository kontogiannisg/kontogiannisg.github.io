---
layout: page
permalink: /research-statement
title: research statement
description: What I work on and what I want to do next in machine learning for respiratory health on phones and wearables.
nav: false
published: false # hidden until finalized
---

I work on machine learning for health monitoring with phones and wearables, mostly from sound: coughs, breathing, and lung sounds. The question I keep coming back to is why models that do well on a benchmark get worse on real recordings, where the microphones differ, the rooms are noisy, and the patients don't look like the training set, and what can be done about it.

In practice this splits into three problems: learning from small, noisy medical datasets, generating extra data when there isn't enough, and getting models to behave predictably when they run on a phone and see new patients. Most of the work is in respiratory and acoustic health. I do it together with clinicians and industry partners, and I test it in systems that run on real devices, not only in offline experiments.

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Respiratory sounds</h3>
  <p>
    Listening to the lungs with a stethoscope is subjective and needs a clinician in the room. I want to find out how much of that information an ordinary phone microphone can pick up. I build pipelines that find and segment coughs in continuous audio, and models that classify respiratory conditions (for example asthma vs. COPD) from lung sounds recorded at the trachea and the chest wall. The models are small enough to run on the phone in real time, with no extra hardware. So far this has produced a review of the field (<a href="/publications/#respiratory%20diseases%20diagnosis">Sensors, 2024</a>), an on-device cough detection and classification system (<a href="/publications/#on-device%20cough%20detection">Computers in Biology and Medicine, 2026</a>), and smartphone-based screening for obstructive disease (<a href="/publications/#transforming%20smartphones%20into%20stethoscopes">JBHI, under review</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Domain shift</h3>
  <p>
    A model trained on one dataset often does poorly on another, because the recording device, the spot on the chest, and the patient population all change the signal in ways that have nothing to do with the disease. Most of my methods work is about this. One part is a <strong>domain-adaptation framework</strong>, so that a model trained on one cohort, site, or device still works on others without collecting and labeling new data. The other is <strong>denoising and signal restoration</strong> for recordings with very low signal-to-noise ratio. This follows earlier work on conditioning a transformer on recording metadata (<a href="/publications/#metadata-conditioned%20audio%20transformers">EUSIPCO, 2026</a>) and on signal-level fixes such as removing percussive noise and correcting frequency differences between microphones and recording sites. Besides accuracy, I check calibration, explainability, and performance on underrepresented patient groups, since a clinician would need to know those before relying on a model.
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Generating data when there isn't enough</h3>
  <p>
    Clinical audio datasets are small, imbalanced, expensive to label, and hard to share because of privacy. Standard augmentation only helps so much here. I train generative models (VAEs and GANs) to synthesize cough and lung sounds and use them as extra training data for classifiers. The models learn in the time-frequency domain but produce time-domain audio, so a synthetic sample can be listened to and checked by a person. I've also looked more generally at how synthetic data affects downstream recognition (<a href="/publications/#synthetic%20data%20on%20human%20gesture">DCOSS-IoT, 2024</a>; <a href="/publications/#on-device%20cough%20detection">CBM, 2026</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Clinical projects</h3>
  <p>
    Most of this work happens inside clinical and funded projects. With the University General Hospital of Patras, I build models that combine lung-sound recordings, chest imaging, and inflammatory markers from the same patients, for example to tell bacterial from viral pneumonia, and I built the data-collection tools the study uses. In the EU Horizon <a href="https://www.synairg.eu/" target="_blank" rel="noopener noreferrer">SynAir-G</a> project I look at causal links between indoor environment measurements, wearable physiology, and health outcomes. In the <a href="https://www.pfizer.com/" target="_blank" rel="noopener noreferrer">Pfizer CDI</a> EyeAI project I apply the same on-device approach to images: segmenting the sclera and estimating jaundice from smartphone photos (<a href="/publications/#jaundice%20assessment%20from%20ocular">IEEE Access, 2026</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">What's next</h3>
  <p>
    As a postdoc, I want to keep moving this work from prototypes toward tools that hold up in practice. The first two items are already in progress:
  </p>
  <ul>
    <li>A domain-adaptation framework that lets one model work across cohorts, recording sites, and devices without new data collection or retraining, with robustness to distribution shift measured directly instead of assumed.</li>
    <li>Denoising and restoration models for low-SNR medical audio recorded on consumer hardware outside the clinic.</li>
    <li>Using generated data to improve calibration as well as accuracy, by combining generative augmentation with uncertainty-aware training, and making sure synthetic data doesn't hide reliability problems.</li>
    <li>Multimodal models that cope when one input is missing or poor quality, and that perform comparably across patient subgroups.</li>
    <li>Model outputs that clinicians can understand and audit.</li>
  </ul>
  <p>
    I'm looking for postdoctoral positions and research collaborations in this area.
  </p>
</div>
