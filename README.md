# FPGA-Based Independent Safety Guardian for Autonomous Systems

An RTL-based safety guardian implemented on the **Microchip PolarFire Splash Kit**, designed to detect hazardous conditions and trigger independent hardware intervention in autonomous systems.

## Problem Statement
Self-driving cars operating in unstructured and unpredictable road environments face significant safety challenges, including uneven road surfaces, poorly marked or absent lanes, unpredictable movements of pedestrians, inconsistent adherence to traffic rules, and animals suddenly crossing the vehicle's path

## Proposed Solution
Our FPGA-based safety guardian independently monitors timestamped obstacle records, vehicle-state data, and proposed trajectories received through Gigabit Ethernet. Dedicated RTL logic performs:

- **Data freshness monitoring** to detect stale or missing perception updates.
- **Input integrity checking** to identify corrupted obstacle records.
- **Conservative hazard prediction** to estimate potential obstacle motion.
- **Trajectory safety verification** against a predefined safety envelope.
- **Hardware fail-safe intervention** through a dedicated GPIO output when safety conditions are violated.

## System Architecture
<img width="1600" height="800" alt="image" src="https://github.com/user-attachments/assets/d8070b76-4b79-4212-b2c1-062134df62d7" />

*Architecture of our proposed independent hardware safety-monitoring pipeline.*

## Hardware Platform
<img width="698" height="500" alt="image" src="https://github.com/user-attachments/assets/5553684f-4241-4660-9c70-ce1f8d83c53f" />

*Target FPGA platform - PolarFire FPGA Splash Kit featuring Gigabit Ethernet connectivity and dedicated GPIO for safety intervention.*

## Innovation
Unlike conventional collision detectors, our approach treats **stale, corrupted, and missing perception data as safety hazards in their own right**. By combining data validation, hazard-motion prediction, and trajectory verification in a single FPGA-based guardian, the design enables independent intervention without relying on the primary software control loop.

## Validation & Expected Outcome
The prototype will be evaluated using simulated sensor streams and hardware-in-the-loop testing, including:

- **Fault injection:** stale timestamps, coordinate corruption, and packet dropouts.
- **Hazard scenarios:** unsafe trajectories and predicted obstacle conflicts.
- **Hardware evaluation:** decision latency, timing behavior, and FPGA resource utilization.

The expected deliverables include synthesizable RTL modules, verification testbenches, and measured hardware results.

## Expected Impact
This project demonstrates a reusable approach to **independent, predictable hardware safety enforcement** for autonomous mobile robots and research vehicles. It is a research prototype, not a certified automotive safety system.
