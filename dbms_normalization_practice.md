MAKAUT DBMS — NORMALIZATION PRACTICE SET
[PYQ-clone questions — same style, different schemas]
[Answers not included — solve yourself, then cross-check with guide]

================================================================
QUESTION 1 (BCNF decomposition + lossless check) — 10 marks
================================================================

Consider relation R(A, B, C, D, E) with functional dependencies:
  F = { A → B, BC → D, D → E, E → A }

(a) Find all candidate keys of R.
(b) Check whether R is in BCNF. Justify.
(c) If not in BCNF, decompose R into BCNF step-by-step.
(d) Show that your decomposition is lossless.

================================================================
QUESTION 2 (3NF decomposition + dependency preservation) — 10 marks
================================================================

Relation R(P, Q, R, S, T) with FDs:
  F = { P → Q, Q → R, R → S, S → T }

(a) Find a candidate key.
(b) Decompose R into 3NF using the canonical cover method.
(c) Is the decomposition dependency preserving? Justify.

================================================================
QUESTION 3 (Normal form check — mixed bag) — 8 marks
================================================================

(a) Relation R(X, Y, Z, W) with FDs: X → Y, Y → Z, W → X.
    Find the highest normal form (1NF/2NF/3NF/BCNF) satisfied by R.
    Justify each step.

(b) For a relation with FDs: AB → C, C → B, B → A.
    Is it in 4NF? Justify. DeptId DeptId

================================================================
QUESTION 4 (Lossless vs lossy — the trap) — 7 marks
================================================================

Given R(A, B, C, D) and F = { A → B, B → C, C → D }.

Consider decomposition: R1(A, B, C) and R2(C, D).

(a) Check whether this decomposition is lossless.
(b) Check whether it preserves all dependencies.
(c) If lossy, show a counterexample where original relation and decomposed join give different results.

================================================================
QUESTION 5 (Anomalies + need for normalization) — 7 marks
================================================================

Consider an unnormalized relation:
  Employee(EmpId, Name, DeptId, DeptName, ProjectId, ProjectName, Hours)

Where one employee can work on multiple projects, and each department has multiple employees.

FDs:
  EmpId → Name, DeptId, DeptName
  DeptId → DeptName
  ProjectId → ProjectName
  (EmpId, ProjectId) → Hours

(a) Identify the anomalies (insertion, deletion, update) present in this relation.
(b) Normalize this relation to 3NF step-by-step.
(c) For each step, state which normal form violation you are removing.

================================================================
QUESTION 6 (Armstrong's axioms + closure proof) — 7 marks
================================================================

Given F = { A → B, B → C, AC → D }.

Using Armstrong's axioms:
(a) Prove that A → C.
(b) Find closure of AC (i.e., (AC)+).
(c) Is A a candidate key? Why or why not?

================================================================
QUESTION 7 (BCNF vs 3NF tradeoff — exam loves this) — 8 marks
================================================================

Relation R(Customer, Course, Instructor, Semester) with FDs:
  Customer → Course
  Course → Instructor
  Instructor → Course

(a) Find candidate keys.
(b) Decompose into BCNF.
(c) Decompose into 3NF (preserving dependencies).
(d) Compare the two decompositions: which one is better for query performance? Which one preserves all FDs?

================================================================
QUESTION 8 (Design case study — integrated) — 10 marks
================================================================

A university maintains a database with the following information:
- Each instructor teaches exactly one course.
- A course may have multiple instructors (team teaching).
- Each student enrolls in exactly one course.
- A course has many students.
- Each course has a unique course coordinator (an instructor).

Attributes:
  Instructor(Id, Name, CourseId)
  Student(Roll, Name, CourseId)
  Course(CourseId, CourseName, CoordinatorId)

(a) Draw an ER diagram for this scenario.
(b) Convert the ER diagram into relational schema with proper keys and foreign keys.
(c) List all functional dependencies in the resulting relation(s) after conversion.
(d) Normalize each resulting relation to BCNF. Show each step.
