# Implementation-of-SPI-Based-BIST
SPI-Based BIST (Built-In Self-Test)
This project implements a Built-In Self-Test (BIST) architecture using the Serial Peripheral Interface (SPI) protocol in Verilog HDL.
It demonstrates how a system can generate test patterns, send them through SPI, validate the outputs of a Circuit Under Test (CUT), and verify correctness using a Multiple Input Signature Register (MISR) and ROM-based golden signature comparison.

Features

Test Pattern Generator (TPG):Supports LFSR-based patterns and external input patterns.

SPI Master and Slave:Data transfer between master and slave via MOSI/MISO.

Slave Select (SS) acts as operation selector for the CUT.

Circuit Under Test (CUT):Supports ADD, SUB, AND, XOR operations on 4-bit inputs.

MISR (Multiple Input Signature Register):Collects and compresses CUT outputs into a signature.

ROM Block:Stores expected/golden signatures for result comparison.

Pass/Fail Indication:
test_pass = 1 → CUT passed self-test.
test_pass = 0 → CUT failed self-test.

 Project Structure

BIST_SPI – Top-level module integrating all blocks.

TPG – Test Pattern Generator.

SPI_Master – Sends test data via SPI.

SPI_Slave – Receives data and drives the CUT.

CUT – Arithmetic and logic unit (ADD, SUB, AND, XOR).

MISR – Compresses CUT outputs into a signature.

ROM – Compares MISR signature with golden signature.

 How It Works:

Pattern GenerationSelect between LFSR-generated or external input patterns.

SPI Transmission: SPI Master sends patterns to the SPI Slave.

Circuit Under Test (CUT):Performs the selected operation (ADD, SUB, AND, XOR).

Signature Analysis:MISR compresses CUT outputs into a compact signature.

Result Verification:ROM compares MISR signature against expected output.

Pass/Fail flag is asserted.

🔧 Simulation

Simulate the design in Xilinx Vivado / ModelSim.

Observe the following signals:

test_pattern (Generated input pattern)

cut_output (CUT results)

misr_signature (MISR output signature)

test_pass (Pass/Fail flag)
