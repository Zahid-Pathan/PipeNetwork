# PipeNetwork

A C++ console application for simulating water flow in a pipe network. This program calculates the flow distribution in a system of interconnected pipes and nodes based on given input data. It is designed as part of a computational engineering assignment at the Technical University of Munich.

## Features

- **Node and Tube Classes**: Each node is represented with coordinates and flow values, and each tube has a diameter and connects two nodes.
- **Flow Calculation**: Uses permeability matrices and flow equations to compute hydraulic head and flow across tubes.
- **Configurable Input**: Reads nodes and tubes data from a text file (`pipedata.txt`).
- **Unit Testing**: Includes tests with the `Catch2` framework to verify functionality.

## Requirements

- C++17 or later
- [CMake](https://cmake.org/) for build management
- [Catch2](https://github.com/catchorg/Catch2) for unit testing
- Optional: [Git LFS](https://git-lfs.github.com/) if you are handling large files

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/PipeNetwork.git
   cd PipeNetwork
   
Set up the project using CMake:
bash
Copy code
mkdir build
cd build
cmake ..
make


## Usage
Input File Format
The input file pipedata.txt should contain:

Number of nodes and tubes.
Node data: Each line contains a node with x and y coordinates and a flow value (inflow < 0, outflow > 0).
Tube data: Each line contains the start and end node IDs and the tube diameter.

## Example:

python
Copy code
8
11
0 0 -50
1000 0 -50
2000 0 0
...

## Running the Application
After building, run the main executable to calculate the flow distribution:

bash
Copy code
./PipeNetworkApp

## Running Tests
To run unit tests:

bash
Copy code
./PipeNetworkTests
Code Structure

## Classes:

PipeNetwork: Manages the network of nodes and tubes and performs flow calculations.
Node: Represents each network node with position and flow data.
Tube: Represents pipes with diameter and connections between nodes.
Namespace: All classes are encapsulated in the cie::pipenetwork namespace.

## Algorithm
Set up a permeability matrix based on tube properties.
Create a load vector using node flow data.
Apply boundary conditions to the matrix.
Solve the system of equations for hydraulic head values.
Compute the flow through each tube based on hydraulic head differences.
