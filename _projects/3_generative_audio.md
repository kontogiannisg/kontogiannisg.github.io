---
layout: page
title: Generative Augmentation for Medical Audio
description: Deep generative models that synthesize clinically meaningful cough and lung sounds to address data scarcity.
# img: assets/img/projects/genaudio.jpg  # TODO: add a screenshot/figure
importance: 3
category: audio & respiratory ai
related_publications: true
---

Deep generative models for synthesizing clinically meaningful cough and lung sounds, used
as a principled data-augmentation strategy to improve classifier robustness under limited
and imbalanced clinical data. The approach uses multiple Variational Autoencoder variants
with a probabilistic cough-level fusion mechanism, operating across the time-frequency
domain while reconstructing acoustically verifiable samples in the time domain.

Related publication: {% cite kontogiannis2026cough %}.
