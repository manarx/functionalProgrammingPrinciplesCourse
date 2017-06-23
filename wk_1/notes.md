- Evaluation Strategies:
	- callByValue:
		- evaluates every function argument only once

	- callByName:
		- a func argument is not evaluated if the corresponding parameter is unused in the evaluation of the function body.

	- example: def test(x: Int, y: int) = x * x    test(3+4, 2*4) ?
		- CBV: test(7, 2*4) => test(7*8) => 7*7 => 49
		- CBN: (3+4) * (3+4) => 7 * (3+4) => 7*7 => 49


	- Both strategies reduce an expr to the same value, as long as both evaluations terminate(!).
	- Scala normally uses CBV. If the type of a function parameter starts with => it uses CBN.
		- def constOne(x: Int, y: => Int) = 1
	
- Value Definitions:
	- byName:
		- using def: its right-hand side is evaulated on each use
	- byValue:
		- using val: right-hand side is evaluated at the point of the definition itself
			ex: val x = 2; val y = square(x) ==> y = 4 not square(x) ==> the name refers to the value

