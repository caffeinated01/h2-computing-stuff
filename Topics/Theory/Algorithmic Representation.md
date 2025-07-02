## 1. Algorithm

An **algorithm** is a well-ordered, unambiguous, and effectively computable sequence of steps designed to perform a particular task
- It must produce an **observable result**
- It must **halt** in a finite amount of time after a finite number of operations
- It can be represented in forms like pseudo-code, flowcharts, or a programming language

---
## 2. Flowchart

| Symbol              | Name             | Description                                                                                                          |
| :------------------ | :--------------- | :------------------------------------------------------------------------------------------------------------------- |
| ![[terminator.png]] | **Terminator**   | Indicates the `Start` and `Stop` points of the algorithm                                                             |
| ![[io.png]]         | **Input/Output** | Represents data being read (`READ`, `INPUT`) or displayed (`PRINT`, `OUTPUT`)                                        |
| ![[process.png]]    | **Process**      | Represents any operation, calculation, or assignment (e.g., `count = count + 1`)                                     |
| ![[decision.png]]   | **Decision**     | A branch point where a decision is made. Has one entry point and at least two exit points (e.g., Yes/No, True/False) |
| ![[connector.png]]  | **Connector**    | Connects separate parts of a flowchart on the same page                                                              |
| ![[subroutine.png]] | **Subroutine**   | Represents a call to a separate, named process or module (e.g., a function or procedure)                             |

--- 
## 3. Modular Design

Breaking down a large program into smaller, self-contained, manageable modules (subroutines)

**Advantages:**
- **Teamwork:** Multiple programmers can work on different modules simultaneously
- **Simplicity:** Easier to write, test, and debug smaller pieces of code
- **Reusability:** Modules can be reused in other programs

---
## 4. Decision Table

A table used to model complex logic by mapping all possible combinations of conditions to corresponding actions

### Basic Format
A decision table is divided into four quadrants:
1.  **Conditions:** The logical conditions to be tested
2.  **Actions:** The possible actions to be taken
3.  **Condition Entries:** The combinations of condition outcomes (`Y`/`N`, `-` for insignificant). 
4.  **Action Entries:** The actions to perform for each rule (`X` to mark the action, `*` for no such outcome)
- Easiest way to fill up decision table (conditions):
	1. Last Row: Start with the easiest pattern: Y N Y N ...
	2. Row Above: Double the block size: Y Y N N ...
	3. Row Above That: Double again: Y Y Y Y N N N N ...
	4. Continue until the top row is filled.

$2^n$ scenarios, where $n$ is the number of conditions

### Decision Table Example (Tutorial Q7)

**Problem:** A furniture company's delivery charges
- Purchase ≥ $2000 AND distance < 20km -> Free delivery
- Purchase ≥ $2000 AND distance ≥ 20km -> Charge 5%
- Purchase < $2000 AND distance < 20km -> Charge 5%
- Purchase < $2000 AND distance ≥ 20km -> Charge 10%

**Decision Table Solution:**

| CONDITIONS                   |  1  |  2  |  3  |  4  |
| :--------------------------- | :-: | :-: | :-: | :-: |
| Purchase price ≥ $2000?      |  Y  |  Y  |  N  |  N  |
| Delivery distance < 20km?    |  Y  |  N  |  Y  |  N  |
| **ACTIONS**                  |     |     |     |     |
| Customer gets free delivery  |  X  |     |     |     |
| Charge customer 5% of price  |     |  X  |  X  |     |
| Charge customer 10% of price |     |     |     |  X  |

### Removing Redundancies
Simplify the table by merging rules that lead to the same action if one or more conditions are irrelevant. An irrelevant condition is marked with a dash (`-`)

**Example: Simplified table for Tutorial Q10(b) (Library Overdue Books)**

| Condition                            |  1  |  2  |  3  |  4  |
| :----------------------------------- | :-: | :-: | :-: | :-: |
| Book overdue by more than 5 days?    |  Y  |  Y  |  Y  |  N  |
| Student has had a previous warning?  |  Y  |  N  |  N  |  -  |
| More than 4 books overdue?           |  -  |  Y  |  N  |  -  |
| **Action**                           |     |     |     |     |
| Send student reminder letter         |     |     |     |  X  |
| Send student warning letter          |  X  |  X  |     |     |
| Send parent's copy of warning letter |  X  |     |     |     |
