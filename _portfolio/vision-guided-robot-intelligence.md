---
title: "Robotics Foundations: State Estimation and Visual Servoing"
excerpt: "Robotics foundations covering Kalman/EKF-based localization, visual servoing, and measurement-guided perception-control reasoning for physical systems."
collection: portfolio
period: "May 2026 - Present"
timeline_date: "May 2026"
order: 5
thumbnail: "/images/robotics/robot_ekf_heading_error.png"
---

<style>
.project-figure-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(280px,1fr));gap:1rem;margin:1rem 0 1.5rem}.project-figure-grid figure{margin:0}.project-figure-grid img{display:block;width:100%;height:220px;object-fit:contain;background:#fff;border:1px solid #ddd}.project-figure-grid figcaption{font-size:.85em;color:#666;margin-top:.35rem;text-align:center}.result-table{width:100%;border-collapse:collapse;margin:.75rem 0 1.25rem}.result-table th,.result-table td{border:1px solid #ddd;padding:.45rem .55rem;text-align:left}.result-table th{background:#f7f7f7}
</style>

## Project Overview

This project documents my transition from optical alignment and image-based feedback systems toward robotics and embodied intelligence. The work is organized into three connected blocks: robot state estimation with Kalman Filter and EKF, visual servoing and vision-based control, and a planned SO-ARM/LeRobot manipulation pipeline for imitation learning and VLA-style experiments.

**Role:** Robotics learning, simulation, notebook implementation, and planned real-robot experimentation  
**Period:** 2026.5 - Present  
**Keywords:** Kalman Filter, EKF, robot localization, odometry drift, camera dropout, visual servoing, IBVS, DINOv2, LeRobot, SO-ARM, imitation learning, VLA

## GitHub Repository

The code, notes, scripts, figures, and staged learning materials are maintained in my GitHub repository: [robotics-learning](https://github.com/Terra11113/robotics-learning).

## Part 1: Kalman/EKF-based Mobile Robot Localization

This block focuses on the question: how can a robot maintain a usable estimate of its own state when sensors are noisy, biased, low-rate, or intermittently unavailable? I built the experiments step by step, starting from a basic 2D Kalman Filter and then moving toward odometry-camera sensor fusion and an EKF unicycle model.

### Experiment Process

The first experiment defines a 2D mobile robot state as `[px, py, vx, vy]`. The simulated sensor only observes position `[px, py]`, while the state transition matrix uses velocity to predict the next position. The script generates a ground-truth trajectory, adds Gaussian position noise, runs the FilterPy `predict()` and `update()` loop, then saves trajectory/error plots and an RMSE table.

The second experiment introduces two complementary sensors. Odometry provides high-rate velocity estimates, but with bias and Gaussian noise, so position error accumulates over time. Camera measurements provide lower-rate absolute position observations, but they are noisy and can drop out. The filter uses odometry for continuous prediction and only performs the camera update when a valid measurement is available; missing camera measurements are marked with `NaN` plus an availability mask, rather than being treated as `[0, 0]`.

The third experiment extends the model to a nonlinear unicycle robot with state `[px, py, theta]` and control `[v, omega]`. Odometry controls drive nonlinear prediction, while sparse camera positions update `[px, py]`. Because the motion model contains `cos(theta)` and `sin(theta)`, the covariance propagation uses a motion Jacobian, making this an EKF-style localization demo rather than a purely linear KF example.

### Results

<table class="result-table">
  <thead>
    <tr><th>Experiment</th><th>Setup</th><th>Key result</th></tr>
  </thead>
  <tbody>
    <tr><td>2D Kalman Filter</td><td>Noisy 2D position measurements; state `[px, py, vx, vy]`.</td><td>Position RMSE decreased from 5.67 for raw measurements to 2.55 after filtering, about a 55% reduction.</td></tr>
    <tr><td>Linear odometry-camera fusion</td><td>Odometry bias `[0.05, -0.03]`, odometry noise 0.08, camera noise 2.0, camera interval 5, 37.5% actual camera dropout.</td><td>Fusion RMSE was 3.09, lower than odometry-only RMSE 4.08. The experiment demonstrates continuous prediction during dropout and correction when camera measurements return.</td></tr>
    <tr><td>EKF unicycle localization</td><td>Nonlinear unicycle motion, odometry control noise/bias, sparse camera position update.</td><td>Position RMSE decreased from 0.671 for odometry-only to 0.466 with EKF fusion. Heading RMSE decreased from 5.63 degrees to 2.45 degrees.</td></tr>
  </tbody>
</table>

### Outputs

<div class="project-figure-grid">
  <figure><img src="/images/robotics/robot_kf_2d_trajectory.png" alt="2D Kalman Filter trajectory"><figcaption>2D Kalman Filter: noisy position measurements are fused with a constant-velocity motion model.</figcaption></figure>
  <figure><img src="/images/robotics/robot_linear_fusion_trajectory.png" alt="Linear odometry-camera fusion trajectory"><figcaption>Linear multi-sensor fusion: odometry keeps the trajectory continuous while sparse camera updates correct drift.</figcaption></figure>
  <figure><img src="/images/robotics/robot_ekf_unicycle_trajectory.png" alt="EKF unicycle localization trajectory"><figcaption>EKF unicycle localization with nonlinear motion, odometry drift, and sparse camera measurements.</figcaption></figure>
  <figure><img src="/images/robotics/robot_ekf_position_error.png" alt="EKF position error comparison"><figcaption>Position error comparison for odometry-only, camera measurement, and EKF fusion.</figcaption></figure>
  <figure><img src="/images/robotics/robot_camera_dropout_timeline.png" alt="Camera measurement dropout timeline"><figcaption>Camera measurement attempts, valid updates, and dropout periods used in the fusion experiments.</figcaption></figure>
</div>

## Part 2: Visual Servoing and Vision-based Control

This block studies how image measurements can be converted into robot motion. It connects my previous 6-DOF vision-guided optical alignment experience with robot visual servoing, where the controller uses image-plane feature error rather than only offline image-quality evaluation.

### Experiment Process

The notebook first establishes the geometry needed for robotic vision: coordinate frames, SE(3) transforms, PnP interface meaning, and hand-eye calibration interfaces. The goal is to understand how a visual target measured in the camera frame can eventually become a robot motion command in the base or end-effector frame.

The core IBVS experiment uses four point features. Each point contributes a `2 x 6` interaction matrix, and the four points are stacked into an `8 x 6` system that maps camera twist to image feature velocity. The controller computes image feature error, solves a damped least-squares control step, updates the camera-frame 3D points, and records feature trajectories, error norms, and camera twist commands.

I also tested depth sensitivity and robustness settings. The depth-bias experiment compares how incorrect depth affects convergence. The robust-control plan further introduces damped pseudo-inverse, velocity limits, visual noise, command delay, dropout, and safety rules such as outputting zero velocity when no visual feature is available.

### Results and Interpretation

The baseline IBVS output shows that feature points move toward their desired image locations and the feature-error norm decreases over time. The camera twist plot makes the control signal explicit, rather than treating visual servoing as a black box. The depth-bias comparison is important because IBVS depends on depth in the interaction matrix: wrong depth can slow convergence, change velocity magnitude, or introduce less stable transient behavior.

This stage is not presented as a full real-robot controller yet. Its value is that it verifies the perception-control chain at the level of geometry, feature error, interaction matrix shape, and command generation. It also prepares the later learning stage: robot policies still need well-defined observations, actions, timing, and safety constraints.

### Outputs

<div class="project-figure-grid">
  <figure><img src="/images/robotics/robot_ibvs_baseline_results.png" alt="IBVS baseline results"><figcaption>IBVS baseline: image feature trajectories, feature-error convergence, and 6D camera twist commands.</figcaption></figure>
  <figure><img src="/images/robotics/robot_ibvs_depth_bias.png" alt="IBVS depth-bias sensitivity"><figcaption>Depth-bias sensitivity: comparing how assumed depth affects visual-servo convergence.</figcaption></figure>
</div>

## Connection to Real-Robot Manipulation

These foundations now inform a separate [SO-101 real-robot language-conditioned manipulation study](/portfolio/so101-real-robot-vla-preliminary/). The state-estimation block teaches how to reason about uncertainty and missing measurements; the visual-servoing block teaches how image error can become bounded robot motion. The real-robot study applies this discipline to multimodal data collection, policy rollout evaluation, and failure analysis.
