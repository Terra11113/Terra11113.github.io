---
title: "Automatic Alignment of Freeform USTP Systems"
excerpt: "Image-quality-driven closed-loop alignment using Zemax modeling, structured image acquisition, MTF/distortion evaluation, and C++ optimization."
collection: portfolio
period: "Nov 2024 - Present"
timeline_date: "Nov 2024"
order: 3
thumbnail: "/images/research_ustp.png"
---

<style>
.project-album{display:flex;gap:1rem;overflow-x:auto;padding:0.25rem 0 1rem;margin-top:0.75rem;scroll-snap-type:x proximity}.project-album__item{flex:0 0 320px;scroll-snap-align:start}.project-album__item img{display:block;width:320px;height:210px;object-fit:contain;background:#fff;border:1px solid #ddd}.project-album__item figcaption{font-size:0.85em;color:#666;margin-top:0.35rem;text-align:center}
</style>

## Project Overview

This master's research project focuses on automatic alignment and image-quality optimization for freeform ultra-short-throw projection (USTP) systems. The key challenge is that six-degree-of-freedom pose errors of the freeform mirror jointly degrade geometric distortion and modulation transfer function (MTF), making manual alignment slow, operator-dependent, and difficult to reproduce.

**Role:** Master's research project  
**Period:** 2024.11 - Present  
**Keywords:** freeform optics, USTP, Zemax, Halcon, OpenCV, C++, MTF, geometric distortion, 6-DOF pose perturbation, closed-loop optimization

## Technical Focus

- Built a Zemax non-sequential optical model matched to the physical prototype.
- Simulated full-parameter 6-DOF perturbations of the freeform mirror to study pose-to-image-quality response laws.
- Designed a structured-target image acquisition and analysis workflow for geometric distortion and MTF-related evaluation.
- Implemented a C++ multi-objective adaptive weighting optimizer with stage-wise metric scheduling.
- Integrated optical simulation, industrial-camera acquisition, a 6-DOF precision platform, image-quality evaluation, optimization software, and motion execution.

## My Role

I participated in the complete system workflow from optical modeling to experimental validation. My work connected Zemax simulation, camera-based image acquisition, Halcon/OpenCV metric extraction, C++ optimization, and closed-loop motion control.

## Outcome

In 10 repeated experiments, the final mean MTF exceeded 70%, and each alignment run took about 10 minutes. This project trained me to connect optical modeling, image-quality feedback, optimization algorithms, and experimental system validation.

[Research Highlight](/files/ResearchHighlight_USTPAlignment_DuoXu.pdf)

## Album

<div class="project-album">
  <figure class="project-album__item"><img src="/images/project_ustp_platform.png" alt="USTP experimental platform"><figcaption>Experimental platform and structured target image.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_ustp_optical.png" alt="USTP optical layout"><figcaption>Optical layout of the freeform USTP system.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_ustp_statistics.png" alt="Alignment statistics"><figcaption>Robustness and statistical evaluation across repeated trials.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_ustp_comparison.png" alt="Local image-quality comparison"><figcaption>Local image-quality comparison after automatic alignment.</figcaption></figure>
</div>
