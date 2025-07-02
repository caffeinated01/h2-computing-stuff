under algorithmic representation, but I separated it for easy reference
# Identifiers
A name for a variable, constant, function, or procedure
- **Rules:** Can contain letters, digits, and underscores (`_`). Must not begin with a digit. Cannot be a keyword
- **Examples:** `studentName`, `total_score` (Valid); `2fast`, `email@address` (Invalid)

# Data Types

| Data Type | Definition                                           | Example Literals    |
| :-------- | :--------------------------------------------------- | :------------------ |
| `INTEGER` | A whole number                                       | `-33`, `0`, `100`   |
| `REAL`    | A number with a fractional part                      | `-24.8`, `3.142`    |
| `CHAR`    | A single character, delimited by single quotes       | `'A'`, `'#'`, `'7'` |
| `STRING`  | A sequence of characters, delimited by double quotes | `"Hello World"`     |
| `BOOLEAN` | A logical value                                      | `TRUE`, `FALSE`     |

# Variables and Constants
- **Variable:** A named storage location that can hold a value which may change during program execution
  - `DECLARE age : INTEGER`
- **Constant:** A named value that does not change during program execution
  - `CONSTANT pi = 3.14159`

# Assignments and Operators
- **Assignment:** The `←` operator assigns a value to a variable
  - e.g. `is_black ← TRUE`
- **Operators:**
  - **Arithmetic:** `+`, `-`, `*`, `/`, `MOD`, `DIV` (floor divide)
  - **Relational:** `>`, `<`, `>=`, `<=`, `=`, `<>` (not equal)
  - **Logical:** `AND`, `OR`, `NOT`

# Arrays
A static data structure with a fixed size and elements of the same type.

### 1D Array Declaration
```pseudocode
// Using lower and upper bounds (1-based index)
DECLARE <identifier>: ARRAY[<lower>:<upper>] OF <TYPE>

// Using size directly
DECLARE <identifier>: ARRAY[<size>] OF <TYPE>
```

### 2D Array Declaration
```
DECLARE <identifier>: ARRAY[<lower1>:<upper1>, <lower2>, <upper2>] OF <TYPE>
```

Assigning values to array:
```arr[<idx>] <- value```

Assigning a group of elements into an array
```
DECLARE SpellingTest: ARRAY[1:30] of INTEGER 
FOR index = 1 TO 30 
	SpellingTest[index] <- -1 
ENDFOR
```
# Sequence
Instructions are executed one after another in the order they are written
## Functions
Available functions (not exhaustive)
- `LENGTH()`
- `INT()`, `STRING()`
Syntax:
```pseudocode
FUNCTION <identifier>(param: <TYPE>) RETURNS <RET_TYPE>
	// Statements to execute
ENDFUNCTION
```

## Procedure
Syntax:
```pseudocode
PROCEDURE <identifier>(param: <TYPE>)
	// Statements to execute
ENDPROCEDURE

CALL identifier(param)
```

> [!note] Key Difference
> - **Function:** Returns a **single value** to the calling code. It is called as part of an expression
> - **Procedure:** **Does not** return a value. It performs an action or a series of actions. It is called as a standalone statement
# Selection
Chooses between two or more paths of execution based on a condition
```pseudocode
IF <condition> THEN
    // Statements to execute if true
ELSE
    // Statements to execute if false
ENDIF
```

# Iteration

- **`FOR` Loop (Count-Controlled):** Used when the number of iterations is known beforehand
  ```pseudocode
  FOR index ← 1 TO 10 STEP 1
      // Statements to repeat
  ENDFOR
  ```
- **`WHILE` Loop (Pre-test):** The condition is checked *before* each iteration. The loop may not execute at all if the condition is initially false
  ```pseudocode
  WHILE <condition is true>
      // Statements to repeat
  ENDWHILE
  ```
- **`REPEAT-UNTIL` Loop (Post-test):** The condition is checked *after* each iteration. The loop body will always execute at least once
  ```pseudocode
  REPEAT
      // Statements to repeat
  UNTIL <condition is true>
  ```
