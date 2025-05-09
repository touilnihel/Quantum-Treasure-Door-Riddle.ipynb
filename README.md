# Quantum-Treasure-Door-Riddle.ipynb


## Overview  
This project implements a quantum circuit simulation of the classic "Treasure Door" logic puzzle using Qiskit. The simulation demonstrates how quantum computing principles can model all possible scenarios of the riddle simultaneously through superposition and entanglement.

## The Riddle  
You face two doors with guardians:  
- One door leads to treasure, the other to nothing  
- One guardian always lies, the other always tells the truth  
- You don't know which is which  
- Both guardians know where the treasure is and which one lies  

**Solution:** Ask either guardian: *"Which door would the other guardian tell me not to open?"* Then choose the opposite door.

## Quantum Implementation  
The simulation uses 3 qubits:  
- `q0`: Treasure location (0=left, 1=right)  
- `q1`: Other guardian's knowledge (entangled with q0)  
- `q2`: Which guardian is lying (0=left lies, 1=right lies)  


## Expected Output

When you run the notebook, you'll see:

1. **Quantum Circuit Diagram**:
   - A visual representation of the 3-qubit circuit
   - Shows all gates applied (H, CNOT, X, SWAP)
   - Displays the final measurement operations

2. **Measurement Histogram**:
   - Results from 1024 simulations of the quantum circuit
   - Four possible outcomes displayed as bars:
     - `00`: Both guardians indicate left door (25% probability)
     - `01`: Guardians disagree (should never occur - 0% probability)
     - `10`: Guardians disagree (should never occur - 0% probability)
     - `11`: Both guardians indicate right door (25% probability)
   - Note: Due to quantum randomness, small non-zero probabilities may appear for 01/10

3. **Consistent Answers**:
   - Valid solutions will only show `00` or `11` results
   - This demonstrates both guardians give the same answer despite one lying

## Interpretation Guide

| Measurement | Meaning | Correct Action |
|-------------|---------|-----------------|
| `00` | Both guardians say "don't open left" | **Choose right door** |
| `11` | Both guardians say "don't open right" | **Choose left door** |
| `01` or `10` | Error case (shouldn't occur) | Re-run simulation |

Key Insights:
1. The 50/50 distribution between `00` and `11` shows the solution works regardless of:
   - Which door actually has the treasure
   - Which guardian is lying
2. The equal probabilities demonstrate quantum superposition handling all scenarios
3. The identical answers prove the classical logic holds in quantum formulation

## License
MIT License
