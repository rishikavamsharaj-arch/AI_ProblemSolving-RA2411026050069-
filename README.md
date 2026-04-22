# AI_ProblemSolving_<RA2411026050058>

Team Members: 1. [vamsharaj Rishika / RA2411026050069]
2. [Sree Lakshmi / RA2411026050058]

Interactive Website Link: [streamlit run "smart emergency response and decision support system.py"]

---

## Repository Folder Structure
Ensure your GitHub repository is structured like this before submitting:
```text
AI_ProblemSolving_<YourRegisterNumber>/
│
├── README.md
├── Problem1_SmartCityEmergency/
│   ├── app.py                  # The Streamlit code
│   └── requirements.txt        # Contains: streamlit, numpy, scikit-learn
│
└── Problem2_SmartNavigation/
    └── navigation.py           # The BFS/DFS terminal code

## Problem 1: Smart City Emergency Decision System
Problem Description
A comprehensive emergency management system designed for a smart city. The system processes incoming emergency data (injury type, location risk, time delay) and autonomously predicts the severity of the incident. Based on the severity and current city resources, it determines the priority level, allocates the most suitable medical or police unit, calculates the optimal route avoiding traffic/roadblocks, and generates a step-by-step extraction plan.

Algorithms Used
Machine Learning (Random Forest Classification): Trains a lightweight model on dummy emergency data to predict the incident's severity (Low, Medium, High).

Rule-Based System: Determines the final dispatch priority (e.g., Code Red, Standard Response) based on the predicted severity and the total available city units.

Constraint Satisfaction Problem (CSP): Allocates the first available rescue unit (Basic Life Support, Advanced Life Support, or Helicopter) that meets the priority constraints.

A (A-Star) Graph Search:* Finds the most optimal path on a 5x5 grid from the responder's location to the emergency, actively avoiding coordinates marked as roadblocks.

Means-Ends Analysis: Generates a sequential action plan to transition the state from "Emergency Detected" to "Mission Complete."

Execution Steps
Navigate to the Problem1_SmartCityEmergency folder.

Install the required dependencies:

Bash

pip install streamlit numpy scikit-learn
Run the Streamlit application:

Bash

streamlit run app.py
Open the provided localhost link in your web browser. Use the sidebar to input emergency parameters and click "Process Emergency".

Sample Output
Predicted Severity (ML Model): High

Priority Level (Rule-Based): Critical (Code Red)

Assigned Rescue Unit (CSP): Unit 4 (Rescue Helicopter)

Optimal Route (A Search):* [(0, 0), (1, 0), (2, 0), (3, 1), (4, 2), (4, 3), (4, 4)]

Step-by-Step Action Plan:

Step 1: Emergency Detected by City Sensors

Step 2: Pre-emptively clear traffic lights on target route.

Step 3: Dispatch Advanced Life Support / Aerial Support.

Step 4: Immediate extraction and trauma care.

Step 5: Transport victim to nearest available hospital.

Step 6: Mission Complete. Resource back to standby.

## Problem 2: Smart Navigation System
Problem Description
A localized pathfinding program that simulates routing through city waypoints (Start, A, B, C, D, E, F, Goal). It compares two fundamental AI search strategies to determine viable routes from a starting location to a destination, demonstrating the difference between shortest-path mapping and randomized exploration.

Algorithms Used
Breadth-First Search (BFS): Explores the map level by level. This algorithm guarantees finding one of the shortest paths (in terms of the number of nodes/hops) from the start to the goal.

Depth-First Search (DFS): Explores as far as possible along each branch before backtracking. Nodes are shuffled dynamically, resulting in random valid paths that may not be the shortest but successfully reach the goal.

Execution Steps
Navigate to the Problem2_SmartNavigation folder.

Ensure you have standard Python installed (no external libraries required).

Run the Python script:

Bash

python navigation.py
Sample Output
Plaintext

=== Randomized Navigation System ===

Breadth-First Search (BFS) Route:
Start -> F -> Goal

Depth-First Search (DFS) Route:
Start -> B -> C -> A -> D -> Goal
