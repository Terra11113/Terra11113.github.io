---
title: "SO-101 Real-Robot Language-Conditioned Manipulation and VLA Preliminary Study"
excerpt: "A dual-view SO-101 real-robot platform for language-conditioned manipulation, ACT baselines, SmolVLA rollout evaluation, and limited-data failure analysis."
collection: portfolio
period: "Jul 2026 - Present"
timeline_date: "Jul 2026"
order: 6
---

<style>
.evidence-table{width:100%;border-collapse:collapse;margin:1rem 0 1.5rem}.evidence-table th,.evidence-table td{border:1px solid #ddd;padding:.5rem .65rem;text-align:left}.evidence-table th{background:#f4f7fa}.status-complete{color:#1c7c3a;font-weight:700}.status-progress{color:#8a5a00;font-weight:700}.project-link-list li{margin:.35rem 0}
</style>

## Project Overview

This preliminary study establishes a low-cost, real-robot testbed for investigating language-conditioned manipulation under limited demonstrations. The goal is not to claim general-purpose autonomous manipulation. It is to make the complete physical pipeline observable: data collection, policy training, real-robot rollout, stage-level evaluation, and failure analysis.

**Role:** platform integration, teleoperation, dataset collection, policy training, rollout evaluation, and failure analysis  
**Platform:** SO-101 leader-follower arm; fixed external RGB camera; wrist RGB camera; LeRobot, ACT, and SmolVLA  
**Keywords:** real-robot learning, language-conditioned manipulation, VLA, ACT, multimodal data, failure analysis, human-in-the-loop learning

## Platform and Task Protocol

The platform uses a leader arm for teleoperation and an SO-101 follower arm for physical execution. A fixed external camera observes the workspace, while a wrist camera provides a local manipulation view. The initial task family contains colored cubes, two target boxes, and three fixed natural-language instructions:

- `pick up the red cube and put it in the left box`
- `pick up the blue cube and put it in the right box`
- `pick up the yellow cube and put it in the left box`

Each episode records synchronized RGB observations, robot state, robot action, timestamps, task text, and episode metadata. Dataset splitting is performed at the episode level rather than by adjacent frames.

## Completed Evidence

<table class="evidence-table">
  <thead><tr><th>Component</th><th>Evidence</th><th>Status</th></tr></thead>
  <tbody>
    <tr><td>Hardware and teleoperation</td><td>Calibrated SO-101 leader-follower control with external and wrist RGB views.</td><td class="status-complete">Completed</td></tr>
    <tr><td>Language-conditioned dataset</td><td>60 dual-view real-robot episodes; 20 demonstrations for each of three instructions; 48/6/6 episode-level train/validation/test split.</td><td class="status-complete">Completed</td></tr>
    <tr><td>Visual imitation baseline</td><td>ACT achieved 8/10 real-robot success on a fixed red-cube pick-and-place task.</td><td class="status-complete">Completed</td></tr>
    <tr><td>Language-conditioned policy</td><td>SmolVLA fine-tuning, model release, and real-robot rollout were completed for the three-instruction setting.</td><td class="status-complete">Completed</td></tr>
    <tr><td>Reliable multi-task VLA grasping</td><td>Initial rollout is target-directed but does not yet reliably complete the descend-grasp-lift-place sequence under the limited demonstration budget.</td><td class="status-progress">Preliminary / ongoing</td></tr>
  </tbody>
</table>

## ACT Baseline

ACT is retained as a non-language visual imitation-learning baseline. On a fixed red-cube pick-and-place task, the platform achieved 8/10 real-robot successes. This establishes that the hardware, cameras, teleoperation, data format, training, and deployment loop can support closed-loop manipulation under a controlled task condition.

## SmolVLA Preliminary Evaluation

SmolVLA was fine-tuned on the 60-episode, three-instruction dataset and deployed on the real robot. The current policy can produce target-directed motion, but it does not yet reliably complete the full grasp-and-place sequence. This is reported as a preliminary failure regime rather than presented as a successful multi-task benchmark.

The current evidence motivates a more specific research question: how much of this failure is caused by visual observability, grasp-stage action completion, initial-state variation, or insufficient targeted corrective data?

## Next Research Question

**Under the same human operation-time budget, can failure-triggered short corrective demonstrations improve a dual-view language-conditioned manipulation policy more efficiently than collecting additional full demonstrations?**

The next experiment will compare generic new demonstrations, complete failed trajectories, and labeled short recovery windows. The comparison will use the same task layout, camera configuration, rollout protocol, and stage-level failure taxonomy.

## Reproducibility Links

<ul class="project-link-list">
  <li><a href="https://huggingface.co/datasets/Terra11113/so101_smolvla_color_sort_v1">Dual-view SO-101 language-conditioned dataset on Hugging Face</a></li>
  <li><a href="https://huggingface.co/Terra11113/smolvla_so101_color_sort_v1">Fine-tuned SmolVLA model on Hugging Face</a></li>
  <li><a href="https://github.com/Terra11113/robotics-learning">Robotics learning notes and supporting code on GitHub</a></li>
</ul>
