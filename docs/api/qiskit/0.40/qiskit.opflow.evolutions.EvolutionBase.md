---
title: EvolutionBase
description: API reference for qiskit.opflow.evolutions.EvolutionBase
in_page_toc_min_heading_level: 1
python_api_type: class
python_api_name: qiskit.opflow.evolutions.EvolutionBase
---

# EvolutionBase[¶](#evolutionbase "Permalink to this headline")

<span id="qiskit.opflow.evolutions.EvolutionBase" />

`EvolutionBase`

Bases: [`qiskit.opflow.converters.converter_base.ConverterBase`](qiskit.opflow.converters.ConverterBase "qiskit.opflow.converters.converter_base.ConverterBase"), `abc.ABC`

A base for Evolution converters. Evolutions are converters which traverse an Operator tree, replacing any `EvolvedOp` e with a Schrodinger equation-style evolution `CircuitOp` equalling or approximating the matrix exponential of -i \* the Operator contained inside (e.primitive). The Evolutions are essentially implementations of Hamiltonian Simulation algorithms, including various methods for Trotterization.

## Methods Defined Here

### convert

<span id="qiskit.opflow.evolutions.EvolutionBase.convert" />

`abstract EvolutionBase.convert(operator)`

Traverse the operator, replacing any `EvolutionOps` with their equivalent evolution `CircuitOps`.

> #### Args:
>
> operator: The Operator to convert.

**Return type**

[`OperatorBase`](qiskit.opflow.OperatorBase "qiskit.opflow.operator_base.OperatorBase")

**Returns**

The converted Operator, with `EvolutionOps` replaced by `CircuitOps`.
