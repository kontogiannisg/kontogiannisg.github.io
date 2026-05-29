---
layout: page
title: Metadata-Conditioned Audio Transformers
description: Adaptive respiratory sound classification robust to recording device, auscultation site, and patient characteristics.
# img: assets/img/projects/ast.jpg  # TODO: add a screenshot/figure
importance: 2
category: audio & respiratory ai
related_publications: true
---

A family of metadata-conditioning mechanisms for the Audio Spectrogram Transformer (AST),
progressing from gated residual fusion to Feature-wise Linear Modulation (FiLM) adapted to
the Transformer architecture, including two novel variants—Token-Aware FiLM (TAFiLM) and
Soft-Factorized FiLM (SoftFiLM). Conditioning on patient- and acquisition-level metadata
mitigates systematic variability unrelated to pathology and improves classification of
underrepresented patient subgroups on the ICBHI benchmark.

Related publication: {% cite kontogiannis2026eusipco %}.
