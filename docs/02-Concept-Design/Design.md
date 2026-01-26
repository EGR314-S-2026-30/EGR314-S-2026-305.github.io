---
title: Concept Generation and Design Ideation
---

## Background Reading and Design Constraints

Before we started brainstorming, we looked through the EGR 314 project description and read up on interactive exhibit design. The main takeaways were that the device needs to hold up under repeated use, be safe for everyone, and be intuitive enough that users can figure it out without needing instructions. Good exhibits also give immediate feedback and make sure important features are easy to find.

The brainstorming guides we read said to hold off on judging ideas too early. They encouraged us to think outside the box and come up with as many ideas as possible before we start narrowing things down. That's what we did when we put together our list of around 100 ideas.

## Goal of the Exploration Device

We want to build something that gives users a real taste of remote scientific exploration. Picture a mobile rover with a robotic arm that can collect samples, similar to the Mars rovers but sized for a lab or demo setting. Users can drive it around, control the arm, and watch sensor data come in live.

The goal is hands-on learning. Instead of just hearing about how rovers work, people get to actually run one. They deal with the same challenges engineers face, like working with limited feedback and making decisions without being right next to the machine. We want users to experiment, observe the results, and pick up knowledge along the way.

## Intended Audience

Our primary audience is experts in the robotics field and scientists at NASA who may use this as a demonstration tool or proof of concept for educational outreach. The device is meant to showcase core rover functionality in a compact, accessible format that can be used in professional presentations, lab demos, or public engagement events hosted by technical organizations.

Secondary audiences include engineering students and researchers who want to study rover mechanics and control systems up close. Because this is aimed at a technically knowledgeable crowd, we focused on making the system modular and well documented so it can be adapted or built upon for future projects.

## Generating Ideas

Here's the raw brainstorm we came up with. About 100 ideas total. We didn't cut anything at this stage, just wrote everything down.

**Mobility and Navigation**  
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

**Robotic Arm and Sampling**  
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

**Sensors and Actuators**  
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

**Human-Machine Interface**  
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

**User Cues and Instruction**  
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

**Durability, Safety, and Comfort**  
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

**Engagement and Motivation**  
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

**Avoiding Common Interactive Pitfalls**  
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

**Unconventional and Exploratory Ideas**  
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

**Infrastructure and Connectivity**  
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

Once we had all our ideas down, we sorted them into categories and ranked them based on how realistic they were for our project.

![Sorted and Grouped Ideas](brainstorm_grouped.png)

### Group 1: User Interaction and Controls
**Top picks:**
- Large directional buttons  
- Joystick-controlled arm  
- Touchscreen display  
- Emergency stop  

These ranked highest because they are simple to use and hard to mess up.

![Ranked Features](brainstorm_ranked.png)

### Group 2: Sensors and Feedback
**Top picks:**
- Arm-mounted camera  
- Distance sensing  
- LED status indicators  
- Real-time data display  

Getting instant feedback matters a lot because it helps users connect their actions to what the rover does.

### Group 3: Durability and Safety
**Top picks:**
- Enclosed mechanisms  
- Force-limited actuators  
- Rounded edges  
- Impact bumpers  

Even though our audience is professionals, we still need the rover to be tough enough to survive transport and demos without breaking.

### Group 4: Engagement and Learning
**Top picks:**
- Mission-based challenges  
- Real-world rover context  
- Visual progress indicators  

These features help keep the demo interesting while also showing off what the rover can do.

### Product Concept Combinations

We narrowed things down to three possible directions:

**Concept A: Mission Rover**  
A structured experience where the user follows guided missions with clear goals and feedback cues.

**Concept B: Open Exploration Rover**  
A freeform setup where users can just drive around and experiment without any set objectives.

**Concept C: Collaborative Science Rover**  
A system designed for multiple users to work together on navigation and data interpretation.

## Product Concept Descriptions and Evaluation

**Concept A: Mission Rover**  
This concept gives users short missions to complete. Things like driving to a specific spot, picking up a sample, or checking a sensor reading. Visual and audio cues walk you through each step so you always know what to do next. We built this around avoiding the common problems we read about, like having too many controls active at once or hiding features that users actually need.

### How We Would Split Up the Work
- **Wireless communication:** Data transmission, logging, and reporting system status  
- **User interface:** Touchscreen, buttons, visual cues, and feedback systems  
- **Sensors and actuators:** Motors, robotic arm, sensors, and response logic  
- **Integration and safety:** Power management, fault detection, and durability testing  

### Why This Design Works
- **Cues:** LED animations, on-screen arrows, sounds, and progress bars help guide users without overwhelming them  
- **Controls:** Big buttons and a joystick make operation straightforward  
- **Durability:** Enclosed parts and current-limited motors keep everything safe  
- **Instructions:** A quick mission briefing and looping tutorial mean no one has to explain it in person  

**Concept B: Open Exploration Rover**  
This one is all about freedom. No set goals, just exploration. It is flexible but we were worried that users might get confused without any guidance.

**Concept C: Collaborative Science Rover**  
This version focuses on teamwork with multiple people controlling different parts. Cool idea but adds a lot of complexity to the interface.

## Selected Concept: Mission Rover

## Why We Picked It

After comparing all three on usability, educational value, durability, safety, and how well they fit exhibit design guidelines, the Mission Rover won out. It hits the sweet spot between engagement and simplicity. We did take a few ideas from the other concepts but the mission-based structure gave us the strongest foundation to work from.

![Annotated Mission Rover Concept](mission_rover_concept.png)

*This diagram highlights the main components including the mobility system, robotic arm, sensors, control interface, and display.*

## Final Selected Concept Summary
- Clear cues across multiple channels like visuals and audio  
- Simple controls that are easy to pick up  
- Built tough and safe for repeated use  
- Minimal instructions needed because the design guides the user naturally  
