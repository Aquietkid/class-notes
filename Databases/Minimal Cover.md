> The minimal set of functional dependencies which covers the original set of functional dependencies, but does not contain any redundant functional dependencies. 

Minimal cover is also known as _canonical cover_ or _irreducible set_.
# Steps to Find Minimal Cover
1. Make the values on the right-hand side atomic 
	For a functional dependency $X \rightarrow YZ$, write as $X \rightarrow Y$ and $X \rightarrow Z$ 
2. Make the values on the left-hand side atomic
	Use the [[Armstrong's Rules of Inference#^8de335|pseudotransitive axiom]] to determine which attribute is extraneous. 
3. Remove any redundant FDs by checking the closure of the left hand side of each of the functional dependencies - ignoring the functional dependency itself - and determining whether it contains the right-hand side or not. If it does, the functional dependency is redundant. 