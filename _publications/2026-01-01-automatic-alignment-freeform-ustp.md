---
title: "Sensitivity-informed Multi-objective Adaptive Weighting Method for Automatic Alignment of Freeform USTP Systems"
collection: publications
category: manuscripts
permalink: /publication/automatic-alignment-freeform-ustp
excerpt: "Image-quality-driven automatic alignment for freeform ultra-short-throw projection systems."
date: 2026-01-01
venue: "Optics Express"
thumbnail: "/images/ustp_publication_thumbnail.png"
authors: 'Jiang Li<sup>†</sup>, <strong>Duo Xu<sup>†</sup></strong>, Changshuai Fang, Zexiao Li, and Xiaodong Zhang'
publication_info: '<i>Optics Express</i>, Vol. 34, No. 11, pp. 20358-20378, 2026'
note: '<sup>†</sup> Equal contribution'
doi: "10.1364/OE.34.020358"
officialurl: "https://opg.optica.org/oe/fulltext.cfm?uri=oe-34-11-20358"
paperurl: "/files/USTP_Automatic_Alignment_Manuscript_DuoXu.pdf"
supplementurl: "/files/USTP_Automatic_Alignment_Supplemental_Document.pdf"
share: false
comments: false
---

<p style="font-size:1.05em; margin-bottom:0.4rem;">
Jiang Li<sup>†</sup>, <strong>Duo Xu<sup>†</sup></strong>, Changshuai Fang, Zexiao Li, and Xiaodong Zhang
</p>

<p style="margin-top:0; color:#666;">
State Key Laboratory of Precision Measurement Technology and Instruments, Tianjin University<br>
<sup>†</sup> Equal contribution
</p>

<p style="margin:1rem 0 1.5rem;">
  <a class="btn" style="background:#2f7f8f; border-color:#2f7f8f; color:#fff;" href="/files/USTP_Automatic_Alignment_Manuscript_DuoXu.pdf">PDF</a>
  <a class="btn" style="background:#2f7f8f; border-color:#2f7f8f; color:#fff;" href="/files/USTP_Automatic_Alignment_Supplemental_Document.pdf">Supplemental Document</a>
  <a class="btn" style="background:#2f7f8f; border-color:#2f7f8f; color:#fff;" href="https://opg.optica.org/oe/fulltext.cfm?uri=oe-34-11-20358">Journal Page</a>
  <a class="btn" style="background:#2f7f8f; border-color:#2f7f8f; color:#fff;" href="https://doi.org/10.1364/OE.34.020358">DOI</a>
</p>

<figure style="margin:1.2rem 0 1.6rem;">
  <img src="/images/ustp_optical_principle.png" alt="Optical layout of the freeform ultra-short-throw projection system" style="width:100%;">
  <figcaption style="font-size:0.9em; color:#666; text-align:center; margin-top:0.45rem;">
    Optical layout of the freeform USTP system. The freeform reflecting mirror folds the optical path and serves as the key adjustable element during automatic alignment.
  </figcaption>
</figure>

Abstract
======

Catadioptric ultra-short-throw projection (USTP) systems are compact but difficult to align because pose errors of the freeform mirror affect both geometric distortion and modulation transfer function (MTF). These effects are strongly coupled: at coarse alignment stages, geometric distortion is usually the dominant constraint, while at finer stages image sharpness and MTF become more important.

This work studies automatic alignment as an image-quality-driven, multi-objective optimization problem. Full-parameter six-degree-of-freedom simulations are used to analyze how freeform mirror pose perturbations influence distortion and MTF. Based on these sensitivity patterns, the paper proposes a physics-guided adaptive weighting strategy that changes the optimization emphasis across alignment stages.

The resulting framework connects optical simulation, structured image acquisition, distortion and MTF-related metric extraction, adaptive objective weighting, and closed-loop motion execution. It provides an automatic alignment strategy for freeform USTP systems while also offering a reference for modeling the relationship between pose errors and image-quality degradation in complex optical systems.

Method
======

<figure style="margin:1.2rem 0 1.6rem;">
  <img src="/images/ustp_method_overview.png" alt="Method overview of the physics-guided automatic alignment framework" style="width:100%;">
  <figcaption style="font-size:0.9em; color:#666; text-align:center; margin-top:0.45rem;">
    Overview of the proposed physics-guided automatic alignment framework, including USTP system analysis, objective-function design, hardware feedback, and closed-loop platform actuation.
  </figcaption>
</figure>

The method begins with a non-sequential optical model of the freeform USTP system. Six-degree-of-freedom perturbations of the freeform mirror are scanned to obtain the response laws between mirror pose errors and image-quality metrics. The analysis shows that different distortion modes are more sensitive to specific subsets of degrees of freedom, while the relative importance of distortion and MTF changes with the alignment stage.

Based on this observation, the alignment process is formulated as a staged multi-objective optimization problem. Instead of using fixed weights for all image-quality metrics, the proposed method adapts the weights according to the current alignment condition. Distortion-related metrics receive stronger emphasis when the system is far from the design state, while MTF-related metrics become more influential as the residual errors decrease.

In the experimental workflow, a structured target image is captured by an industrial camera. Image-processing procedures are used to extract geometric distortion and MTF-related indicators from the captured image. These metrics are then fed into a C++ optimization program, which computes the next six-degree-of-freedom adjustment command for the motion platform. The system repeats this measurement, evaluation, optimization, and execution loop until the image quality converges.

Results
======

<figure style="margin:1.2rem 0 1.6rem;">
  <img src="/images/ustp_result_statistics.png" alt="Robustness and statistical comparison of automatic alignment metrics" style="width:100%;">
  <figcaption style="font-size:0.9em; color:#666; text-align:center; margin-top:0.45rem;">
    Robustness and statistical evaluation across repeated automatic alignment trials.
  </figcaption>
</figure>

The proposed method was validated on a physical freeform USTP automatic alignment platform. Across repeated experiments with different initial conditions, the method achieved stable convergence from coarse alignment to fine alignment. The final mean MTF exceeded 70%, and each alignment run took about 10 minutes.

Compared with manual adjustment, the automatic method reduced result dispersion and improved repeatability. The local high-frequency line-pair regions became clearer after alignment, and the geometric boundaries of the projected target were more stable. These results indicate that explicit use of optical sensitivity information can make the optimization process more robust than a fixed-weight image-quality objective.

<figure style="margin:1.2rem 0 1.6rem;">
  <img src="/images/ustp_result_visual_comparison.png" alt="Local image-quality comparison after automatic alignment" style="width:100%; border:1px solid #ddd;">
  <figcaption style="font-size:0.9em; color:#666; text-align:center; margin-top:0.45rem;">
    Local image-quality comparison after automatic alignment. High-frequency line-pair regions become clearer and more stable across selected field positions.
  </figcaption>
</figure>

Citation
======

Jiang Li<sup>†</sup>, Duo Xu<sup>†</sup>, Changshuai Fang, Zexiao Li, and Xiaodong Zhang. "Sensitivity-informed multi-objective adaptive weighting method for automatic alignment of freeform USTP systems." <i>Optics Express</i> 34(11), 20358-20378, 2026. DOI: 10.1364/OE.34.020358.

<sup>†</sup> Equal contribution.
