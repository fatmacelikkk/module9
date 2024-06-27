# module9
from pycsp3 import *

n = 8

# q[i] is the column of the ith queen (at row i)
q = VarArray(size=n, dom=range(n))

satisfy(
   # all queens are put on different columns
   AllDifferent(q),

   # no two queens on the same upward diagonal
   AllDifferent(q[i] + i for i in range(n)),

   # no two queens on the same downward diagonal
   AllDifferent(q[i] - i for i in range(n))
)
