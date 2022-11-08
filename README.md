## Python Simple Cycles

This is an algorithm for finding all the simple [cycles][4] in a directed graph.

This was implemented directly from the 1975 Donald B Johnson [paper][5] "Finding all the elementary circuits of a directed graph" with modificatios so that it didn't depend on the NetworkX data structures (so the algorithm could be used in [IronPython][3]). Tarjan's algorithm was modified to a [non-recursive implementation][6].

[NetworkX][1]'s [original implementation][2]

[1]: https://networkx.github.io/
[2]: https://github.com/networkx/networkx/blob/master/networkx/algorithms/cycles.py#L110
[3]: http://ironpython.net/
[4]: https://en.wikipedia.org/wiki/Cycle_(graph_theory)
[5]: https://doi.org/10.1137/0204007 
[6]: https://code.activestate.com/recipes/578507/ 

The original paper which described the algorithm:  
Donald B Johnson. "Finding all the elementary circuits of a directed graph." SIAM Journal on Computing. 1975.






### Example

```python
>>> from johnson import simple_cycles
>>> graph = {0: [7, 3, 5], 1: [2], 2: [7, 1], 3: [0, 5], 4: [6, 8], 5: [0, 3, 7], 6: [4, 8], 7: [0, 2, 5, 8], 8: [4, 6, 7]}
>>> print(tuple(simple_cycles(graph)))
([0, 7, 5, 3], [0, 7, 5], [0, 7], [0, 5, 7], [0, 5, 3], [0, 5], [0, 3, 5, 7], [0, 3, 5], [0, 3], [1, 2], [2, 7], [3, 5], [8, 7], [8, 6, 4], [8, 6], [8, 4, 6], [8, 4], [5, 7], [4, 6])
```
