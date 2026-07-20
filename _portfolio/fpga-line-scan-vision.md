---
title: "FPGA-based Line-scan Vision Inspection System"
excerpt: "High-speed industrial vision project involving line-scan image reconstruction, C++ image processing, and HLS/FPGA-oriented algorithm adaptation."
collection: portfolio
period: "Oct 2024 - Nov 2024"
timeline_date: "Oct 2024"
order: 2
thumbnail: "/images/research_fpga_line_scan.png"
---

<style>
.project-album{display:flex;gap:1rem;overflow-x:auto;padding:0.25rem 0 1rem;margin-top:0.75rem;scroll-snap-type:x proximity}.project-album__item{flex:0 0 320px;scroll-snap-align:start}.project-album__item img{display:block;width:320px;height:210px;object-fit:contain;background:#fff;border:1px solid #ddd}.project-album__item figcaption{font-size:0.85em;color:#666;margin-top:0.35rem;text-align:center}
</style>

## Project Overview

This project focused on a high-speed line-scan vision inspection system for industrial scenarios where area-scan imaging struggles to balance field of view, resolution, and real-time throughput. The project combined image-processing algorithm development with FPGA-oriented implementation considerations.

**Role:** Software-side image processing and hardware-oriented algorithm adaptation  
**Period:** 2024.10 - 2024.11  
**Keywords:** line-scan vision, industrial inspection, C++, image reconstruction, image preprocessing, HLS, FPGA adaptation, software-hardware co-debugging

## Technical Focus

- Reconstructed line-scan image data and built preprocessing modules for industrial visual inspection.
- Implemented feature extraction, candidate-region analysis, and detection-result output in C++.
- Refactored parts of the algorithm into HLS/FPGA-friendly processing blocks.
- Considered streaming data organization, memory access patterns, fixed-point constraints, and pipeline execution.

## My Role

I mainly worked on the software-side image-processing workflow and participated in hardware-oriented algorithm adaptation. During debugging, I checked intermediate results, tuned parameters, and verified consistency between software behavior and FPGA-oriented processing logic.

## Outcome

This project gave me practical experience in industrial machine vision, real-time image processing, and hardware-aware algorithm implementation. It also helped me understand how algorithm design changes when throughput, memory access, and hardware execution constraints become central.

## Album

<div class="project-album">
  <figure class="project-album__item"><img src="/images/project_fpga_system.png" alt="Line-scan imaging system"><figcaption>Line-scan optical and imaging setup.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_fpga_zynq.png" alt="ZYNQ processing architecture"><figcaption>ZYNQ-based processing architecture.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_fpga_pipeline.png" alt="Processing pipeline"><figcaption>Image-processing pipeline and data flow.</figcaption></figure>
  <figure class="project-album__item"><img src="/images/project_fpga_stripes.png" alt="Stripe pattern"><figcaption>Structured stripe image used in inspection experiments.</figcaption></figure>
</div>
