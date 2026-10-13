## Constraint Satisfaction Problems (CSP) in AI

- A Constraint Satisfaction Problem is a mathematical problem where the objective is to assign values to variables such that all the constraints are satisfied. Many AI applications use CSPs to solve decision-making problems. Common applications of CSPs include:

- Scheduling: It assigns resources like employees or equipment while respecting time and availability constraints.
  <img width="780" height="440" alt="image" src="https://github.com/user-attachments/assets/2e26a134-4156-4062-992c-bb843b57354e" />

- Planning: Organize tasks with specific deadlines or sequences.
  <img width="1000" height="500" alt="image" src="https://github.com/user-attachments/assets/4151515d-3e90-4898-b2c2-f0428b7bfec3" />

- Resource Allocation: Distributing resources efficiently without overuse

# Example
  Team Assignment Problem
1. Variables (The 3 People)
We have three people to assign to teams:

Alex
Bob
Hi

2. Domains (The Choices)
Each person can be assigned to one of two teams:
Team 1
Team 2

4. Constraints (The Rules)
Alex and Bob are enemies: They cannot be on the same team.
Constraint: Alex != Bob
Constraint: Hi != Bob

The Stranger has no enemies: There are no restrictions on which team the Stranger can join.

6. Solution (A Valid Assignment)

Since there are only two teams, we can assign the people as follows:

Person	Assigned Team
Alex	Team 1
Bob	Team 2
hi	Team 1
Why Does This Work?
Alex is assigned to Team 1.
Bob is assigned to Team 2, keeping Alex and Bob on separate teams.
The hi can join either team because there are no constraints on their assignment.
5. Conclusion

This is a valid solution because all constraints are satisfied. The Stranger can be assigned to either Team 1 without violating any rules.
