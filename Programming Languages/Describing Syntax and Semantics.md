## Program Syntax
- Program **syntax** refers to the rules and structure of a programming language
- **How programs must be written** so they are considered **well-formed**
- It defines things like **correct keywords**, **punctuation**, and the **arrangement of symbols** (grammar)
- Syntax answers the **question**: "Is the program written correctly?"

## Program Semantics
- Program semantics **refers to the meaning and behavior of a** **program.**
- This error occurs **when the statements** written in the program are not **meaningful to the compiler**.
- Semantics answers the **question**: “What does the program do?” code does)

### In short:
**Syntax** = *form* (how code is written)
**Semantics** = *meaning* (what the code does)

## Recovering from Syntax Errors
- Compilers **must continue** parsing after a syntax **error**.
- **Goals:** Detect **additional real errors**.
- Avoid cascading (spurious) errors.
- Minimize loss of useful input.
- Example Syntax Error:
	- A = B : C + D;
	- Error detected after B
	- Compiler cannot stop; must recover and continue analysis

## Searching for Further Syntax Errors: Techniques
### Panic-Mode Recovery
- Simplest error recovery technique.
- Defines a fixed set of safe symbols (e.g., ;, end).
- On error:
	- Delete input tokens until a safe symbol is found.
	- Back parser to a valid context.
- Pros:
	- Easy to implement
	- Guarantees progress
- Cons:
	- Deletes large chunks of input
	- Often causes cascading errors
	- Poor for structured languages

#### Panic-Mode Recovery Example
	IF a b THEN x
	ELSE y;
	END;  
- The equal sign is missing
- Skipping to; misses THEN
- Leads to errors at ELSE and END

### Phrase-Level Recovery
- Improves panic mode by using **context-specific safe symbols**.
- Recovery depends on where the error occurs.

#### Phrase-Level Recovery Example:
	int a,b
	// AFTER RECOVERY:
	int a,b; // Semicolon is added by the compiler
- Benefits:
	- More local recovery
	- Fewer cascading errors
	- Allows checking remaining parts of a statement


## Exercise
| Program                                                                | Syntax Error                      | Semantic Error                                       |
| ---------------------------------------------------------------------- | --------------------------------- | ---------------------------------------------------- |
| C++ <br> int main () <br> { <br> int x = 10 return 0; <br> }           | Yes - Missing semicolon after 10  | No - Meaning is clear; error is purely syntactic     |
| 2. Python <br> if x > 5 <br> print(x)                                  | Yes - Missing a colon             | No - Logic is fine, grammar is invalid               |
| 3. C++ <br> int a = "hello"                                            | No - Syntax is correct            | Yes - Type mismatch: string assigned to int          |
| 4. Python <br> x = 10 / 0                                              | No - Valid Syntax                 | Yes - deviidion by zero at runtime                   |
| 5. C++ <br> string x,z; <br> cout << y;                                | No - Syntax is correct            | Yes - Variable is not declared                       |
| 6. Python <br> for i in range (5) <br> print(i)                        | Yes missing colon after ranges    | No - Intended meaning is valid                       |
| 7. C++ <br>int add(int a, int b){ <br> return a + b; } <br> int main() | No - Syntax is correct            | Yes - Function called with wrong number of arguments |
| 8. Python <br> print("Hello"                                           | Yes - Missing closing parenthesis | No - Intended output is clear                        |
| 9. C++                                                                 | No - Syntax is correct            | Yes - Using unitialized variable                     |
| 10. Python <br> x = "5" + 2                                            | No - Syntax is valid              | Yes - Type error: cannot add string and integer      |

