# Boids++ Simulation System
[Korean](https://github.com/OperaAIBot/BoidsSimulation/blob/main/README-KR.md)

![2025-07-12 19 26 44 mp4 (2)](https://github.com/user-attachments/assets/a4db2a4a-6bc2-48b1-9e51-73b88f627cc2)

*A spatial hash-based flocking simulation that implements classic Boids behavior along with predator-prey interactions and obstacle avoidance, complete with performance optimization and interactive controls.*  

---

<details>
<summary>Table of Contents</summary>

1. Introduction  
2. Key Features  
3. Quick Start  
4. Controls & CLI Options  
5. Project Structure  
6. AI Generation Process  
7. Customisation Guide  
8. Performance Metrics  
9. Appendix A – AI Prompt Templates  

</details>

---

## 1. Introduction <a id="introduction"></a>

**Boids++ Simulation** is a Python implementation that:

* simulates flocking behavior using the classic Boids algorithm (separation, alignment, cohesion)
* optimizes collision detection using spatial hash grid techniques
* implements multiple agent types including standard Boids, predators, obstacles, and leaders
* provides real-time visualization using Pygame
* includes automatic testing and performance measurement features

The simulation demonstrates emergent behavior patterns and efficient spatial partitioning techniques, making it ideal for teaching AI concepts, optimization strategies, and interactive visualization.

---

## 2. Key Features <a id="key-features"></a>

- **Spatial Hash Grid System**
  - Optimized collision detection and neighbor finding
  - Up to 80% reduction in collision checks
  
- **Multiple Agent Types**
  - Standard Boids - exhibit classic flocking behavior
  - Predators - hunt and chase Boids
  - Obstacles - static objects to be avoided
  - Leaders - special Boids that influence group movement
  
- **Advanced Flocking Algorithms**
  - Separation, alignment, cohesion
  - Obstacle avoidance
  - Boundary handling
  - Predator evasion
  
- **Interactive Controls**
  - Real-time parameter adjustment
  - Visualization mode switching
  - Simulation speed control
  
- **Performance Optimization**
  - Maintains 60 FPS with 200+ agents
  - Supports up to 10x speed multipliers
  - Efficient data structures and algorithms

---

## 3. Quick Start <a id="quick-start"></a>

```bash
# 1 – Install dependencies
pip install pygame numpy

# 2 – Clone repository
git clone https://github.com/OperaAIBot/BoidsSimulation.git
cd BoidsSimulation

# 3 – Run the simulation
python boids_simulation.py
```

---

## 4. Controls & CLI Options <a id="controls--cli-options"></a>

| Key / Option        | Effect |
| ------------------- | ------ |
| **ESC**             | Quit simulation |
| **SPACE**           | Pause/resume simulation |
| **G**               | Toggle grid visualization |
| **V**               | Change visualization mode |
| **+/-**             | Increase/decrease simulation speed |
| **H**               | Toggle help display |
| `--auto-test`       | Run automated 30-second test |

---

## 5. Project Structure <a id="project-structure"></a>

```text
BoidsSimulation/
 ├─ boids_simulation.py     # Main simulation code
 ├─ config.json             # Configuration parameters
 ├─ AIInputText/            # AI input specification
 │   ├─ Common.txt          # Common development guidelines
 │   └─ Simulation/         # Simulation-specific requirements
 │       └─ Simulation.txt  # Boids simulation specifications
 └─ Simulation/             # AI automation scripts
     └─ simulation.py       # Automation controller
```

---

## 6. AI Generation Process <a id="ai-generation-process"></a>

The program was produced through an AI-driven development process:

1. Requirements specified in Simulation.txt
2. Development guidelines defined in Common.txt
3. AI automation controller (simulation.py) generates and refines code
4. Iterative testing and optimization to meet performance targets
5. Final code produced in boids_simulation.py with configuration in config.json

---

## 7. Customisation Guide <a id="customisation-guide"></a>

| What to tweak      | Location | Notes |
| ------------------ | -------- | ----- |
| Agent counts       | config.json | "boidCount", "predatorCount", etc. |
| Speed & forces     | config.json | "maxSpeed", "maxForce" |
| Grid cell size     | config.json | "gridCellSize" (affects performance) |
| Visualization      | config.json | "visualizeGrid" to show/hide grid |
| Speed multiplier   | config.json | "speedMultiplier" for simulation speed |

To create custom scenarios, modify the configuration file or extend the agent classes in the code.

---

## 8. Performance Metrics <a id="performance-metrics"></a>

The simulation is optimized to meet the following performance targets:

- **60+ FPS** with 200+ agents at normal speed
- Support for **up to 10x** speed multipliers for accelerated testing
- **80%+ reduction** in collision checks through spatial hashing
- **30-second automated test** feature for validation

Performance metrics are displayed in real-time during simulation, including FPS, agent counts, and collision efficiency statistics.

---

## 9. Appendix A – AI Prompt Templates <a id="appendix-a--ai-prompt-templates"></a>

> The agent (`simulation.py`) uses a library of reusable message templates to interact with the OpenAI API. Below are the **raw prompt texts** used in the autonomous development process.

### A.1 Project Analysis **System** Prompt

```text
You are an expert Python developer specializing in simulation systems.
Analyze the current project state and suggest the next development step.

CRITICAL RULES:
- Focus on spatial hash grid and flocking algorithms
- Prioritize performance optimization for 200+ agents
- Suggest specific, actionable improvements
- Consider the 30-second automated testing requirement
```

### A.2 Partial-Fix **System** Prompt

```text
You are an expert Python developer.
Fix the specific error in the provided code with minimal changes.

CRITICAL RULES:
- Provide ONLY the corrected Python code
- Use a single ```python code block
- No explanations outside the code block
- Fix only what's necessary to resolve the error
- Maintain the performance requirements for spatial hash grid operations
```

### A.3 Partial-Fix **User** Prompt Template

```text
PROJECT GOAL: Implement a spatial hash-based Boids++ simulation system using Pygame

Fix ONLY the specific error in the Python code for '{filename}'.
Do NOT rewrite the entire code. Only modify the minimal parts necessary.

ERROR TO FIX:
{error_message}

{error_line_info}

CURRENT CODE:
```python
{code}
```

INSTRUCTIONS:
You must respond with ONLY the corrected code in a single code block.
Fix only what is necessary to resolve the error.
Do not include explanations or any other text.

Provide the complete corrected code:
```

### A.4 Full-Rewrite **System** Prompt

```text
You are an expert Python developer specializing in simulation and optimization.
Rewrite the provided code to achieve a high-performance Boids simulation.

REQUIREMENTS:
- Provide complete, working Python code
- Use a single ```python code block
- No explanations outside the code block
- Optimize for 60+ FPS with 200+ agents

CRITICAL PERFORMANCE REQUIREMENTS:
- Implement efficient spatial hash grid for collision detection
- Optimize neighbor search algorithms
- Use vectorized operations where possible
- Implement all core flocking behaviors: separation, alignment, cohesion
- Include predator-prey interactions and obstacle avoidance
```

### A.5 Full-Rewrite **User** Prompt Template

```text
PROJECT GOAL: Implement a spatial hash-based Boids++ simulation system using Pygame

Rewrite the Python code for '{filename}' to resolve all errors and optimize performance.

The simulation has the following error:
----------------
{error_message}
----------------

Current code:
```python
{code}
```

Configuration reference:
{config_reference}

Provide ONLY the complete optimized Python code in a single code block. No explanations.
```

### A.6 New-Code **System** Prompt

```text
You are an expert Python developer specializing in simulation and visualization.
Create a complete Boids simulation system with spatial hash optimization.

REQUIREMENTS:
- Provide complete Python code in ```python code blocks
- No explanations outside the code block
- Follow the project requirements exactly
- Include automatic testing capability with '--auto-test'
- Implement all agent types: Boids, Predators, Obstacles, Leaders
- Ensure 60+ FPS with 200+ agents
```

### A.7 New-Code **User** Prompt Template

```text
PROJECT GOAL: Implement a spatial hash-based Boids++ simulation system using Pygame

Create complete Python code from scratch to implement a high-performance Boids simulation.

SPECIFIC REQUIREMENTS:
1) Spatial hash grid system for efficient collision detection
2) Multiple agent types (Boids, Predators, Obstacles, Leaders)
3) Flocking algorithms (separation, alignment, cohesion)
4) Performance optimization for 60+ FPS with 200+ agents
5) 30-second automated testing mode

Configuration reference:
{config_reference}

Provide ONLY the complete Python code in a code block, no explanations.
```

### A.8 Performance Optimization **System** Prompt

```text
You are an expert in Python performance optimization.
Optimize the provided Boids simulation code to achieve maximum frame rate.

REQUIREMENTS:
- Provide ONLY the optimized Python code
- Focus on spatial hash grid efficiency
- Improve neighbor search algorithms
- Use vectorized operations with numpy
- Consider all possible optimizations without compromising functionality
```

### A.9 Testing Mode **System** Prompt

```text
You are an expert in automated testing for simulation systems.
Enhance the provided code with a comprehensive 30-second test mode.

REQUIREMENTS:
- Provide ONLY the complete Python code
- Implement automated testing that completes in exactly 30 seconds
- Validate all key features: flocking, obstacle avoidance, predator-prey
- Generate performance metrics and scoring
- Ensure the test results are clearly reported
```

### A.10 Advanced Features **System** Prompt

```text
You are an expert in AI behavioral systems and simulation.
Enhance the provided Boids simulation with advanced behavioral features.

REQUIREMENTS:
- Provide ONLY the complete Python code
- Add group splitting/merging behaviors
- Implement environmental factors that affect movement
- Create more sophisticated predator strategies
- Ensure all additions maintain the 60+ FPS performance target
```
