# SPI-Slave-with-Single-Port-RAM


This project implements an SPI (Serial Peripheral Interface) slave module with a single port RAM block. The SPI slave module receives data from a master device and communicates with the single port RAM to store and retrieve data.

## Project Overview

The project consists of the following components:
- **SPI Slave Module**: Handles communication with the SPI master.
- **Single Port RAM Module**: Provides memory storage for the data received from the SPI master.

## File Structure


SPI-Slave-with-Single-Port-RAM/ ├── README.md ├── rtl/ │ ├── spi_slave.v │ ├── single_port_ram.v │ └── top_module.v ├── testbench/ │ ├── spi_slave_tb.v │ └── single_port_ram_tb.v └── docs/ ├── schematic.pdf └── report.pdf


## SPI Slave Module

The SPI slave module is responsible for receiving data from the master device and interacting with the RAM module. It has the following ports:

| Name   | Type   | Size | Description                        |
|--------|--------|------|------------------------------------|
| clk    | Input  | 1 bit| Clock signal                       |
| rst_n  | Input  | 1 bit| Active low reset signal            |
| SS_n   | Input  | 1 bit| Slave Select signal                |
| MOSI   | Input  | 1 bit| Master-Out-Slave-In data signal    |
| MISO   | Output | 1 bit| Master-In-Slave-Out data signal    |
| tx_data| Input  | 8 bit| Data to be transmitted to the master|
| rx_data| Output | 8 bit| Data received from the master      |

## Single Port RAM Module

The single port RAM module implements a memory block with a single data port. It has the following parameters:

| Parameter | Default | Description           |
|-----------|---------|-----------------------|
| MEM_DEPTH | 256     | Depth of the memory   |
| ADDR_SIZE | 8       | Size of the memory address |

### Ports

| Name   | Type   | Size | Description                        |
|--------|--------|------|------------------------------------|
| clk    | Input  | 1 bit| Clock signal                       |
| rst_n  | Input  | 1 bit| Active low reset signal            |
| din    | Input  | 8 bit| Data input                         |
| dout   | Output | 8 bit| Data output                        |
| addr   | Input  | 8 bit| Memory address                     |
| we     | Input  | 1 bit| Write enable                       |

## Simulation and Synthesis

To simulate and synthesize the design, use the provided scripts in the `scripts/` directory. The project is compatible with tools like QuestaSim and Vivado.

## Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/SPI-Slave-with-Single-Port-RAM.git
   cd SPI-Slave-with-Single-Port-RAM

Run the simulation:
cd testbench
vsim -do run.do

Synthesize the design:
cd rtl
vivado -mode batch -source run.tcl

Documentation
Detailed documentation and schematics are available in the docs/ directory.

License
This project is licensed under the MIT License - see the LICENSE file for details.

Acknowledgments
Thanks to the open-source community for providing valuable resources and tools.
