A function declaration in solidity looks like the following:



function eatHamburgers\(string \_name, uint \_amount\) {



}

This is a function named eatHamburgers that takes 2 parameters: a string and a uint. For now the body of the function is empty.



> Note: It's convention \(but not required\) to start function parameter variable names with an underscore \(\_\) in order to differentiate them from global variables. We'll use that convention throughout our tutorial.



You would call this function like so:



eatHamburgers\("vitalik", 100\);

