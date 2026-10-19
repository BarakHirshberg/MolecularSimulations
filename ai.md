# How the course works

**Policy.** AI is allowed in the projects and exercises, without disclosure. It is not allowed in the oral exams or the final defense.

**Responsibility.** You are responsible for everything you submit, including errors made by an AI. An AI can produce solutions to every task in this course on its own; your job is to learn honestly. The oral exams and the defense test what you understand.

**Grading.**

| Component | Weight |
| --- | --- |
| Oral exam 1 (Project 1), in class | 25% |
| Oral exam 2 (Project 2), in class | 25% |
| Final defense, during the break (date coordinated with you): a talk and an oral exam on your code | 50% |

Push your work for each project to its branch (see the README in your repository). At the end of each project, the state of that branch at the deadline is checked automatically. These checks are not graded; you get feedback on what to fix.

**How an oral exam works.** You open your own repository, and I ask three questions: explain a part of your code that I choose, and why you wrote it that way; read a different version of that part and explain what it does, how it differs from yours, and what would happen if you used it; and a question on the theory behind your code or on one of the figures in your notebook. Each answer is scored 0–3: 3 for a correct answer with the right reason, 2 if the reason is incomplete, 1 for a correct answer without a reason, 0 otherwise. The talk at the defense is scored the same way, one score per guiding question of the final project.

**Example** (Project 1). You open `evalHarm`. (1) "What do these lines do, and why?" A good answer: it sets $U = \frac{1}{2} m \omega^2 x^2$ and $F = -m \omega^2 x$; the force is minus the gradient of the potential, which velocity Verlet needs at every step. (2) You are shown this version of the same lines:

```python
self.U = 0.5 * np.sum(m * omega**2 * self.R**2)
self.F = m * omega**2 * self.R
```

"What does it do, how does it differ from yours, and what would happen if you used it?" A good answer: the potential is the same but the force has the wrong sign, so it points away from the minimum; the atom accelerates outward instead of oscillating, and the energy is not conserved. (3) "Why do we use periodic boundary conditions for the argon simulation?" A good answer: to simulate bulk argon with a few hundred atoms. Without them most atoms would sit at a surface; with them an atom near the box edge interacts with the images of the atoms on the other side, so there is no surface. The price is an artificial periodicity, so the box must be large compared with the range of the interactions. Or, instead of a theory question: "Open Figure 3 of Part A, the potential and kinetic energies against time. Explain what you see." A good answer: they oscillate out of phase, each at twice the frequency of the motion, with the kinetic energy largest when the atom passes the minimum; their sum is constant, which is the energy conservation of the NVE run.

**Course structure.** The dates are on Moodle.

| Class | In class | Due before this class |
| --- | --- | --- |
| 1 | Course introduction; classical mechanics | |
| 2 | Statistical mechanics fundamentals | |
| 3 | Molecular dynamics; GitHub fundamentals and Project 1 instructions | |
| 4 | Project 1 in class (Part A) | |
| 5 | Project 1 in class (Part B) | |
| 6 | Oral exam 1 | Project 1 |
| 7 | Monte Carlo I | |
| 8 | Monte Carlo II; Project 2 instructions | |
| 9 | Project 2 in class (Parts A and B) | |
| 10 | Project 2 in class (Part C) | |
| 11 | Oral exam 2 | Project 2 |
| 12 | The final project explained | |
| Break | Final project; final defense | |
