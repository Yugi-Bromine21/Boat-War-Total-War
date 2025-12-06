# Naval Command: Tactical Boat Simulator

A physics-based naval combat survival game built entirely in a single HTML5 file using the Canvas API. No external game engines or libraries were used.

## 🎮 Overview

**Naval Command** is a top-down arcade shooter that simulates hydrodynamic physics. Players control a destroyer, leading a fleet of AI allies against endless waves of enemy ships. The game features vector-based drift mechanics, procedural terrain generation, and scaling difficulty modes.

## ✨ Key Features

### Physics & Core Engine
* **Hydrodynamic Drift:** Custom physics engine using vector decomposition. Ships "slide" on water (high lateral friction vs. low forward friction).
* **Vector Math Library:** Manual implementation of `Vec2` for addition, subtraction, scaling, dot products, and normalization.
* **Collision System:** Circle-to-circle collision detection with bounce resolution (reflection vectors) and energy loss.

### Combat & AI
* **Fleet System:** AI Allies fight alongside the player.
* **Targeting Logic:** Enemies and Allies dynamically scan for the closest valid target.
* **Ballistics:** Projectiles inherit ship velocity (inertia) and apply recoil force to the firing vessel.
* **Elimination:** Ships are permanently removed from the battlefield upon reaching 0 HP.

### Game Loop & Progression
* **Wave System:** Enemies increase in number every wave.
* **Reinforcements:** Surviving allies are repaired and destroyed allies are replaced at the start of a new wave.
* **Difficulty Modes:**
    * **Easy:** High ally count (+3 per wave).
    * **Medium:** Balanced (+2 per wave).
    * **Extreme:** 1 Ally only. Enemies scale aggressively (+5 per wave).
* **Persistence:** High Score is saved to Local Storage.

### Visuals
* **Procedural Rocks:** Obstacles generated using "Sum of Sines" noise (radial harmonic noise) to create organic, jagged shapes.
* **Particle Systems:**
    * **Wake:** Decaying opacity trails that visualize speed and drift.
    * **Explosions:** Debris particles with velocity and fade-out.
* **HUD:** Real-time telemetry, hull integrity, score, and wave tracking.

## 🕹️ Controls

| Key | Action |
| :--- | :--- |
| **W / Up** | Throttle Forward |
| **S / Down** | Reverse / Brake |
| **A / Left** | Rudder Port (Left) |
| **D / Right** | Rudder Starboard (Right) |
| **SPACE** | Fire Main Gun |
| **R** | Restart (On Game Over) |

## 🚀 How to Run

Since the game is a standalone HTML file, it requires no compilation.

### Option 1: Direct Open
Simply double-click `boat_war_extreme.html` to open it in your default web browser (Brave, Chrome, Firefox).

### Option 2: Terminal / Python Server (Recommended)
If you are developing or testing on other devices on your network:

1. Open your terminal.
2. Navigate to the directory containing the file.
3. Run a local server:
   ```bash
   python3 -m http.server 8000
