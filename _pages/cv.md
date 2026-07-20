---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

[Download full academic CV](/files/CV_DuoXu_PhD_2027.pdf)

Education
======

**Tianjin University**  
M.Eng. in Electronic Information, recommended admission  
Sep 2024 - Present

- Advisor: Prof. Xiaodong Zhang
- Average score: 87.88/100; rank: 15/115
- Research focus: freeform ultra-short-throw projection systems, image-quality-driven alignment, optical simulation, closed-loop optimization, and measurement-guided real-robot manipulation

**University of Science and Technology Beijing**  
B.Eng. in Mechanical Engineering  
Sep 2020 - Jul 2024

- Average score: 83.62/100; rank: 17/178

**University of Science and Technology Beijing**  
Second Major Coursework in Computer Science and Technology  
Sep 2021 - Jul 2024

- Completed systematic training in programming, data structures, image processing, and computational approaches to engineering problems

Research and Project Experience
======

**Automatic Alignment and Image-quality Optimization of Freeform USTP Systems**  
Master's research project, 2024 - Present

- Built a Zemax non-sequential optical model matched to the physical prototype and simulated 6-DOF freeform-mirror pose perturbations.
- Designed a structured-target image acquisition and analysis workflow to evaluate geometric distortion and MTF-related image quality.
- Implemented a C++ multi-objective adaptive weighting optimizer for closed-loop optical alignment.
- Integrated optical simulation, industrial-camera acquisition, a 6-DOF precision platform, image-quality evaluation, optimization software, and motion execution.
- In 10 repeated experiments, the final mean MTF exceeded 70%, and each alignment run took about 10 minutes.

**Real-Robot Language-Conditioned Manipulation and VLA Failure Analysis**  
SO-101 / LeRobot research platform, Jul 2026 - Present

- Built and calibrated a dual-view SO-101 leader-follower manipulation platform with external and wrist RGB cameras; implemented teleoperation, synchronized RGB/state/action recording, and hardware-safe real-robot rollout workflows.
- Curated a 60-episode dual-camera dataset for three language-conditioned color-sorting instructions, with episode-level train/validation/test splits and reproducible Hugging Face dataset/model releases.
- Established a visual imitation-learning ACT baseline with 8/10 real-robot success on a fixed pick-and-place task; fine-tuned and deployed SmolVLA for multi-instruction manipulation and structured rollout failure analysis.

**Wavefront-aberration-guided Automatic Alignment of Optical Lens Groups**  
Optical alignment software and experiment, 2024 - Present

- Studied wavefront-aberration-guided alignment as a complementary feedback strategy to MTF/PSF-based alignment.
- Participated in modeling the relationship between low-order Zernike coefficients and lens-group misalignment parameters.
- Developed Qt/C++ modules based on ZOS-API for Zemax automation, perturbation scanning, ray tracing, image-quality analysis, and result export.
- Supported phase-deflectometry experiments for off-axis optical components and systems, including acquisition workflow debugging and simulation-experiment comparison.

**Chromatic-aberration-enhanced Metalens Design and Simulation for Spectral Confocal Sensing**  
Undergraduate thesis project, 2023 - 2024

- Designed chromatic-aberration-enhanced metalenses for compact spectral confocal displacement sensing.
- Derived wavelength-dependent phase profiles and meta-atom rotation rules from Fermat's principle, generalized Snell's law, and geometric phase theory.
- Used FDTD Lumerical to screen nanofin meta-atoms and analyze phase/transmittance responses.
- Built MATLAB scripts for array rotation matrices and visualization, then evaluated RGB wavelength separation and focal behavior through optical-field simulation.

**FPGA-based Line-scan Vision Inspection System**  
Industrial vision project, 2023 - 2024

- Developed the software-side image-processing pipeline for high-speed line-scan inspection.
- Built C++ modules for line-scan image reconstruction, preprocessing, feature extraction, candidate-region analysis, and result output.
- Refactored parts of the algorithm into HLS/FPGA-friendly processing blocks considering streaming data, memory access, fixed-point constraints, and pipeline execution.
- Participated in software-hardware co-debugging, parameter tuning, and consistency checks between software simulation and hardware-oriented implementation.

Publications and Intellectual Property
======

- Jiang Li*, Duo Xu*, Changshuai Fang, Zexiao Li, and Xiaodong Zhang, "Sensitivity-informed multi-objective adaptive weighting method for automatic alignment of freeform USTP systems," *Optics Express*, published online, 2026. DOI and page numbers pending. *Equal contribution.*
- Patent application under review: "An optimization and alignment method for imaging and display systems based on physical-model-driven adaptive weighting" (translated title).

Technical Skills
======

- **Programming and software:** C++, Qt, MATLAB, Python, CMake, Git
- **Image processing:** OpenCV, Halcon, image preprocessing, structured target analysis, feature extraction, geometric-distortion evaluation, MTF-related image-quality assessment
- **Optical design and simulation:** Zemax OpticStudio, ZOS-API, FDTD Lumerical, non-sequential ray tracing, tolerance/error analysis, optical-field simulation
- **Mechanical modeling and simulation:** SolidWorks, AutoCAD, Ansys Workbench
- **Experimental and engineering tools:** industrial cameras, 6-DOF motion platforms, line-scan vision systems, HLS/FPGA adaptation
- **Robotics and embodied AI:** LeRobot, SO-101 leader-follower teleoperation, PyTorch, Hugging Face, real-robot data collection, ACT, SmolVLA, multimodal rollout evaluation
- **Technical writing:** academic manuscripts, patent documents, project reports, and formal research presentations

English Proficiency
======

- IELTS Academic: Overall 6.5; Listening 7.5, Reading 7.0, Writing 6.5, Speaking 5.5
- CET-6 and CET-4 passed

Selected Awards and Honors
======

- Second-Class Academic Scholarship, Tianjin University, 2025
- People's Scholarship, University of Science and Technology Beijing, 2021, 2022, and 2023
- Outstanding Student Cadre, University of Science and Technology Beijing, 2022 and 2023
- Third Prize, National College Students Mathematics Competition, 2021
- Third Prize, National English Competition for College Students, 2022
