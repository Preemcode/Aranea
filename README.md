1. Title:
QUADROPOD: HYBRID WHEELED-QUADRUPED SURVEILLANCE, SEARCH & RESCUE BOT

2. Problem Statement:
“FIRST RESPONDERS LACK VERSATILE, LOW-COST SCOUTING ROBOTICS CAPABLE OF BOTH RAPID, ENERGY-EFFICIENT TRAVERSAL OVER FLAT TERRAIN AND COMPLEX OBSTACLE NAVIGATION WITHIN STRUCTURALLY UNSTABLE DISASTER ZONES.”

3. Solution Proposed:
Quadropod is a hybrid quadrupedal robot with four 3-DOF legs, each ending in an actively driven wheel. This dual-locomotion design lets it act as a high-speed rover on flat ground and as a climbing quadruped over rubble.
The CAD model below shows the complete design.
 
Hexagonal chassis plates  ·   Hip servo joint  ·  Articulated leg linkage  ·   Wheel (Ø44 mm)  ·   N20 gear motor (wheel drive)

Mechanism	Components
Locomotion:	Tank drive (skid steering) via N20 gear motors for wheeled transit; MG90S servos for leg articulation and active suspension.
Core Compute:	ESP32 microcontroller handling inverse kinematics, motor PWM routing and primary logic.
Sensory Payload:	ESP32-CAM for live visual scouting and an MLX90640 thermal sensor array for detecting body heat in low-visibility environments.
Communication	Tri-modal link: Wi-Fi streaming, LoRa/Reticulum sub-GHz mesh for deep penetration, and a physical tether option.


Mechanical layout. A hexagonal two-plate chassis carries four identical leg modules. Each module has a servo-driven hip joint, an articulated linkage and a wheel driven by an N20 gear motor at the hub. In the modelled pose the robot measures about 380 × 303 × 107 mm (Figure 2), and the leg module is shown in Figure 3.


4. Implementation Plan
Development runs in iterative phases so that reliability is proven before real-world use.
•	Target beneficiaries: disaster management agencies (e.g. NDRF), fire departments and urban search and rescue (USAR) teams.
•	Phase 1 (Prototyping): chassis fabrication, integrating N20 motors and MG90S servos, and basic tank-drive control through a web server.
•	Phase 2 (Payload Integration): mounting the ESP32-CAM and thermal sensor, and balancing payload weight across the chassis.
•	Phase 3 (Testing & Deployment): field tests in simulated rubble. Deliverables: a working prototype, open-source control software and a performance report.
•	Expected outcomes: shorter time to locate victims, lower risk to human responders, and longer uptime thanks to energy-efficient locomotion.


5. Safety and Efficiency Analysis
Efficiency: Walking gaits keep servos under continuous load, which drains batteries quickly. It rolls on N20 gear motors in a skid-steer layout for most of its travel, and its MG90S servos hold a rigid, low-centre-of-gravity stance during transit. This saves battery for the sensor payload.
Safety and material handling: Scouting unstable areas ahead of human teams reduces risk to first responders. The sturdy chassis and efficient wheeled mode also let the robot carry small essentials such as medical supplies, two-way radios or structural markers to trapped victims.

6. Scalability and Future Development
•	Hybrid automatic/manual communication toggle: the system falls back from high-bandwidth Wi-Fi to the low-bandwidth Reticulum mesh as signal degrades, while the operator keeps a physical override.
•	Higher-torque actuators and multiple units: several robots working as a local mesh swarm to map large disaster zones at once.
•	Six-legged design: for better balance and faster, more efficient movement.

7. Innovation Advantage
Current solutions are either wheeled rovers, which get stuck on debris, or pure quadrupeds, which are slow, mechanically complex and expensive. Quadropod bridges this gap. It uses accessible, low-cost components to deliver hybrid mobility with a strong cost-to-capability ratio compared with enterprise rescue robots.

8. Visual Impact & User Journey
The storyboard below shows how Phido changes the emergency response workflow.

Traditional search & rescue
•	Blind entry: rescuers enter structurally compromised buildings without prior interior knowledge.
•	High risk: human operators face secondary collapses and hazardous gases.
•	Slow search: searching in smoke or darkness relies entirely on flashlights.	Quadropod
•	Rapid scouting: robot rolls quickly over flat approaches, then climbs over structural debris.
•	Thermal mapping: ESP32-CAM and MLX90640 stream heat signatures to operators outside.
•	Targeted rescue: rescuers enter with a known path directly to survivors, minimising exposure time.

Quadropod
•	Rapid scouting: robot rolls quickly over flat approaches, then climbs over structural debris.
•	Thermal mapping: ESP32-CAM and MLX90640 stream heat signatures to operators outside.
•	Targeted rescue: rescuers enter with a known path directly to survivors, minimising exposure time.
