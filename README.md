### Hi, I'm Raahim

Robotics engineer. I build systems from first-principles physics and modern ML, and I like them to run on real hardware.

My usual approach: derive the physics, learn what it can't explain, benchmark it honestly against the classical method, then port it to something that runs in a control loop. Where the model loses is often the most interesting part, so I publish that too.

Most of my work falls into three lines, each building on earlier projects.

📫 [LinkedIn](https://www.linkedin.com/in/raahim-nawaz-9ab64220b/)

---

#### Robot arm

**[workbench-copilot](https://github.com/raahimnawaz/workbench-copilot)** · *Python · LeRobot · SO-101 arm*
A voice-controlled lab assistant with a robot arm, built for the Meta Global AI Developer Hackathon 2026. A desk camera finds the tool you name and the arm picks it up; a command only runs when a local Llama model and a rule-based parser agree, giving **0 wrong moves** on 117 new phrasings.

Grew out of:
- **[singularity-robust-control](https://github.com/raahimnawaz/singularity-robust-control)**: the damped-least-squares control the arm's IK uses, studied on its own. Through a singularity the naive controller asks for **2,434 rad/s**; the damped one, 2.8.
- **[vision_demos](https://github.com/raahimnawaz/vision_demos)**: the same perception → decision → action loop, with hand gestures driving a robot base in Python and ROS 2.

#### Wildfire drone

**[wildfire-vtol](https://github.com/raahimnawaz/wildfire-vtol)** · *C++ · embedded*
The flight core for a simulated wildfire-mapping fleet: a tiltrotor mothership and four tailsitter drones. Today it is quaternion attitude control on a chip with no floating-point unit, with the control loop sped up from **23 Hz to 179 Hz**.

Will build on:
- **[aerospace-surrogate](https://github.com/raahimnawaz/aerospace-surrogate)**: the wing model. ML aerodynamics that hold up through stall, where the classic theory fails.
- **[wildfire](https://github.com/raahimnawaz/wildfire)** · [live](https://raahimnawaz.github.io/wildfire/): the fire forecast. Predicts where West Coast fires will start and spread, from satellite data.

#### Motorsport

**[parc-ferme](https://github.com/raahimnawaz/parc-ferme)** · [live](https://raahimnawaz.github.io/parc-ferme/) · *Python · Numba*
Post-session engineering debriefs for 2026 F1, worked out from public timing data by physics models checked against what the cars actually did. A digital 2026 car laps in **0.3 ms**, and a test bench with known answers recovers each team's mechanical grip to **0.3 %**.

Builds on:
- **[engine-map-pinn](https://github.com/raahimnawaz/engine-map-pinn)**: the track model and lap simulator, ported and extended for 2026. A better racing line saves **53 s** at the Nürburgring; doubling the power gains only **5–6 %**.
- **[vehicle-dynamics-estimation](https://github.com/raahimnawaz/vehicle-dynamics-estimation)** *(planned: tyres and brakes)*: five estimators, from a Kalman filter to physics-informed neural networks, compared on the same braking data. The C++ port runs a filter step in **7 ns**.
- **[apex-forecast](https://github.com/raahimnawaz/apex-forecast)** · [live](https://raahimnawaz.github.io/apex-forecast/) *(planned: race strategy)*: Bayesian F1 race forecasts for 2026. **93 %** of the finishing order comes down to the car.

#### Also

- **[monocular-vo](https://github.com/raahimnawaz/monocular-vo)**: tracks a camera's path in real metres from a single webcam, within **13 %** on a measured 5 m walk.
- [flux](https://raahimnawaz.github.io/flux/) (interactive visualizations of the math behind robotics) · [neutrino-ml](https://github.com/raahimnawaz/neutrino-ml) (finding neutrinos in real ATLAS collision data) · [quantview](https://github.com/raahimnawaz/quantview) (a Bloomberg-style finance terminal in the shell)

---

Python · C++ · PyTorch · NumPy / SciPy · ROS 2 · OpenCV · sensor fusion · physics-informed ML · embedded & edge deployment · KiCad
