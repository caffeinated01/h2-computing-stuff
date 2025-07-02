# 1. Programming Standards
A set of guidelines to ensure code is well-structured, maintainable, and readable
- **Comments**: clear explanations for complex algorithms
- **Meaningful Identifiers**: Use descriptive names for variables and functions and avoid single-letter names except for common loop counters like `i`
- **Indentation and White Space**: Use consistent formatting to show the structure of loops and conditional statements
- **Avoid Deep Nesting**: Excessively nested loops and `if` statements make code hard to read and can increase execution time

---

# 2. Trace Table
A technique to manually simulate the execution of an algorithm to track variable values, conditions, and outputs at each step. It is used to debug code and verify its logic
-   **Structure**: A table where columns represent variables, conditions, or outputs
-   **Purpose**: To find logical errors by observing how the state of the program changes over time

**Example Trace Table for a Loop:**
```
num ← 0
total ← 0
FOR i ← 1 TO 3
	FOR j ← 1 TO 3
		num ← j * i
		total ← total + num
	ENDFOR
ENDFOR
OUTPUT total
```

|  i  |  j  | num | total | OUTPUT |
| :-: | :-: | :-: | :---: | :----: |
|     |     |  0  |   0   |        |
|  1  |  1  |  1  |   1   |        |
|     |  2  |  2  |   3   |        |
|  2  |  1  |  2  |   8   |        |
|     | ... | ... |  ...  |        |
|     |     |     |       |   36   |

---

# 3. Data Verification vs. Data Validation

## Data Verification
Confirms that data has been transferred accurately from source to destination without alteration. It does not check if the data itself is correct
-   **Purpose**: To detect errors during data entry or transfer.

**Transcription Error**: A mistake made when copying data (e.g., OCR detecting `l` instead of `1`)

**Transposition Error**: Swapping two adjacent characters (e.g., typing `13245` instead of `12345`)

**Verification techniques**:


| Technique    | Description                                                                      | Example                                                                                     |
| ------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------- |
| Double Entry | Entering the data twice and comparing the two entries to ensure consistency      | Re-entering password during account registration                                            |
| Visual Check | Having a person review the data entered to compare it with the original document | After entering data, user checks and confirms that everything looks right before proceeding |

## Data Validation
An automated process to check if input data is sensible, reasonable, and meets predefined rules
-   **Purpose**: To ensure data is acceptable before it is processed

**Validation Checks:**

| Check Type         | Description                                                             | Example                                                       |
| :----------------- | :---------------------------------------------------------------------- | :------------------------------------------------------------ |
| **Range Check**    | Ensures a number is within a specific range                             | Age must be between 18 and 65                                 |
| **Format Check**   | Ensures data follows a specific pattern                                 | A flight number must start with 'EK' followed by three digits |
| **Length Check**   | Ensures data has the correct number of characters                       | A postal code must be exactly 6 digits                        |
| **Presence Check** | Ensures a required field is not left empty                              | The 'Name' field cannot be blank                              |
| **Type Check**     | Ensures data is of the correct data type                                | An input for 'Quantity' must be numeric                       |
| **Check Digit**    | An extra digit calculated from the other digits, used for self-checking | The last character of an ISBN or NRIC                         |

### Mod-11 Arithmetic
- Is a type of check digit
- Steps
	1. Starting from the units column, assign weights to each digit. **Weights start from 2**. Assign weights **from the back**	
	2.  Multiply each digit to its weight `∑ (digit * weight) = sum`
	3. Take that sum and MOD it by 11 `sum MOD 11 = remainder`
	4. Subtract the remainder off 11 `11-remainder = check digit`, and that is the check digit. If the check digit is 10, replace it with `X` instead


| Units         |     1      |  2  |  3  |  4  |
| ------------- | :--------: | :-: | :-: | :-: |
| Weights       |     5      |  4  |  3  |  2  |
| Unit * Weight |     5      |  8  |  9  |  8  |
| Sum           | 5+8+9+8=30 |  -  |  -  |  -  |
| Remainder     |  30%11=8   |     |     |     |
| 11-Remainder  |   11-8=3   |     |     |     |
| Check digit   |     3      |     |     |     |


---

# 4. Program Testing

## Syntax Errors
- Happens when the code violates the rules of the programming language (e.g., `pint` instead of `print`, missing quotes, mismatched parentheses)
- Detected by the compiler or interpreter *before* the program is run
- The program fails to compile or run

## Runtime Errors
- Happens *during* the execution of the program. The syntax is correct, but an operation is impossible to perform
- e.g. Zero division, trying to access an array index that doesn't exist (`Index Out of Bounds`), or running out of memory (`Stack Overflow` from infinite recursion)
- The program crashes or terminates unexpectedly

| Type of runtime error   | Description                                                                      | Examples                                                                                                |
| :---------------------- | :------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| **Input Error**         | Occurs when the program receives incorrect data from the user                    | User entering a text when a number is expected, or enters a date in an incorrect format                 |
| **Index Out of Bounds** | Happens when trying to access an invalid element in an array                     | Trying to access the 6th element in an array with only 5 items                                          |
| **Undeclared Variable** | Occurs when trying to use a variable that has not been declared                  | Trying to use a variable x without declaring it first                                                   |
| **Arithmetic Error**    | Happens during incorrect arithmetic operations                                   | Dividing by zero, or attempting to store a number larger than a variable can hold                       |
| **Out of Memory**       | Occurs when the program uses more memory than is available                       | Trying to create a large array that exceeds the computer's available memory                             |
| **Stack Overflow**      | Occurs when there is excessive nesting or recursion. The call stack its max size | Recursively calling a function without a base case, causing the program to crash                        |
| **Infinite Loop**       | Occurs when a loop never ends due to a missing exit condition                    | A while loop that never reaches its exit condition, freezing the program                                |
| **Memory Leak**         | Happens when memory is allocated but not properly released                       | Allocating memory in a program but never freeing it, causing a gradual decrease in available memory     |
| **Type Mismatch Error** | Occurs when a variable is used with an incompatible type in an operation         | Trying to add a string and an integer, or passing the wrong data type to a function                     |
| **File I/O Error**      | Happens when there are issues with file operations                               | Trying to read a file that doesn't exist or attempting to write to a read-only file                     |
| **Overflow**            | Occurs when a value exceeds the maximum limit of a data type                     | Trying to store a number larger than the variable can hold, such as 256 in an 8-bit unsigned integer    |
| **Underflow**           | Happens when a value goes below the minimum limit of a data type                 | Subtracting 1 from 0 in an unsigned integer, causing it to wrap around to the maximum value (e.g., 255) |

## Logic Errors
- A logic error is a mistake made in the design of a program, such as using an inappropriate mathematical formula or control structure
- The program gives the wrong output but the program still runs
- Fix by observation and running test cases

## Designing Test Cases
- **Normal Data**: Sensible, expected, and should be accepted and processed by the system.
- **Abnormal Data**: Abnormal data (also known as invalid or erroneous test data) falls outside of what is acceptable and should be rejected by the system
- **Extreme Data**: Extreme data is at the upper or lower limits of expectations that should be accepted by the system. Or where special handling of the input data is required (e.g. use of -1 as NULL value)
- **Boundary Data**: Boundary data can be extreme data and also includes the immediate values before or beyond the limits of expectations that should be rejected

| Input (test cases) | Purpose (test for ...) | Expected output |
| :--- | :--- | :--- |
| 10, 25, 65, 88 | Normal data | Accepted |
| -1, 101, 200, -55 | Abnormal data | Rejected |
| 0, 100 | Extreme (or Boundary) data | Accepted |
| -1, 101 | Boundary data | Rejected |

---

# 5. Recursion
A process where a function calls itself as part of its definition. Each recursive function has two key components: **1. a stopping condition (or base case)** and a **2. recursive call**. The stopping condition prevents infinite recursion by ensuring that the function eventually stops calling itself and begins to “unwind”
## Recursion vs. Iteration

| Feature                  | Recursion                                                                                                           | Iteration (Loops)                                                                                                                                   |
| :----------------------- | :------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Simplicity**           | More elegant for problems that naturally break into smaller subproblems (e.g., tree traversal)                      | Can be more complex for problems that involve recursive patterns                                                                                    |
| **Memory Usage**         | Can use a large amount of memory due to call stack growth, especially for deep recursion                            | Fixed memory usage; does not use extra memory for function calls                                                                                    |
| **Execution Speed**      | May be slower due to overhead from function calls and maintaining the call stack                                    | Generally faster as it avoids the overhead of recursive function calls                                                                              |
| **Risk of Errors**       | Risk of stack overflow if base case is missing or if recursion depth is too large                                   | No risk of stack overflow; risks are usually related to incorrect loop conditions or logic errors                                                   |
| **Ease of Debugging**    | More challenging to trace due to repeated function calls and deeper call stack                                      | Easier to debug since it involves straightforward loop constructs                                                                                   |
| **Proof of Correctness** | Easier to prove mathematically using induction, especially when the problem follows a recursive structure           | Harder to prove, but still possible with loop invariants or inductive reasoning                                                                     |
| **Code Size**            | Typically shorter and more elegant, especially for naturally recursive problems                                     | May require more lines of code, especially for problems that can be described recursively                                                           |
| **Use Cases**            | Best for problems that can be divided into smaller, similar subproblems (e.g., factorial, Fibonacci, binary search) | Suitable for repetitive tasks that don't require breaking down problems into smaller subproblems (e.g., summing numbers in a list, printing values) |
| **Time Complexity**      | May be less efficient due to overhead from multiple function calls                                                  | Generally more time-efficient for simple problems as there's no overhead from function calls                                                        |

## Trace Tree Diagram
```pseudocode
FUNCTION Fac(N: INTEGER) RETURNS INTEGER
	IF N = 1 THEN
		RETURN 1
	ELSE
		RETURN N * Fac(N-1)
	ENDIF
ENDFUNCTION
```
![[tracetreediagram.png]]
## Call Stack
A system data structure that manages active function calls.
- When a function is called, a **stack frame** containing its local variables, parameters, and return address is **pushed** onto the stack.
- When the function finishes, its frame is **popped** off the stack, and control returns to the saved address.
- In recursion, many frames are pushed onto the stack, one for each call. The "unwinding" process begins when the base case is hit and frames start popping off.

e.g. of call stack:

| Call Stack Contents                         |
| ------------------------------------------- |
| top of stack                                |
| **--- Stack Frame for function call 2 ---** |
| Return address of function call 2           |
| Parameters for function call 2              |
| Local variables for function call 2         |
| **--- Stack Frame for function call 1 ---** |
| Return address of function call 1           |
| Parameters for function call 1              |
| Local variables for function call 1         |
| ..............................              |
| **(rest of the stack)**                     |
