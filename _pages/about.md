---
permalink: /
title: "Home"
author_profile: true
---

Hi, I am **Duo Xu**. I build measurement-guided methods for physical systems, spanning **automatic optical alignment**, **machine vision**, and emerging work in **real-robot manipulation**.

Research Snapshot
======

<figure>
  <img src="/images/graphical-abstract/ustp-graphical-abstract-png-demo-v2.png" alt="Graphical overview of the USTP automatic alignment system" style="width: 100%; max-width: 100%; border: 1px solid #d8e2f1; border-radius: 6px;">
  <figcaption>Graphical overview of my current work on image-quality-driven automatic alignment for freeform ultra-short-throw projection systems.</figcaption>
</figure>

Current Focus
======

**Automatic Alignment of Freeform Ultra-short-throw Projection Systems**

My current work studies how optical pose errors affect captured image quality, and how image feedback can guide automatic alignment. The system connects optical simulation, camera acquisition, image-quality evaluation, C++ optimization, and motion execution.

_Project image placeholder: a 2x2 evidence matrix or a system/result comparison figure will be added here._

Key elements:

- **Optical modeling:** Zemax non-sequential modeling and 6-DOF perturbation analysis.
- **Image feedback:** structured-target acquisition with distortion and MTF-related metric extraction.
- **Closed-loop optimization:** C++ multi-objective adaptive weighting for automatic alignment.

In repeated experiments, the final mean MTF exceeded 70%, and each alignment run took about 10 minutes.

Current Embodied AI Work
======

**Real-Robot Language-Conditioned Manipulation**

I have established an SO-101 leader-follower research platform with fixed external and wrist RGB cameras. The current preliminary study connects teleoperation, synchronized multimodal recording, real-robot policy training, and deployment evaluation.

| Evidence | Current status |
|---|---|
| Task protocol | Three language-conditioned tabletop sorting instructions |
| Dual-view dataset | 60 real-robot episodes with episode-level 48/6/6 train/validation/test splits |
| Visual imitation baseline | ACT: 8/10 real-robot success on a fixed pick-and-place task |
| Language-conditioned policy | SmolVLA fine-tuning and real-robot rollout completed |
| Current research question | How can dual-view measurement and failure-triggered human correction improve reliability under limited demonstrations? |

The current VLA rollout is a preliminary failure-analysis setting rather than a claimed mature manipulation result: it produces target-directed motion but does not yet reliably complete the full grasp-and-place sequence. This defines the next research problem rather than being hidden by selected success clips.

- [SO-101 real-robot preliminary study](/portfolio/so101-real-robot-vla-preliminary/)
- [Dataset on Hugging Face](https://huggingface.co/datasets/Terra11113/so101_smolvla_color_sort_v1)
- [SmolVLA model on Hugging Face](https://huggingface.co/Terra11113/smolvla_so101_color_sort_v1)

Visual Overview
======

- Freeform USTP automatic alignment and closed-loop optimization
- Wavefront-aberration-guided optical alignment
- Real-robot language-conditioned manipulation and VLA evaluation
- FPGA-based line-scan vision inspection
- Metalens simulation for spectral confocal sensing

Explore
======

- [Duo Xu](/about/) - personal background, PhD application interests, and contact
- [Research Projects](/portfolio/) - selected research and engineering projects
- [Publications](/publications/) - paper, DOI, and intellectual property
- [Academic CV](/files/CV_DuoXu_PhD_2027.pdf)
