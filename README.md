### Hi, I'm Raahim

Robotics engineer working at the intersection of first-principles physics, numerical methods, and modern ML. I like building systems that are both mathematically rigorous and deployable on real hardware.

---

#### Recent projects

**[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** &nbsp;·&nbsp; *Python / C++ / PyTorch*
Physics-informed parameter estimation for vehicle braking dynamics. Compares batch optimization, EKF, MLP, and two PINNs on the same data, with an honest model-mismatch study. Ships an allocation-free C++ edge port delivering a **3,400× EKF speedup** over the Python reference — 62 KB binary, zero external deps, Jetson-targeted.

**[quantview](https://github.com/raahimnawaz/quantview)** &nbsp;·&nbsp; *Python / Textual*
Bloomberg-style quantitative analysis terminal (TUI). Black-Scholes Greeks with live IV solver, Cox-Ross-Rubinstein binomial and Boyle trinomial lattices, Monte Carlo pricing (GBM + Heston with antithetic + control variates), and Markowitz mean-variance optimization. Pure NumPy/SciPy math layer cross-checked against QuantLib.

**[function-classifier-cnn](https://github.com/raahimnawaz/function-classifier-cnn)** &nbsp;·&nbsp; *PyTorch*
Multi-task CNN (ResNet + Squeeze-and-Excitation) that classifies rendered plots of mathematical functions into 16 families and detects 9 structural properties (periodicity, monotonicity, symmetry, saddle points, …). Trained end-to-end on an effectively infinite synthetic dataset with an auxiliary self-supervised reconstruction head.

---

#### Tools

Python &nbsp;·&nbsp; C++ &nbsp;·&nbsp; PyTorch &nbsp;·&nbsp; NumPy / SciPy &nbsp;·&nbsp; embedded systems &nbsp;·&nbsp; Kalman filtering &nbsp;·&nbsp; numerical optimization
