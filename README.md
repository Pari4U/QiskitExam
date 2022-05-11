# Qiskit Exam Notes
Study notes for IBM's Quantum Computation using Qikit v0.2x Exam

1. [Perform Operations on Quantum Circuits](#1-perform-operations-on-quantum-circuits-----47) --- 47%
    * Construct multi-qubit quantum registers
    * Measure quantum circuits in classical registers
    * Use single-qubit gates
    * Use multi-qubit gates
    * Use barrier operations
    * Return the circuit depth
    * Extend quantum circuits
    * Return the OpenQASM string for a circuit
2. [Executing Experiments](#2-executing-experiments-----3) --- 3%
    * Execute a quantum circuit
3. [Implement BasicAer: Python-based Simulators](#3-implement-basicaer-python-based-simulators-----3) --- 3%
    * Use the available simulators
4. [Implement Qasm](#4-implement-qasm-----1) --- 1%
    * Read a QASM file and string
5. [Compare and Contrast Quantum Information](#5-compare-and-contrast-quantum-information-----10) --- 10%
    * Use classical and quantum registers
    * Use operators
    * Measure fidelity
6. [Return the Experiment Results](#6-return-the-experiment-results-----7) --- 7%
    * Return and understand the histogram data of an experiment
    * Return and understand the statevector of an experiment
    * Return and understand the unitary of an experiment
7. [Use Qiskit Tools](#7-use-qiskit-tools-----1) --- 1%
    * Monitor the status of a job instance
8. [Display and Use System Information](#8-display-and-use-system-information-----3) --- 3%
    * Perform operations around the Qiskit version
    * Use information gained from %quiskit_backend_overview
9. [Construct Visualizations](#9-construct-visualizations-----19) --- 19%
    * Draw a circuit
    * Plot a histogram of data
    * Plot a Bloch multivector
    * Plot a Bloch vector
    * Plot a QSphere
    * Plot a density matrix
    * Plot a gate map with error rates
10. [Access Aer Provider](#10-access-aer-provider-----6) --- 6%
    * Access a statevector_simulator backend
    * Access a qasm_simulator backend
    * Access a unitary_simulator backend





## 1. Perform Operations on Quantum Circuits --- 47%
Mostly defined in [/circuit/quantumcircuit.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/quantumcircuit.py)

### Construct multi-qubit quantum registers
Can be done explicitly (`qr = QuantumRegister(numqubits, 'name')`) or implicitly (`qc = QuantumCircuit(numqubits, numclbits)`). 

`QuantumRegister` is based on `Register`, although the classical vs quantum differentiation is hidden in the type of `Bit` used.
- [/circuit/quantumregister.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/quantumregister.py)
- [/circuit/register.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/register.py)
- [/circuit/bit.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/bit.py)

### Measure quantum circuits in classical registers
`circuit.measure(qubitSpecifier, clbitSpecifier)`


`circuit.measure_active()` adds measuremeant to all ACTIVE qubits.

`circuit.measure_all()` adds measuremeant to ALL qubits.  Will add classical bits as necessary.

***NOTE*** - There is a `circuit.remove_final_measurement()` that removes all the measures and cleans up any now unused classical bits.



### Use single-qubit gates
All are defined (sort of... methods are defined that import the required gate from [/library/standard_gates/](https://github.com/Qiskit/qiskit-terra/tree/main/qiskit/circuit/library/standard_gates) and appends it to the circuit) way down near the bottom of [/circuit/quantumcircuit.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/quantumcircuit.py)

- `circuit.h(qubitSpecifier)` 
- `circuit.x()`
- `circuit.y()`
- `circuit.z()`
- `circuit.p()`
- `circuit.s()`
- `circuit.sdg()`
- `circuit.t()`
- `circuit.tdg()`
- `circuit.u()`



### Use multi-qubit gates

### Use barrier operations
`qc.barrier()` applies barrier to all qubits, with optional argument to specify qubit(s) to apply barrier to. 

Defined in [/circuit/quantumcircuit.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/quantumcircuit.py), way down at line 2643-ish.



### Return the circuit depth
`qc.depth()` returns the depth of a circuit.  Can accept an optional filter function as an argument.

***NOTE*** - `qc.size()` returns the total number of gate operations, which is not the same thing as the circuit depth.

Defined in [/circuit/quantumcircuit.py](https://github.com/Qiskit/qiskit-terra/blob/main/qiskit/circuit/quantumcircuit.py)


### Extend quantum circuits
***NOTE*** - `qc.combine()` and `qc.extend()` are both deprecated in favor of `qc.compose()` and `qc.tensor()` 




### Return the OpenQASM string for a circuit



## 2. Executing Experiments --- 3%
### Execute a quantum circuit

## 3. Implement BasicAer: Python-based Simulators --- 3%
### Use the available simulators


## 4. Implement Qasm --- 1%
### Read a QASM file and string

## 5. Compare and Contrast Quantum Information --- 10%
### Use classical and quantum registers
### Use operators
### Measure fidelity

## 6. Return the Experiment Results --- 7%
### Return and understand the histogram data of an experiment
### Return and understand the statevector of an experiment
### Return and understand the unitary of an experiment

## 7. Use Qiskit Tools --- 1%
### Monitor the status of a job instance

## 8. Display and Use System Information --- 3%
### Perform operations around the Qiskit version
### Use information gained from %quiskit_backend_overview

## 9. Construct Visualizations --- 19%
### Draw a circuit
### Plot a histogram of data
### Plot a Bloch multivector
### Plot a Bloch vector
### Plot a QSphere
### Plot a density matrix
### Plot a gate map with error rates

## 10. Access Aer Provider --- 6%
### Access a statevector_simulator backend
### Access a qasm_simulator backend
### Access a unitary_simulator backend





