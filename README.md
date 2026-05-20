### Hi, I'm Raahim

Robotics engineer working at the intersection of first-principles physics, numerical methods, and modern ML. I like building systems that are both mathematically rigorous and deployable on real hardware.

📫 [LinkedIn](https://www.linkedin.com/in/raahim-nawaz-9ab64220b/)

---

#### Recent projects

**[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** &nbsp;·&nbsp; *Python / C++ / PyTorch*
Physics-informed parameter estimation for vehicle braking dynamics. Compares batch optimization, EKF, MLP, and two PINNs on the same data, with an honest model-mismatch study. Ships an allocation-free C++ edge port delivering a **3,400× EKF speedup** over the Python reference — 62 KB binary, zero external deps, Jetson-targeted.

**[monocular-vo](https://github.com/raahimnawaz/monocular-vo)** &nbsp;·&nbsp; *Python / PyTorch / OpenCV*
Monocular visual odometry with **metric-scale trajectory recovery** from a single calibrated webcam. Uses [Depth Anything v2](https://huggingface.co/depth-anything/Depth-Anything-V2-Metric-Indoor-Small-hf) per-frame depth + ORB matches + PnP-RANSAC to estimate camera motion in real-world units — bypassing the scale-ambiguity wall that classical essential-matrix monocular VO hits. **12.96 % scale error** on a tape-measured 5 m hallway walk; 1161 median inliers per frame; 227 ms depth inference on M5 MPS.

**[aerospace-surrogate](https://github.com/raahimnawaz/aerospace-surrogate)** &nbsp;·&nbsp; *Python / Rust*
ML surrogates for 2D airfoil aerodynamics benchmarked honestly against the 100-year-old thin-airfoil baseline (gradient boosting wins through stall, where the classical formula collapses to R² = −1.77). A nonlinear lifting-line solver lifts 2D sectional polars to 3D finite-wing predictions, with a faithful **Rust port that runs 9.8× faster than Python** and agrees to 1e-10 on every wing tested.

**[wildfire](https://github.com/raahimnawaz/wildfire)** &nbsp;·&nbsp; *Python / PyTorch / XGBoost*
Operational two-stage US West Coast wildfire prediction. XGBoost ignition model (**ROC-AUC 0.78** on 2025 holdout) over 2.4M live Google Earth Engine cells, plus a U-Net spread model that matches the Google Research *Next Day Wildfire Spread* benchmark. [Live interactive dashboard.](https://raahimnawaz.github.io/wildfire/)

**[quantview](https://github.com/raahimnawaz/quantview)** &nbsp;·&nbsp; *Python / Textual*
Bloomberg-style quantitative analysis terminal (TUI). Black-Scholes Greeks with live IV solver, Cox-Ross-Rubinstein binomial and Boyle trinomial lattices, Monte Carlo pricing (GBM + Heston with antithetic + control variates), and Markowitz mean-variance optimization. Pure NumPy/SciPy math layer cross-checked against QuantLib.

**[function-classifier-cnn](https://github.com/raahimnawaz/function-classifier-cnn)** &nbsp;·&nbsp; *PyTorch*
Multi-task CNN (ResNet + Squeeze-and-Excitation) that classifies rendered plots of mathematical functions into 16 families and detects 9 structural properties (periodicity, monotonicity, symmetry, saddle points, …). Trained end-to-end on an effectively infinite synthetic dataset with an auxiliary self-supervised reconstruction head.

---

#### Tools

Python &nbsp;·&nbsp; C++ &nbsp;·&nbsp; Rust &nbsp;·&nbsp; PyTorch &nbsp;·&nbsp; NumPy / SciPy &nbsp;·&nbsp; XGBoost &nbsp;·&nbsp; Google Earth Engine &nbsp;·&nbsp; embedded systems &nbsp;·&nbsp; Kalman filtering &nbsp;·&nbsp; numerical optimization
