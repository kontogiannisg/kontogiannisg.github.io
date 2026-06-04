---
layout: page
permalink: /research-statement
title: research statement
description: Research vision, themes, and a forward agenda in trustworthy edge health AI.
nav: false
---

My research builds **machine-learning systems that turn everyday devices—smartphones and wearables—into reliable, clinical-grade diagnostic instruments.** It is organized around a single question: _what does it take for a model to stay accurate, calibrated, and trustworthy not on a curated benchmark, but under the messy, heterogeneous conditions of real clinical practice?_

Answering this requires progress on three coupled fronts—learning robust representations from scarce and noisy medical signals, generating data where little exists, and deploying models that behave predictably on-device and across patient populations. I pursue these questions primarily in **respiratory and acoustic health**, in close collaboration with clinicians and industry, and I validate them in **deployed systems** rather than in simulation alone. The sections below trace this arc from the core problem, through the methods I develop, to the clinical settings in which they are tested, and finally to the agenda I intend to pursue as a postdoctoral researcher.

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Acoustic Biomarkers for Respiratory Health</h3>
  <p>
    Auscultation remains subjective and clinic-bound, yet the underlying acoustic signals are rich in diagnostic information. My core line of work asks whether commodity microphones can capture clinically meaningful respiratory biomarkers. I design pipelines that detect and segment coughs from continuous audio and classify respiratory conditions—such as asthma versus COPD—directly from tracheal- and chest-wall–acquired lung sounds, with models lightweight enough to run on-device, in real time, without specialized hardware. This program spans a systematic framing of the field (<a href="/publications/#kapetanidis2024respiratory">Sensors, 2024</a>), a deployed on-device detection-and-classification system (<a href="/publications/#KONTOGIANNIS2026111784">Computers in Biology and Medicine, 2026</a>), and edge-AI screening for obstructive disease (<a href="/publications/#kontogiannis2026stethoscope">JBHI, under review</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Generative Modeling under Clinical Data Scarcity</h3>
  <p>
    Clinical audio datasets are small, imbalanced, expensive to label, and privacy-sensitive—conditions under which conventional augmentation falls short. I develop deep generative models (VAE and GAN families) that synthesize clinically meaningful cough and lung sounds and use them as a principled augmentation strategy to improve classifier robustness. A distinctive element of this work is <strong>cross-domain generation</strong>: optimizing latent representations in the time–frequency domain while reconstructing acoustically verifiable samples in the time domain, so that synthetic biomarkers remain clinically inspectable. I also study, more broadly, how synthetic data affects downstream recognition performance (<a href="/publications/#kontogiannis2024dcoss">DCOSS-IoT, 2024</a>; <a href="/publications/#KONTOGIANNIS2026111784">CBM, 2026</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Robustness, Domain Shift &amp; Trustworthy Deployment</h3>
  <p>
    Models that excel in the lab routinely fail in deployment: differences in recording devices, auscultation sites, and patient populations introduce systematic variability unrelated to the underlying pathology. I study how a <em>single</em> model can adapt to these conditions—through metadata-conditioning mechanisms that let a transformer adjust to recording context (<a href="/publications/#kontogiannis2026eusipco">EUSIPCO, 2026</a>), and through signal-level domain mitigation such as percussive-noise removal and frequency-spectrum correction across heterogeneous microphones and auscultation sites. Throughout, I treat calibration, explainability, and behavior on underrepresented patient subgroups as first-class objectives rather than afterthoughts, because these properties determine whether a model can be trusted at the point of care.
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Multimodal &amp; Clinical AI in Practice</h3>
  <p>
    Real diagnosis is multimodal, and my methods are tested in genuine clinical and consortium settings. With the University General Hospital of Patras, I build multimodal models that fuse paired lung-sound recordings, chest imaging, and inflammatory biomarkers—for example, to distinguish bacterial from viral pneumonia—and I develop the clinical data-acquisition tooling that makes such studies possible. Within the EU Horizon <a href="https://www.synairg.eu/" target="_blank" rel="noopener noreferrer">SynAir-G</a> project I study causal relationships between indoor environmental signals, wearable physiology, and health outcomes. Through the <a href="https://www.pfizer.com/" target="_blank" rel="noopener noreferrer">Pfizer CDI</a> EyeAI project I extend the same edge-deployment philosophy to computer vision, including sclera segmentation and non-invasive jaundice assessment from smartphone images (<a href="/publications/#kontogiannis2026jaundice">survey, under review</a>).
  </p>
</div>

<div class="card mt-3 p-3">
  <h3 class="card-title font-weight-medium">Future Directions</h3>
  <p>
    As a postdoctoral researcher I want to push edge-deployed medical AI from proof-of-concept toward dependable clinical tools, along four interconnected lines:
  </p>
  <ul>
    <li><strong>Generation that improves calibration, not just accuracy</strong>—integrating generative augmentation with uncertainty-aware and robust training, so synthetic data strengthens reliability rather than masking it.</li>
    <li><strong>Calibrated multimodal fusion under real-world shift</strong>—principled handling of missing or degraded modalities at the point of care, where not every signal is always available.</li>
    <li><strong>Causal and metadata-aware adaptation for fairness</strong>—models that remain equitable across devices, auscultation sites, and underrepresented patient subgroups.</li>
    <li><strong>Decisions that are explainable and auditable to clinicians</strong>—closing the loop between model outputs and clinical accountability.</li>
  </ul>
  <p>
    My longer-term goal is a general methodology for trustworthy edge health AI that transfers across acoustic, visual, and physiological signals. I am actively seeking postdoctoral positions and research collaborations where I can develop this agenda.
  </p>
</div>
