Language design and Implementation go together
- An **implementer** must **understand the language** to guarantee a **correct** implementation
- A **language designer** must understand **implementation concerns** to ensure the language can be **implemented efficiently**
- A **skilled programmer** must understand **both** in order to write correct, readable, and **efficient** programs

## Classification of Programming Languages
- Languages can be classified by their model of computation
- Two main families: **Declarative** and **Imperative**

## Declarative vs Imperative
- Declarative: focus on **what** the computer should do
- Imperative: focus on **how** the computer should do it

## Imperative Languages are Dominant
- Closer to hardware
- Better performance control
- Widely used in practice

## Design Tension in Declarative Languages
- Hide implementation details
- Still allow algorithm control
- Compilers cannot always infer optimal algorithms

## Programming Languages Sub-Families
- Within the declarative and imperative families, there are several important subfamilies:
	1. Functional Languages
		- Employ a computational model based on the **recursive definition of functions**
		- Functional programming treats programs as mathematical function that transform inputs into outputs without changing state
	2. Dataflow Languages
		- They model computation as the flow of information (tokens) among primitive functional nodes
		- They provide an inherently parallel model: nodes are triggered by the arrival of input tokens, and can operate concurrently
		- *e.g. Id and Val are examples of dataflow languages. Sisal, a descendant of Val, is more often described as a functional language*
	3. Logic or constraint-based languages
		- Take their inspiration from **predicate logic**
		- They **model computation** as **an attempt to find values that satisfy certain specified relationships**
			- *e.g. Prolog is the best-known logic language*
		- The **term** is also **sometimes** applied to the **SQL** database language, the XSLT scripting language, and programmable aspects of spreadsheets such as Excel and its predecessors
	4. The von Neumann languages
		- The **most familiar** and widely used
		- They include Fortran, Ada, C, and all of the others in which the **basic means of computation is the modification of variables**
		- Von Neumann languages **are based on statements** (assignments in particular) that influence subsequent computation
	5. Object-oriented languages
		- Most are closely related to the **von Neumann languages**
		- Have a much more structured and distributed model of memory and computation
		- Rather than picture computation as the operation of a monolithic processor on a monolithic memory, object-oriented languages picture it as interactions among semi-independent objects, each of which has both its own internal state and subroutines to manage that state
	6. Scripting Languages
		- Used to glue components together
		- Often used for **automating tasks** and "gluing" together other software components
		- Emphasis on productivity
		- Examples: Python, Ruby, JavaScript, Bash

## Core Langauge Concepts
- Types
- Control Structures
- Abstraction
- Naming

### Exercise: Write a pseudocode to compute the sum of all even numbers from 1 to N using a(n) imperative paradigm, (b) declarative paradigm
1. Compute the sum of all even numbers from 1 to N
2. Find the maximum value in a list

## Program Compilation
- A compiler **translates the high-level source** program into an **equivalent target program** (typically in machine language) and then **goes away**
- At some arbitrary later time, **the user tells the operating system** to **run the target** program
- During **compilation, control resides in the compiler**; during **execution,** control shifts to the **target program**

## Program Interpretation
- Unlike a compiler, an interpreter **stays** around **for the execution** of the application
- During **execution,** the **interpreter** has control of the operation
- The interpreter **reads statements** in that **one at a time, executing** them as it goes along

## Tradeoffs
- **Interpretation**
	- Leads to greater flexibility and better diagnostics (error messages)
	- Because the **source code is being executed** directly, the interpreter can include an excellent **source-level debugger**
- **Compilation**
	- Leads to better **performance**
	- A **decision made at compile** time is a decision that **does not** need to be made at **run time**
		- Example: if variable **x** is known to always be at memory location **49378**, the **compiler generates** direct machine **instructions** to access that location
		- No additional lookup is required during execution

## Compilation and Interpretation Together
- Most language implementations include a **mixture of compilation** and interpretation
- We generally say that a language is **"interpreted"** when the **initial translator (compiler) is simple**
- If the **translator is complicated**, we say that the language is **"compiled"**
- Tokens such as keywords, identifiers, numbers, and symbols
- Most interpreted languages employ an initial translator (a preprocessor) that removes comments and white space, and groups characters together into

### Exercises: Compilation vs. Interpretation
- Instructional:
	- Write and execute a simple program in both Python and C++.
	- Explain how execution differ in these languages
- Program examples:
	- Checking if a number is even or odd
	- Finding the largest of three numbers
	- Temperature conversion (Celsius ↔ Fahrenheit)

## Programming Environments
- **Compilers and interpreters** are part of a **larger** tool **ecosystem**
- Programmers rely on **multiple tools** to write, debug, and maintain software
- These tools support **productivity**, **correctness**, and **performance**

## Programming Tools
1. Common Programming Tools
	- **Editors**: used to write and modify source code
	- **Assemblers**: translate assembly language to machine code
	- **Linkers**: combine separately compiled modules
	- **Preprocessors**: handle macros
	- **Debuggers**: help locate and fix runtime errors
2. Code Navigation and Quality Tools
	- **Cross-referencing tools**: find where variables or functions are defined.
	- **Pretty printers**: enforce consistent code formatting.
	- **Style checkers**: enforce stricter syntactic or semantic conventions.
	- **Often apply rules beyond what the compiler enforces.**
3. Configuration Management
	- **Tracks dependencies** among many versions of modules.
	- Supports large systems with **separately compiled components.**
	- Helps **ensure correct builds** after code **changes**
4. Performance Analysis Tools
	- **Profilers** identify where programs spend most of their execution time.
	- Often used alongside debuggers.
	- Help optimize performance-critical sections of code.
5. Integrated Development Environments (IDE)
	- Combine editor, compiler, debugger, and build tools.
	- Errors highlight the exact source line where they occur.
	- Breakpoints and tracing set without explicitly invoking a debugger.
	- Source changes made without explicitly invoking an editor.
- Advanced IDE features
	- Editors understand language syntax.
	- Provide templates for common control structures.
	- Perform syntax checking while typing.
	- Maintain an internal, partially compiled representation.
	- Update internal structures incrementally after edits.
	- Structural changes may propagate automatically to source code.
#### KEY TAKEAWAY
- Programming environments evolved from separate tools to integrated systems. 
- IDEs improve productivity, debugging, and code understanding.
- Modern software development relies heavily on tool integration
