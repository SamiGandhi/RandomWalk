# 🚶‍♀️ OOP 2D Bounded Random Walker

## 🎯 Objective
[cite_start]This project, developed for the Object-Oriented Programming (OOP) course[cite: 2], implements a 2D Random Walker simulation. The core objective is to demonstrate the enforcement of **grid boundary constraints** through object methods.

## ✨ Implementation Details

### Grid Constraints
- The simulation uses a $10 \times 10$ grid ($W=10, H=10$)[cite: 9]. Any point $(x, y)$ must strictly satisfy the boundary conditions:
- $$0 \le x \le 9 \quad \text{and} \quad 0 \le y \le 9 \text{ [cite: 10]}$$

### ⚙️ Boundary Clamping Logic
- The `Point.move()` method is updated to implement clamping logic, which mathematically ensures the new position is within the valid range $[0, W-1]$[cite: 17].

- The operation for finding the final coordinate ($x^{\prime}$) from the intended new coordinate ($x_{new}$) is[cite: 19, 20]:
$$x^{\prime} = \min(W-1, \max(0, x_{new}))$$

- This clamping is achieved by checking three conditions on the intended position[cite: 22, 23, 24, 25]:
1.  If $x_{new} < 0$, set $x^{\prime} = 0$ (Too low/Left boundary)[cite: 23].
2. If $x_{new} \ge W$, set $x^{\prime} = W-1$ (Too high/Right boundary)[cite: 24].
3. Otherwise, set $x^{\prime} = x_{new}$ (Valid move)[cite: 25].

### 🛠 Required Code Changes Summary
- **Update Point Class:** The `move` method must accept the grid dimensions (`max_x`, `max_y`) and apply the boundary clamping logic[cite: 27].
- **Update Main Loop:** Calls to the `move` method must pass the grid dimensions, e.g., `p1.move(G1.width, G1.height)`[cite: 28].
