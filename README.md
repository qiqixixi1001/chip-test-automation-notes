# Chip Test Automation Notes

Engineering notes on JTAG / DFT / ATE / chip test automation / verification infrastructure.

## What this repository is about
This repository focuses on a structured automation path:
functional test intent → primitive templates → JTAG state-driven expansion → executable vectors / downstream testbench flow.

## Why this matters
Traditional vector flows often depend too heavily on waveforms, manual scripts, and long change chains.
This series explains a more scalable architecture.

## Series Map
1. Why Traditional Functional Test Vector Flows Slow Down Over Time
2. From Functional Test Instructions to JTAG Vectors
3. Why DP/AP Read-Write Is the Right Abstraction
4. JTAG State Machine Is Not a Black Box

## Target audience
DFT engineers / validation engineers / test automation engineers / EDA infrastructure engineers

## Key engineering ideas
- test-intent-driven generation
- primitive template abstraction
- JTAG state-machine driven signal expansion
- scalable downstream vector / WGL / testbench organization

## About the author
Darren H. Chen
Semiconductor test automation / DFT / verification infrastructure
