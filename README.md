### Hi, I'm Raahim

Robotics engineer. I build systems from first-principles physics and modern ML, and I like them to run on real hardware.

My usual approach: derive the physics, learn what it can't explain, benchmark it honestly against the classical method, then port it to something that runs in a control loop. Where the model loses is often the most interesting part, so I publish that too.

**Now building:** [wildfire-vtol](https://github.com/raahimnawaz/wildfire-vtol), a simulated drone fleet that maps wildfires and feeds a field fire forecast, and an F1 simulator built on my vehicle-dynamics work.

📫 [LinkedIn](https://www.linkedin.com/in/raahim-nawaz-9ab64220b/)

---

#### Main projects

**[workbench-copilot](https://github.com/raahimnawaz/workbench-copilot)** · *Python · LeRobot · SO-101 arm*
A voice-controlled lab assistant with a robot arm, built for the Meta Global AI Developer Hackathon 2026. A desk camera finds the tool you name and the arm picks it up; a command only runs when a local Llama model and a rule-based parser agree, giving **0 wrong moves** on 117 new phrasings.

**[wildfire-vtol](https://github.com/raahimnawaz/wildfire-vtol)** · *C++ · embedded*
The flight core for a simulated wildfire-mapping fleet: a tiltrotor mothership and four tailsitter drones. Today it is quaternion attitude control on a chip with no floating-point unit, with the control loop sped up from **23 Hz to 179 Hz**.

**[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** · *Python · C++ · PyTorch*
Five estimators, from a Kalman filter to physics-informed neural networks, compared on the same braking data to show which wins when. The C++ port runs a filter step in **7 ns** with no dependencies.

#### Robotics

- **[singularity-robust-control](https://github.com/raahimnawaz/singularity-robust-control)**: keeps a robot arm controllable through a singularity. The naive controller asks the joints for **2,434 rad/s**; the damped one, 2.8.
- **[vision_demos](https://github.com/raahimnawaz/vision_demos)**: hand gestures drive a robot base, as a Python loop and as a ROS 2 node graph, and it stops when it loses sight of you.
- **[monocular-vo](https://github.com/raahimnawaz/monocular-vo)**: tracks a camera's path in real metres from a single webcam, within **13 %** on a measured 5 m walk.

#### Simulation & ML

- **[apex-forecast](https://github.com/raahimnawaz/apex-forecast)** · [live](https://raahimnawaz.github.io/apex-forecast/): Bayesian F1 race forecasts for 2026. **93 %** of the finishing order comes down to the car.
- **[engine-map-pinn](https://github.com/raahimnawaz/engine-map-pinn)**: from a dyno curve to a lap time on real circuits. Doubling the power gains only **5–6 %**; a better racing line saves **53 s** at the Nürburgring.
- **[aerospace-surrogate](https://github.com/raahimnawaz/aerospace-surrogate)**: ML models of wing aerodynamics that hold up through stall, where the classic theory fails. The Rust port is **9.8×** faster.
- **[wildfire](https://github.com/raahimnawaz/wildfire)** · [live](https://raahimnawaz.github.io/wildfire/): predicts where West Coast fires will start and spread, from satellite data.

#### Also

[flux](https://raahimnawaz.github.io/flux/) (interactive visualizations of the math behind robotics) · [neutrino-ml](https://github.com/raahimnawaz/neutrino-ml) (finding neutrinos in real ATLAS collision data) · [quantview](https://github.com/raahimnawaz/quantview) (a Bloomberg-style finance terminal in the shell)

---

Python · C++ · PyTorch · NumPy / SciPy · ROS 2 · OpenCV · sensor fusion · physics-informed ML · embedded & edge deployment · KiCad
