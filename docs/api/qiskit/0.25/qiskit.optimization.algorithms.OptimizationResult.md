# qiskit.optimization.algorithms.OptimizationResult

<span id="undefined" />

`OptimizationResult(x, fval, variables, status, raw_results=None, samples=None)`

A base class for optimization results.

The optimization algorithms return an object of the type `OptimizationResult` with the information about the solution obtained.

`OptimizationResult` allows users to get the value of a variable by specifying an index or a name as follows.

## Examples

```python
>>> from qiskit.optimization import QuadraticProgram
>>> from qiskit.optimization.algorithms import CplexOptimizer
>>> problem = QuadraticProgram()
>>> _ = problem.binary_var('x1')
>>> _ = problem.binary_var('x2')
>>> _ = problem.binary_var('x3')
>>> problem.minimize(linear={'x1': 1, 'x2': -2, 'x3': 3})
>>> print([var.name for var in problem.variables])
['x1', 'x2', 'x3']
>>> optimizer = CplexOptimizer()
>>> result = optimizer.solve(problem)
>>> print(result.variable_names)
['x1', 'x2', 'x3']
>>> print(result.x)
[0. 1. 0.]
>>> print(result[1])
1.0
>>> print(result['x1'])
0.0
>>> print(result.fval)
-2.0
>>> print(result.variables_dict)
{'x1': 0.0, 'x2': 1.0, 'x3': 0.0}
```

<Admonition title="Note" type="note">
  The order of variables should be equal to that of the problem solved by optimization algorithms. Optimization algorithms and converters of `QuadraticProgram` should maintain the order when generating a new `OptimizationResult` object.
</Admonition>

**Parameters**

*   **x** (`Union`\[`List`\[`float`], `ndarray`, `None`]) – the optimal value found in the optimization, or possibly None in case of FAILURE.
*   **fval** (`float`) – the optimal function value.
*   **variables** (`List`\[`Variable`]) – the list of variables of the optimization problem.
*   **raw\_results** (`Optional`\[`Any`]) – the original results object from the optimization algorithm.
*   **status** (`OptimizationResultStatus`) – the termination status of the optimization algorithm.
*   **samples** (`Optional`\[`List`\[`SolutionSample`]]) – the solution samples.

**Raises**

[**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError#qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – if sizes of `x` and `variables` do not match.

<span id="undefined" />

`__init__(x, fval, variables, status, raw_results=None, samples=None)`

**Parameters**

*   **x** (`Union`\[`List`\[`float`], `ndarray`, `None`]) – the optimal value found in the optimization, or possibly None in case of FAILURE.
*   **fval** (`float`) – the optimal function value.
*   **variables** (`List`\[`Variable`]) – the list of variables of the optimization problem.
*   **raw\_results** (`Optional`\[`Any`]) – the original results object from the optimization algorithm.
*   **status** (`OptimizationResultStatus`) – the termination status of the optimization algorithm.
*   **samples** (`Optional`\[`List`\[`SolutionSample`]]) – the solution samples.

**Raises**

[**QiskitOptimizationError**](qiskit.optimization.QiskitOptimizationError#qiskit.optimization.QiskitOptimizationError "qiskit.optimization.QiskitOptimizationError") – if sizes of `x` and `variables` do not match.

## Methods

|                                                                                                                                                                          |                                                         |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------- |
| [`__init__`](#qiskit.optimization.algorithms.OptimizationResult.__init__ "qiskit.optimization.algorithms.OptimizationResult.__init__")(x, fval, variables, status\[, …]) | **type x**`Union`\[`List`\[`float`], `ndarray`, `None`] |

## Attributes

|                                                                                                                                                          |                                                                                         |
| -------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------- |
| [`fval`](#qiskit.optimization.algorithms.OptimizationResult.fval "qiskit.optimization.algorithms.OptimizationResult.fval")                               | Returns the optimal function value.                                                     |
| [`raw_results`](#qiskit.optimization.algorithms.OptimizationResult.raw_results "qiskit.optimization.algorithms.OptimizationResult.raw_results")          | Return the original results object from the optimization algorithm.                     |
| [`samples`](#qiskit.optimization.algorithms.OptimizationResult.samples "qiskit.optimization.algorithms.OptimizationResult.samples")                      | Returns the list of solution samples                                                    |
| [`status`](#qiskit.optimization.algorithms.OptimizationResult.status "qiskit.optimization.algorithms.OptimizationResult.status")                         | Returns the termination status of the optimization algorithm.                           |
| [`variable_names`](#qiskit.optimization.algorithms.OptimizationResult.variable_names "qiskit.optimization.algorithms.OptimizationResult.variable_names") | Returns the list of variable names of the optimization problem.                         |
| [`variables`](#qiskit.optimization.algorithms.OptimizationResult.variables "qiskit.optimization.algorithms.OptimizationResult.variables")                | Returns the list of variables of the optimization problem.                              |
| [`variables_dict`](#qiskit.optimization.algorithms.OptimizationResult.variables_dict "qiskit.optimization.algorithms.OptimizationResult.variables_dict") | Returns the optimal value as a dictionary of the variable name and corresponding value. |
| [`x`](#qiskit.optimization.algorithms.OptimizationResult.x "qiskit.optimization.algorithms.OptimizationResult.x")                                        | Returns the optimal value found in the optimization or None in case of FAILURE.         |

<span id="undefined" />

`property fval`

Returns the optimal function value.

**Return type**

`float`

**Returns**

The function value corresponding to the optimal value found in the optimization.

<span id="undefined" />

`property raw_results`

Return the original results object from the optimization algorithm.

Currently a dump for any leftovers.

**Return type**

`Any`

**Returns**

Additional result information of the optimization algorithm.

<span id="undefined" />

`property samples`

Returns the list of solution samples

**Return type**

`List`\[`SolutionSample`]

**Returns**

The list of solution samples.

<span id="undefined" />

`property status`

Returns the termination status of the optimization algorithm.

**Return type**

`OptimizationResultStatus`

**Returns**

The termination status of the algorithm.

<span id="undefined" />

`property variable_names`

Returns the list of variable names of the optimization problem.

**Return type**

`List`\[`str`]

**Returns**

The list of variable names of the optimization problem.

<span id="undefined" />

`property variables`

Returns the list of variables of the optimization problem.

**Return type**

`List`\[`Variable`]

**Returns**

The list of variables.

<span id="undefined" />

`property variables_dict`

Returns the optimal value as a dictionary of the variable name and corresponding value.

**Return type**

`Dict`\[`str`, `float`]

**Returns**

The optimal value as a dictionary of the variable name and corresponding value.

<span id="undefined" />

`property x`

Returns the optimal value found in the optimization or None in case of FAILURE.

**Return type**

`Optional`\[`ndarray`]

**Returns**

The optimal value found in the optimization.