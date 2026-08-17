### Hi, I'm Raahim

Robotics engineer working at the intersection of first-principles physics, numerical methods, and modern ML. I like building systems that are both mathematically rigorous and deployable on real hardware.

Most of what's below follows the same spine: **derive the physics → learn what the physics can't close → benchmark it honestly against the classical baseline → port it to something that runs in a control loop.** The interesting part is usually where the model *loses*, so that's what I try to publish.

📫 [LinkedIn](https://www.linkedin.com/in/raahim-nawaz-9ab64220b/)

---

#### Vehicle dynamics & control

**[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** · *Python / C++ / PyTorch*
Physics-informed parameter estimation for vehicle braking dynamics. Five estimators on the same data — batch optimiser, EKF, MLP, and two PINNs — with an honest model-mismatch study showing which method wins *when*. Ships an allocation-free C++ edge port: **3,414× EKF speedup** over the Python implementation, which is 99.97 % per-call dispatch — 62 KB binary, zero external dependencies, zero runtime allocations, Python↔C++ parity to 6.7e-9.

**[engine-map-pinn](https://github.com/raahimnawaz/engine-map-pinn)** · *Python / PyTorch*
From a dyno pull to a Nürburgring lap: a PINN reconstructs the full engine torque map from sparse sweeps, then a quasi-steady-state lap sim runs it on real circuit geometry (Silverstone, Spa, Nordschleife). Two findings worth the build — doubling the engine's power buys only **5–6 %** of lap time because most of a lap is grip-limited, while re-optimizing the *racing line* saves **53 s** on the Nordschleife. Validation brackets the SVJ's real 6:44.97 record rather than tuning to hit it.

#### Robotics & perception

**[singularity-robust-control](https://github.com/raahimnawaz/singularity-robust-control)** · *Python / NumPy*
Detect an approaching kinematic singularity in a 3R manipulator and switch to a damped, singularity-robust velocity law before joint velocities blow up. The testbed is chosen so the singularity is exact and hand-derivable — `det(J) = l₁·l₂·sin(q₂)` — and the workspace manipulability map is validated against a closed form via Heron's formula, so the figures can't quietly drift from the algebra.

**[monocular-vo](https://github.com/raahimnawaz/monocular-vo)** · *Python / PyTorch / OpenCV*
Monocular visual odometry with **metric-scale** trajectory recovery from a single calibrated webcam, using [Depth Anything v2](https://huggingface.co/depth-anything/Depth-Anything-V2-Metric-Indoor-Small-hf) depth + ORB matches + PnP-RANSAC — bypassing the scale-ambiguity wall that classical essential-matrix VO hits. **12.96 % scale error** on a tape-measured 5 m hallway walk; a pose-graph back-end with loop closure cuts ATE by **36 %** on TUM RGB-D.

**[vision_demos](https://github.com/raahimnawaz/vision_demos)** · *Python / OpenCV / MLX*
Realtime CV on Apple Silicon, building to a closed perception → decision → actuation loop. `gesture_bot` takes webcam gestures through a debounced state machine (confidence gate, stability requirement, dead-man timeout) to `(v, ω)` — the same pair as `geometry_msgs/Twist` — behind pluggable sim / Arduino / HID backends.

#### Aerospace & process control

**[aerospace-surrogate](https://github.com/raahimnawaz/aerospace-surrogate)** · *Python / Rust*
ML surrogates for airfoil aerodynamics, benchmarked against the 100-year-old thin-airfoil baseline — which **wins in the linear regime** and only collapses (R² = −1.77) through stall, where the surrogate holds R² = 0.77. A nonlinear lifting-line solver lifts 2D polars to 3D finite wings, reproducing the elliptic-wing identity to machine precision. The Rust port runs **9.8× faster** than Python and agrees to 1e-10 across 28 parity tests.

**[synfuel-control](https://github.com/raahimnawaz/synfuel-control)** · *Python / C++ / ESP32*
End-to-end sense → model → control → deploy for a thermal-runaway-prone Fischer–Tropsch reactor. Sobol analysis identifies pressure as the dominant runaway driver; a PINN surrogate (R² ≈ 0.996) drives an RTO + PI controller that holds **296 °C** through a cooling failure that otherwise runs away to 328 °C. Deployed as a dependency-free C++ engine at **0.98 µs/inference** — 4.8× faster than the ONNX Runtime Python path — closed in software-in-the-loop through a modeled analog front-end and an ESP32 node.

#### Also

**[flux](https://raahimnawaz.github.io/flux/)** — interactive 2D/3D visualizations of the math I keep reaching for: Jacobians & manipulability ellipsoids, Kalman filtering, SE(3) screw motion, Fourier, optimization, eigenvectors. Vanilla JS, no build step.
**[wildfire](https://github.com/raahimnawaz/wildfire)** — operational two-stage US West Coast fire prediction: XGBoost ignition (ROC-AUC 0.785, evaluated fully out-of-time) + U-Net spread matching the Google Research NDWS benchmark. [Live dashboard.](https://raahimnawaz.github.io/wildfire/)
**[neutrino-ml](https://github.com/raahimnawaz/neutrino-ml)** — ML on real ATLAS Open Data (13 TeV W→ℓν): RDataFrame selection and neutrino-p_z reconstruction, recovering the W mass at 80.38 GeV.
**[quantview](https://github.com/raahimnawaz/quantview)** — Bloomberg-style quant terminal in the shell. Black-Scholes Greeks, CRR/trinomial lattices, Monte Carlo (GBM + Heston), Markowitz. Pure NumPy/SciPy math layer cross-checked against QuantLib.

---

#### Tools

Python · C++ · Rust · PyTorch · NumPy / SciPy · Kalman filtering · numerical optimization · physics-informed ML · embedded & edge deployment · CMake · GitHub Actions
