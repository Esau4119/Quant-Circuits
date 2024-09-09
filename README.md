# Quant-Circuits Date: 02/21/24

<h2>Overview </h2>
This coding project focuses on constructing and manipulating the quantum state of mutli-qubit systems.  Like Coding Project #1, this is a multi-part assignment. Environment will consist of Python+Qiskit in a Jupyter notebook. 
<h2>Part 1: Conditional bit flipping</h2>
This is a two part problem where you will implement two solutions: one classical and one quantum.

The problem: Given a set of 2^3 3-bit vectors, [000, 001, … , 110, 111], flip the two most significant bits (MSBs) if the least significant bit (LSB) is set. The LSB of input always goes to the output.

For example: 000→000, 001→111, 110→110, 111→001, etc.
## Part 1a: Classical implementation


For your Python implementation, use this definition for your input data:

in_data = [0b000, 0b001, 0b010, 0b011,  0b100, 0b101, 0b110, 0b111]

Your Python implementation should iterate over all these inputs and produce outputs that satisfy the conditional bit flipping as described above. Be sure your implementation prints out the inputs and outputs.

## Part 1b: quantum implementation


For your quantum implementation, create a quantum circuit using 3 qubits. Using quantum gates and entanglement, this circuit should perform this same bit-flipping operation, where if the LSB (qubit 0) is set, then flip the bit (the state) of the other two MSB (qubits 1 and 2).

You will create multiple circuits: one for each of the input values. To initialize the state of your qubits to reflect the bit settings of the input values, DO NOT USE qiskit’s Initialize method. Instead, assume that qubits are created in a |0> state, and if you need to flip the state to |1>, use the appropriate gate (eg, from CP1) that flips the state of a specific qubit. You do not need a measurement gate in this circuit.

For each of the input values in in_data[] above:
Print the input value being processed
Generate a qiskit quantum circuit that will do the conditional bit flipping as described earlier
Display your circuit using print() or draw()
Use the Statevector operator to obtain the state vector from your circuit (don’t run it through a simulator, see lecture slides for examples)
Display the state vector using the draw(“latex”) method. Note the state vector of your circuit will contain the solution to the conditional bit flipping problem.

## Part 2: Implement “Controlled Swap” using Building Block Gates

Construct a 3-qubit circuit that Implements a “controlled swap” gate using building block gates like CNOT. In this circuit, qubits 0 and 1 are the two that may potentially be swapped, while qubit 2 is the control qubit. So, if qubit 2 is |1> then swap the states of qubits 0 and 1.  

E.g., 000→000, 100→100, 010→010, 110→101, etc.

You will create multiple circuits: one for each of the input values. To initialize the state of your qubits to reflect the bit settings of the input values, DO NOT USE qiskit’s Initialize method. Instead, assume that qubits are created in a |0> state, and if you need to flip the state to |1>, use the appropriate gate (eg, from CP1) that flips the state of a specific qubit. You do not need a measurement gate in this circuit.

Test your implementation using the in_data above and using the same methodology for qubit initialization as in Part 1. For each input in_data value:

Print the input value being processed

Generate a qiskit quantum circuit that will do the controlled swap operation as above

Display your circuit using print() or draw()

Use the Statevector operator to obtain the state vector from your circuit (don’t run it through a simulator, see lecture slides for examples)

Display the state vector using the draw(“latex”) method. Note the state vector of your circuit will contain the solution to the controlled swap operation on 3 qubits

## Part 3: Evolving towards a specified solution state
Construct a 2-qubit quantum circuit that will result in a final distribution that concentrates 50% of the probabilities on states |10> and |01>. This circuit should include gates that create states of superposition, whatever gates you need to steer the solution towards the target states, and measurement gates. Run this circuit using the aer_simulator simulator for 1000 shots. Obtain the counts from the results() object and plot the histogram of counts/probabilities using qiskit’s plot_distribution() method to show your results. 





