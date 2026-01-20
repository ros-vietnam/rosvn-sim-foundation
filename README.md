# ROS Vietnam – Simulation Foundation  
`rosvn-sim-foundation`

> **A standardized, reproducible simulation foundation for ROS 2 algorithm research, education, and open-source collaboration in Vietnam.**

---
## 1. Overview

**ROS Vietnam Simulation Foundation** is the official baseline simulation repository of the **ROS Vietnam** community.

This repository provides a **clean, deterministic, and extensible simulation environment** for developing, testing, and benchmarking robotics algorithms using **ROS 2**.

Our goal is to eliminate fragmentation in simulation setups and enable:
- High-quality academic research
- Serious algorithm development
- Long-term open-source collaboration
- Industry-grade engineering practices

This repository is **not a tutorial collection**.  
It is a **foundation** upon which all ROS Vietnam algorithmic and research projects are built.

---

## 2. Motivation & Problem Statement

Robotics communities often fail to scale because:

- Everyone uses a different simulator setup
- Robot models are inconsistent
- Results are not reproducible
- Algorithms cannot be fairly compared
- Simulation quality is treated as secondary

As a result, collaboration breaks down.

**ROS Vietnam Simulation Foundation** addresses this by defining:
- A **single source of truth** for simulation
- Clear engineering standards
- Reproducible experiments
- Shared evaluation assumptions

> *Strong algorithms require a strong simulation baseline.*

---

## 3. Scope & Non-Goals

### In Scope
- ROS 2 simulation baseline
- Gazebo / Ignition / Gazebo Harmonic
- Robot modeling (URDF / Xacro)
- Sensor simulation (LiDAR, camera, IMU)
- Deterministic launch & configuration
- CI-friendly simulation setups

### Explicitly Out of Scope
- Hardware drivers
- Real robot bring-up
- Vendor-specific integrations
- End-user applications

This repository **does not compete** with Nav2, Isaac Sim, or commercial tools.  
It complements them with **community-driven rigor and openness**.

---

## 4. Supported Technologies

| Component | Status |
|---------|-------|
| ROS 2 (Humble / Jazzy) | ✅ |
| Gazebo Classic | ⚠️ Legacy |
| Gazebo Harmonic / Ignition | ✅ Primary |
| URDF / Xacro | ✅ |
| RViz2 | ✅ |
| Linux (Ubuntu LTS) | ✅ |

---

## 5. Repository Structure

```
rosvn-sim-foundation/
├── README.md
├── docs/
│ ├── architecture.md
│ ├── simulation-standards.md
│ ├── ros2-best-practices.md
│ └── contribution-guidelines.md
├── worlds/
│ ├── indoor/
│ ├── outdoor/
│ └── benchmark/
├── robots/
│ ├── differential_drive/
│ ├── ackermann/
│ └── modular_base/
├── sensors/
│ ├── lidar/
│ ├── camera/
│ └── imu/
├── launch/
├── config/
├── tools/
└── .github/
```


---

## 6. Architecture Principles

This repository follows strict architectural principles:

### 6.1 Determinism
- Identical inputs must produce identical outputs
- Simulation time is explicitly controlled
- Randomness must be seedable

### 6.2 Modularity
- Robots, sensors, and worlds are decoupled
- Algorithms must not depend on specific worlds
- Swappable components by design

### 6.3 Transparency
- No hidden parameters
- All configs version-controlled
- Explicit assumptions documented

### 6.4 Reproducibility
- Experiments must be replayable
- Results must be explainable
- Benchmarks must be fair

---

## 7. Simulation Standards

All components in this repository must comply with:

- Metric units (SI)
- Right-handed coordinate systems
- Consistent frame naming
- ROS 2 naming conventions
- Clear TF tree definitions

Detailed standards are defined in: `docs/simulation-standards.md`


---

## 8. Getting Started

### 8.1 Prerequisites
- Ubuntu 22.04 or later
- ROS 2 Humble or newer
- Gazebo Harmonic

### 8.2 Build

```bash
mkdir -p ~/rosvn_ws/src
cd ~/rosvn_ws/src
git clone https://github.com/ros-vietnam/rosvn-sim-foundation.git
cd ..
colcon build



