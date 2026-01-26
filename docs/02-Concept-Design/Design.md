---
title: Concept Generation and Design Ideation
---

## Background Reading and Design Constraints

From our research, we found that a good exploration device needs to be realistic but still easy to understand and operate. Operators should always know what the rover is doing and how their actions can affect it. Good feedback on both visual and auditory helps make the system intuitive, considering operators can’t directly touch the rover or see everything it’s sensing. We also learned that durability and safety are really important. The rover has to handle repeated use, bumps, and mistakes without breaking. Its vital moving parts should be protected, motors should be limited to safe forces, and the controls should default to safe states if something goes wrong. These are very similar to the real challenges engineers face with planetary rovers. research showed that too many controls or hidden functions can confuse operators. Keeping interactions simple, continous, and supported with clear indicators makes it easier to understand the cause and effect to complete tasks successfully. Generating a lot of ideas before deciding what to include also helped us explore creative ways to meet these needs. 

## Goal of the Exploration Device

The goal of this exploration device is to simulate a realistic planetary robotic exploration rover equipped with a robotic sampling arm to be a representative of planetary and remote-environment missions. The rover is designed to demonstrate how engineers remotely navigate, sense, manipulate, and collect samples in environments where human presence is impossible or very difficult. The device will show system-level thinking, sensor–actuator integration, and operational decision-making under constraints. The rover is intended to showcase engineering design considerations such as mobility tradeoffs, arm kinematics, sensing limitations, communication latency, and fault handling. Users get hands-on experience with the rover, learning how its design changes its movement, sensing, and ability to complete missions.

## Intended Audience

The primary audience for this exploration device is NASA engineers, researchers, and mission operators who want to study or test rover systems in realistic scenarios. It is designed for operators who understand remote navigation, sensor feedback, and robotic manipulation, and who are interested in seeing how system design affects mission performance. A secondary audience could include aerospace engineering students and research collaborators who can use the rover as a hands-on learning tool to explore control strategies, sample collection, and system integration. The interface is designed to be clear and straightforward, providing all necessary information through visual and auditory indicators so operators can focus on testing and learning.

## Generating Ideas

This is our raw brainstorm of about 100 ideas. We didn't filter anything out at this stage, just wrote everything down.

Mobility and Navigation  

1. Tank-style tread drive  
2. Four-wheel independent steering  
3. Obstacle-climbing wheel geometry  
4. Adjustable speed modes  
5. Automatic collision avoidance  
6. Physical boundary markings  
7. LED trail visualization  
8. Compass orientation display  
9. Variable terrain difficulty zones  
10. Rover recovery mode  

Robotic Arm and Sampling  

11. Two-joint sampling arm  
12. Three-joint articulated arm  
13. Magnetic sample pickup  
14. Soft compliant gripper  
15. Sample storage bin  
16. Force-limited arm motors  
17. Arm-mounted camera  
18. Color-coded gripper tips  
19. Sample-secured feedback indicator  
20. Automatic arm homing  

Sensors and Actuators  

21. Ultrasonic distance sensors  
22. Color detection sensor  
23. Weight measurement sensor  
24. Temperature sensor  
25. Ambient light sensor  
26. Audio feedback output  
27. LED status indicators  
28. Haptic control feedback  
29. Real-time data visualization  
30. Manual sensor scan mode  

Human-Machine Interface 

31. Large directional control buttons  
32. Joystick-based arm control  
33. Touchscreen display  
34. On-screen arrows and prompts  
35. Icon-based interface design  
36. Task checklist display  
37. Start and reset buttons  
38. Physical emergency stop  
39. Multi-language support  
40. Adjustable difficulty levels  

User Cues and Instruction  

41. Attention-guiding LED animations  
42. Context-sensitive hints  
43. Animated tutorial loop  
44. Physical arrows and labels  
45. Consistent color coding  
46. Success and error sound cues  
47. Diagram-based instruction panel  
48. Mission briefing screen  
49. Countdown timer  
50. Progress bar visualization  

Durability, Safety, and Comfort  

51. Rounded structural edges  
52. Fully enclosed mechanisms  
53. Motor overcurrent protection  
54. Rubberized impact bumpers  
55. Low-speed default operation  
56. Stable weighted base  
57. Height-adjustable control panel  
58. Easy-to-clean materials  
59. Tethered operational area  
60. Child-safe construction materials  

Engagement and Motivation  

61. Mission-based challenges  
62. Timed objectives  
63. Accuracy-based scoring  
64. Cooperative multi-user mode  
65. Scientist of the Day display  
66. Randomized sample placement  
67. Achievement indicators  
68. Science fact integration  
69. Real-world rover comparisons  
70. Take-home QR code results  

Avoiding Common Interactive Pitfalls 

71. Single clear goal per task  
72. Limited simultaneous controls  
73. Immediate action feedback  
74. No hidden required features  
75. Fail-safe idle behavior  
76. Automatic reset after inactivity  
77. Clear start and end states  
78. Minimal text reliance  
79. Robust repeatable hardware  
80. Clearly defined physical boundaries  

Unconventional and Exploratory Ideas  

81. Augmented reality overlay  
82. Simulated communication delay  
83. Voice command interaction  
84. AI-guided narration  
85. Simulated environmental hazards  
86. Modular arm tools  
87. Sample contamination simulation  
88. Multi-rover interaction  
89. Competitive mission mode  
90. Night-vision camera mode  

Infrastructure and Connectivity  

91. Two-way wireless communication  
92. Cloud-based data logging  
93. Instructor control interface  
94. Remote system monitoring  
95. Software update capability  
96. Sensor calibration mode  
97. Diagnostic LED indicators  
98. Data export functionality  
99. Power-saving idle state  
100. Automatic startup self-check  

## Sorting, Ranking, and Grouping

After getting all those ideas out, we organized them into groups and ranked them based on what made the most sense for our project.

### Group 1: User Interaction and Controls
**Top Picks**  
- Large directional buttons  
- Joystick-controlled arm  
- Touchscreen display  
- Emergency stop  

These ranked highest because they are clear and accessible. Users won't get confused trying to figure out how to use them.

### Group 2: Sensors and Feedback
**Top Picks**  
- Arm-mounted camera  
- Distance sensing  
- LED status indicators  
- Real-time data display  

These give users immediate feedback so they can see how their actions affect the rover.

### Group 3: Durability and Safety
**Top Picks**  
- Enclosed mechanisms  
- Force-limited actuators  
- Rounded edges  
- Impact bumpers  

Since this will be used by the public including kids, we prioritized making it tough and safe.

### Group 4: Engagement and Learning
**Top Picks**  
- Mission-based challenges  
- Real-world rover context  
- Visual progress indicators  

These features keep people interested while also teaching them something.

### Product Concept Combinations

We came up with three different directions we could go:

**Concept A: Mission Rover**  
A structured experience with guided missions and clear goals. Strong cues tell users what to do next.

**Concept B: Open Exploration Rover**  
A sandbox style setup where users can experiment freely with minimal guidance.

**Concept C: Collaborative Science Rover**  
A cooperative system where multiple users share control and work together to interpret the data.

## Product Concept Descriptions and Evaluation

**Concept A: Mission Rover**  
This concept gives users short missions to complete. They navigate terrain, collect samples, and check sensor readings. Visual and audio cues guide them through each step so they always know what to do. We designed it to avoid common exhibit problems like having too many controls active at once or hiding features users need.  
![Concept A](concept.png)

### Functional Distribution Across Team Members
- Internet-based two-way wireless communication: Data transmission and logging and system status reporting  
- Human-machine interface: Touchscreen UI and buttons and visual cues and user feedback  
- Sensor and actuator control: Motors and robotic arm and sensors and closed-loop responses  
- System integration and safety: Power management and fault detection and durability and testing  

### Design Justification
- Cues: LED animations and on-screen arrows and audio feedback and progress indicators  
- Controls: Large buttons and joystick to make operation straightforward  
- Durability and Comfort: Enclosed mechanisms and current-limited motors and ergonomic layout  
- Instruction: Brief mission briefing and looping tutorial so no one needs to explain it  

## Concept B: Open Exploration Rover
The **Open Exploration Rover** concept prioritizes user-driven discovery by removing predefined objectives and allowing unrestricted interaction with the rover and its environment. Users are free to navigate terrain, operate sensors, and experiment with rover capabilities at their own pace. This approach encourages curiosity, creativity, and self-directed learning, but it ranked lower overall due to the increased risk of user confusion and lack of clear guidance for first-time users. Without structured goals, some users may struggle to understand the rover’s purpose or how to meaningfully engage with its systems.  
![Concept B](concept.png)

### Functional Distribution Across Team Members
- **Internet-based two-way wireless communication:** Real-time telemetry streaming, live sensor data visualization, and remote command handling  
- **Human–machine interface:** Open-ended touchscreen UI, manual control inputs, live data dashboards, and minimal instructional overlays  
- **Sensor and actuator control:** Direct control of motors, robotic arm, cameras, and environmental sensors with fewer automated constraints  
- **System integration and safety:** Power regulation, collision prevention, emergency stop logic, and robustness under unpredictable user behavior  

### Design Justification
- **Cues:** Minimal visual indicators, raw sensor readouts, and subtle status LEDs to avoid over-directing user behavior  
- **Controls:** Full-access joystick and manual controls that expose the rover’s complete functionality  
- **Durability and Comfort:** Reinforced chassis, protected actuators, and current-limited systems to tolerate exploratory misuse  
- **Instruction:** Optional on-demand help screens and tooltips replace guided tutorials, preserving a sense of freedom while offering limited support  

## Concept C: Collaborative Science Rover
The Collaborative Science Rover concept emphasizes teamwork and shared problem-solving by enabling multiple users to simultaneously control different subsystems of the rover. Each participant is responsible for a specific role, such as navigation, sensor operation, or data analysis, encouraging communication and collaboration. While this concept promotes social learning and mirrors real-world scientific workflows, it introduces additional interface and coordination complexity that can challenge users if roles and responsibilities are not clearly defined.

### Functional Distribution Across Team Members
- Internet-based two-way wireless communication: Multi-user session management, synchronized command handling, and shared data streams  
- Human–machine interface: Role-based control panels, multi-screen or multi-input support, and shared visual feedback  
- Sensor and actuator control: Partitioned control of motors, robotic arm, cameras, and sensors assigned to different users  
- System integration and safety: Command arbitration, conflict resolution, system safeguards, and fault handling across multiple operators  

### Design Justification
- Cues: Role-specific visual indicators, shared status displays, and alerts to communicate system state across users  
- Controls: Segmented controls mapped to user roles to prevent conflicting inputs  
- Durability and Comfort: Robust mechanical design and software interlocks to protect hardware from simultaneous or conflicting commands  
- Instruction: Brief role introductions and cooperative task prompts help users understand responsibilities and encourage effective teamwork  


## Selected Concept: Mission Rover

## Concept Selection Rationale

After comparing all three concepts on usability, educational value, durability, safety, and how well they fit exhibit design guidelines, the Mission Rover won out. It balances engagement with simplicity better than the others. We pulled in some ideas from the other concepts but the mission-based structure gave us the strongest foundation.

![Annotated Mission Rover Concept](mission_rover_concept.png)

*This diagram shows the main parts including the mobility system and robotic arm and sensors and control interface and display.*

## Final Selected Concept Summary
- Clear Indicators through multiple channels like visuals and audio  
- Simple controls that anyone can pick up  
- Built tough and safe for repeated use  
- Minimal instructions needed because the design guides users naturally  
