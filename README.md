### Hi, I'm Raahim

Robotics engineer working at the intersection of first-principles physics, numerical methods, and modern ML. I like building systems that are both mathematically rigorous and deployable on real hardware.

Most of what's below follows the same spine: **derive the physics → learn what the physics can't close → benchmark it honestly against the classical baseline → port it to something that runs in a control loop.** The interesting part is usually where the model *loses*, so that's what I try to publish.

**Now building:** [wildfire-vtol](https://github.com/raahimnawaz/wildfire-vtol), a simulated fleet of VTOL drones that maps wildfires and feeds a field fire forecast, and an F1 simulator that runs my vehicle-dynamics work against real 2026 telemetry.

📫 [LinkedIn](https://www.linkedin.com/in/raahim-nawaz-9ab64220b/)

---

#### Robot systems

**[workbench-copilot](https://github.com/raahimnawaz/workbench-copilot)** · *Python / LeRobot / SO-101 / ESP32 / KiCad*
A voice-driven lab partner with an SO-101 arm, built for the Meta Global AI Developer Hackathon 2026. A top-down camera finds a named tool on the desk at 0.5 mm per pixel, and damped-least-squares IK with minimum-jerk moves picks it up and puts it away. Every pose of a pick is solved and checked against joint limits, servo temperature and a floor clearance before the first motor moves; the IK round-trips 200 of 200 bench poses within **0.2 mm and 0.5°**. Spoken arm commands run on-device and only execute when a local Llama 3.2 3B and a rule-based parser agree: **0 wrong moves** on 117 unseen phrasings (the model alone made 20), in **0.25 s** against 4.4 s through the cloud. It also reads the breadboard with SAM 3.1 and fixes and flashes the firmware.

**[vision_demos](https://github.com/raahimnawaz/vision_demos)** · *Python / ROS 2 / PyTorch / OpenCV / Arduino*
A closed perception → decision → actuation loop: webcam gestures drive a robot base, both as a plain Python loop and as a ROS 2 node graph sharing one controller. A debounced state machine (confidence gate, stability requirement, dead-man timeout) turns a twitchy gesture classifier into safe `(v, ω)` commands for sim, Arduino or HID backends.

#### Control & estimation

**[wildfire-vtol](https://github.com/raahimnawaz/wildfire-vtol)** · *C++ / AVR / Wokwi*
Quaternion attitude estimation and control on an ATmega2560 with no floating-point unit, against a rigid-body plant written as a custom Wokwi chip (Euler's equations, RK4, exponential-map integration). Mahony fusion with gyro-bias estimation feeds a PD law on quaternion error. Measured in software-in-the-loop: fixing a bus-speed reset and a blocking display call took the loop from **22.9 Hz to 179 Hz**, and the unwinding fix turns a 372° detour into **4.5°**. Yaw is unobservable without a magnetometer, and the README shows how far it drifts. It is the attitude core for Phoenix, a tiltrotor mothership, and four tailsitter Dragonflies that will map wildfires in simulation.

**[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** · *Python / C++ / PyTorch*
Physics-informed parameter estimation for vehicle braking dynamics. Five estimators on the same data (batch optimiser, EKF, MLP and two PINNs) with a model-mismatch study showing which method wins *when*. A network with no assumed functional form recovers the Pacejka friction peak at **0.889** against a true 0.900 from noisy braking data. Ships an allocation-free C++ edge port at **7 ns per EKF step** (**41×** over the same math in scalar Python), 33 KB deployable, zero external dependencies, Python↔C++ parity to 7.4e-9.

**[singularity-robust-control](https://github.com/raahimnawaz/singularity-robust-control)** · *Python / C++ / ROS 2 / Webots*
Schedules damped-least-squares damping as a 3R arm nears a kinematic singularity: through the crossing, the naive inverse Jacobian commands **2,434 rad/s** and the damped law 2.8 rad/s. Ships as header-only C++ held to the Python reference within 1e-9, and as a `ros2_control` plugin on a Webots arm.

#### Perception

**[monocular-vo](https://github.com/raahimnawaz/monocular-vo)** · *Python / PyTorch / OpenCV*
Monocular visual odometry with **metric-scale** trajectory recovery from a single calibrated webcam, using [Depth Anything v2](https://huggingface.co/depth-anything/Depth-Anything-V2-Metric-Indoor-Small-hf) depth + ORB matches + PnP-RANSAC, bypassing the scale ambiguity that classical essential-matrix VO hits. **12.96 % scale error** on a tape-measured 5 m hallway walk; a pose-graph back-end with loop closure cuts ATE by **36 %** on TUM RGB-D.

#### Simulation & ML

**[apex-forecast](https://github.com/raahimnawaz/apex-forecast)** · [live dashboard](https://raahimnawaz.github.io/apex-forecast/)
Bayesian F1 race forecasting for the 2026 regulations. Separates driver from car (**93 %** of finishing-order spread is the car) and beats a fitted starting-grid baseline in walk-forward testing (ranked probability score 0.1026 vs 0.1095).

**[engine-map-pinn](https://github.com/raahimnawaz/engine-map-pinn)**
A PINN rebuilds a full engine map from sparse dyno pulls, and a lap sim runs it on real circuits. Doubling the power buys only **5–6 %** of lap time; re-optimising the racing line saves **53 s** on the Nordschleife.

**[aerospace-surrogate](https://github.com/raahimnawaz/aerospace-surrogate)**
ML airfoil surrogates against thin-airfoil theory: tied in the linear regime, well ahead through stall (R² 0.77 vs −1.77). A nonlinear lifting-line solver takes it to 3D wings, and the Rust port runs **9.8×** faster at 1e-10 parity.

**[wildfire](https://github.com/raahimnawaz/wildfire)** · [live dashboard](https://raahimnawaz.github.io/wildfire/)
Two-stage US West Coast fire prediction on real satellite data: XGBoost ignition at ROC-AUC **0.785**, tested fully out-of-time, and a U-Net spread model at **0.903** that matches Google Research's Next Day Wildfire Spread benchmark.

#### Also

**[flux](https://raahimnawaz.github.io/flux/)**: interactive 2D/3D visualizations of the math I keep reaching for: Jacobians & manipulability ellipsoids, Kalman filtering, Fourier, vector fields, optimization, eigenvectors. Vanilla JS, no build step.
**[neutrino-ml](https://github.com/raahimnawaz/neutrino-ml)**: ML on real ATLAS Open Data (13 TeV W→ℓν). XGBoost separates real-neutrino events at weighted AUC 0.825, and neutrino-p_z reconstruction recovers the W mass at 80.38 GeV (PDG 80.379).
**[quantview](https://github.com/raahimnawaz/quantview)**: Bloomberg-style quant terminal in the shell: Black-Scholes Greeks, CRR/trinomial lattices, Monte Carlo (GBM + Heston), Markowitz and VaR. The NumPy/SciPy math layer is cross-checked against QuantLib.

---

#### Tools

Python · C++ · PyTorch · NumPy / SciPy · ROS 2 · OpenCV · sensor fusion · physics-informed ML · embedded & edge deployment · KiCad
