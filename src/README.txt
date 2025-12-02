
# Petri Net Analysis: BDD & ILP

This project implements symbolic and algebraic reasoning in Petri nets, focusing on reachability analysis, deadlock detection, and optimization using Binary Decision Diagrams (BDD) and Integer Linear Programming (ILP).

## Project Overview

The main objective of this project is to:
- Parse a 1-safe Petri net from PNML (Petri Net Markup Language) files.
- Compute reachable markings explicitly and symbolically using BDDs.
- Detect deadlocks using a combination of ILP and BDDs.
- Perform optimization over reachable markings using the Karp-Miller tree and integer weights.

## Requirements

This project requires Python 3.x and the following Python libraries:
- **pulp**: Used for ILP (Integer Linear Programming) to solve deadlock detection.
- **dd**: Used for Binary Decision Diagrams (BDD) for symbolic reachability analysis.
- **xml.etree.ElementTree**: Python's standard library for parsing XML files, used to parse PNML files.

### Installing Dependencies

All necessary dependencies are listed in the `requirements.txt` file. To install them, simply run:

```bash
pip install -r requirements.txt
```

Once the dependencies are installed, you're ready to run the project.

## Setup Instructions

1. **Clone or download** the project files to your local machine.
2. **Install dependencies** by running:
   ```bash
   pip install -r requirements.txt
   ```

3. **File Structure**:
   The project folder is organized as follows:

   ```
   __pycache__/
   venv/
   bdd_encoding.py
   bdd_reachability.py
   ilp_bdd_deadlock.py
   main.py
   optimization.py
   PetriNetSample.pnml
   PetriNetSample_Deadlock.pnml
   PetriNetSample_Deadlock2.pnml
   PNML_Read.py
   README.txt
   ```

   - `main.py`: The main entry point that integrates all functionalities (parsing, reachability, deadlock detection, optimization).
   - `PNML_Read.py`: Contains functions for parsing PNML files and performing BFS-based reachability analysis.
   - `bdd_encoding.py`: Functions to build BDD structures for Petri nets.
   - `bdd_reachability.py`: Functions to compute reachability using BDDs.
   - `ilp_bdd_deadlock.py`: Implements ILP-based deadlock detection in combination with BDDs.
   - `optimization.py`: Implements the Karp-Miller tree-based optimization over reachable markings.
   - `PetriNetSample.pnml`, `PetriNetSample_Deadlock.pnml`, `PetriNetSample_Deadlock2.pnml`: Example PNML files containing Petri nets.
   - `README.txt`: This file, providing instructions for the project.

4. **Input Files**:
   Ensure that the required input PNML files (`PetriNetSample.pnml`, `PetriNetSample_Deadlock.pnml`, etc.) are present in the project directory or provide the correct path.

## Running the Program

### Running the Script

To run the analysis on Petri nets, simply execute the following command in your terminal:

```bash
python main.py
```

This will automatically perform the following tasks:
1. Parse the provided PNML files to extract Petri net components (places, transitions, arcs, initial marking).
2. Perform explicit BFS-based reachability analysis and print the number of reachable markings.
3. Compute symbolic reachability using BDD and print the number of reachable markings using this method.
4. Detect deadlocks using ILP combined with BDD and print the results (if any deadlocks are detected).
5. Optimize over reachable markings using Karp-Miller tree and print the best marking and its corresponding value.

### Output

The output will be printed in the terminal and will include:
- The number of reachable markings (both explicit and BDD-based).
- Any detected deadlock markings (if applicable).
- Optimization results, including the best reachable marking and its corresponding value.

### Example Output:

```plaintext
=== Explicit reachability (BFS) ===
Number of reachable markings (explicit): 10

=== BDD reachability ===
Number of reachable markings (BDD): 10

=== Deadlock detection (ILP + BDD) ===
Deadlock marking (if any): None
Deadlock search time: 0.0254 s
ILP iterations: 100

=== Optimization over reachable markings (Karp–Miller) ===
Best value: 150
Best marking:
  p1: 5
  p2: 3
  p3: ω
```

## Files Description

- **`main.py`**: The script that runs the entire pipeline (parsing, reachability, deadlock detection, and optimization).
- **`PNML_Read.py`**: Contains functions to parse PNML files and compute explicit BFS reachability.
- **`bdd_encoding.py`**: Contains the `build_bdd_structures` function to generate Binary Decision Diagram (BDD) structures.
- **`bdd_reachability.py`**: Contains functions to compute the reachable set of markings using BDDs.
- **`ilp_bdd_deadlock.py`**: Implements ILP-based deadlock detection using BDD reachability.
- **`optimization.py`**: Implements the optimization over reachable markings using the Karp-Miller tree.

## Contributing

If you would like to contribute to this project, please fork the repository, make your changes, and submit a pull request. All contributions are welcome, but make sure to follow the structure and guidelines mentioned in the report for clarity.

## License

This project is for academic use only. Redistribution without permission is prohibited.

## Contact

For any questions or issues, feel free to reach out to the instructor or refer to the assignment forum on the course platform.
