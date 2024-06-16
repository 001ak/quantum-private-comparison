# Quantum Private Comparison via Quantum Walks on Circle

This repository contains the implementation of the protocol described in the research paper titled "Novel two-party quantum private comparison via quantum walks on circle" by Feng-Lin Chen, Hai Zhang, Su-Gen Chen, and Wen-Tao Cheng.

## Introduction

The problem of secure multi-party computation (SMPC) was proposed by Yao in 1982. This repository implements a protocol for quantum private comparison (QPC) using quantum walks (QWs) on a circle, as described in the mentioned research paper. The protocol allows two parties to compare their private information without revealing it to each other or to an arbitrator (TP).

## Protocol Steps

The implementation follows these steps:

1. **TP’s Initialization**: 
   - TP generates the initial quantum state |φ₀ using a secret position state and coin state.
   - TP applies f steps of quantum walk evolution to generate the quantum state |φf.

2. **TP’s Distribution**: 
   - TP transmits k copies of the quantum state |φf along with decoy particles to Alice.

3. **Alice’s Position Operator and QWs Evolution**: 
   - Alice applies her private information as a position operator on the received state and performs her own QWs evolution.

4. **Alice’s Distribution**: 
   - Alice transmits the modified quantum state to Bob along with decoy particles.

5. **Bob’s Inverse Position Operator**: 
   - Bob applies his private information as an inverse position operator on the received state.

6. **Bob’s Distribution**: 
   - Bob transmits the modified quantum state back to TP.

7. **TP’s Inverse QWs Evolution**: 
   - TP applies the inverse QWs evolution steps to retrieve the quantum state.

8. **TP’s Private Comparison**: 
   - TP measures the quantum state to determine the size relationship between Alice’s and Bob’s private information.

## Implementation

The implementation involves creating quantum circuits using Qiskit and simulating them using AerSimulator on IBM Quantum Lab.

### Prerequisites

- Python 3.7+
- Qiskit
- Numpy

### Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/quantum-private-comparison.git
    cd quantum-private-comparison
    ```

2. Install the required packages:

    ```bash
    pip install qiskit numpy
    ```

### Usage

The main script is `quantum_private_comparison.ipynb`, which performs the following:

1. Defines position and shift operators.
2. Applies the Hadamard gate and shift operator to simulate the quantum walk.
3. Applies the inverse operations to revert to the original state.
4. Measures the quantum states and compares the private information.


### Example

An example of the quantum walk and private comparison is included in the script. It demonstrates the initialization, evolution, and measurement of quantum states.

### Execution on IBM Quantum Lab

1. Open IBM Quantum Lab and create a new notebook.
2. Upload the `quantum_private_comparison.ipynb` script to your notebook.
3. Ensure that the notebook environment has Qiskit installed. If not, install it using:

    ```python
    !pip install qiskit
    ```

4. Run the script cells sequentially in the notebook to perform the quantum private comparison.

