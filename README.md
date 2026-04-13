# Chip Test Automation & Verification Infrastructure

**Notes and engineering articles on chip test automation, vector generation, WGL processing, synthesizable testbench generation, and verification infrastructure.**

This repository collects a series of technical articles and engineering notes around a core question:

> How can test intent be translated into executable, reusable, and scalable infrastructure?

The content here is not limited to protocol descriptions or tool usage.  
The focus is on **engineering structure**, including:

- functional test vector generation
- JTAG / DP / AP based access flows
- VCD to WGL conversion
- multi-WGL integration
- synthesizable testbench generation
- verification acceleration oriented workflows

---

## Repository Focus

This repository currently follows three major tracks:

### 1. JTAG Vector Generation
From functional test intent to JTAG-level vectors.

Topics include:

- why traditional functional test vector flows become slow
- template-based generation from test instructions
- why DP/AP read-write operations are the right abstraction layer
- how TDI / TMS / TCK / TDO are actually derived through the JTAG state machine

### 2. WGL to Synthesizable Testbench
From test patterns to reusable verification execution units.

Topics include:

- why merging multiple WGL files improves verification throughput
- what a synthesizable testbench package really contains
- clock and timing offset alignment across multiple test cases
- bidirectional pins, valid bits, and pattern switching

### 3. VCD to WGL Toolchain Engineering
A focused engineering track on building practical conversion tools.

Topics include:

- why VCD to WGL is not just a text format conversion
- clock selection, sampling semantics, pad mapping, and vector extraction
- why script-based implementations eventually need tool-style refactoring
- how VCD->WGL can connect to ATE flows, WGL integration, and synthesizable testbench generation

---

## Article Series

### Part I — JTAG Vector Generation

1. **Why Traditional Functional Test Vector Flows Keep Slowing Down**
2. **From Functional Test Instructions to JTAG Vectors: A Template-Based Generation Method**
3. **Why DP/AP Read-Write Is the Right Basic Abstraction for Chip Test Tasks**
4. **The JTAG State Machine Is Not a Black Box: How TDI / TMS / TCK / TDO Are Actually Derived**

### Part II — WGL to Synthesizable Testbench

5. **Why Merging Multiple WGL Files into One Synthesizable Testbench Improves Verification Efficiency**
6. **What Are the Key Parts of a Synthesizable Testbench?**
7. **The Hardest Part of Multi-Pattern Integration Is Not File Generation, but Clock and Timing Offset Alignment**
8. **Bidirectional Pins, Valid Bits, and Pattern Switching: How One Testbench Can Run Multiple Patterns**

### Part III — VCD to WGL Toolchain Engineering

9. **VCD to WGL: The Hard Part Is Not Format Conversion, but Sampling**
10. **Why VCD->WGL Scripts Eventually Need to Be Rebuilt as C++ Tools**
11. **VCD->WGL Is Not the End: How It Connects to ATE, Multi-WGL Integration, and Synthesizable Testbench Flows**

---

## Why This Repository Exists

In many real projects, test flows become fragmented:

- test intent lives in one place
- vector generation logic lives in another
- waveform conversion is handled by ad hoc scripts
- WGL handling is disconnected from downstream verification execution

As complexity grows, the real bottleneck is no longer a single conversion step.  
The bottleneck becomes the lack of a coherent infrastructure model.

This repository is built to document a more structured view:

**test intent -> protocol abstraction -> vector generation -> WGL organization -> synthesizable execution framework**

---

## Intended Readers

This repository may be useful for:

- engineers working on chip test, ATE, DFT, or verification platforms
- engineers dealing with JTAG, debug access, register/bus access automation
- engineers interested in verification throughput, infrastructure reuse, and toolchain engineering
- readers who want to understand not only *what* a flow does, but *how* it should be structured

---

## Engineering Viewpoint

A recurring theme in this repository is:

> The real value is not a single script or a single file format converter.  
> The real value is building reusable infrastructure from test semantics all the way down to executable artifacts.

That is why the articles here emphasize:

- abstraction boundaries
- modular flow design
- sampling semantics
- data organization
- execution efficiency
- long-term maintainability

---

## Repository Structure

```text
.
├─ README.md
├─ articles/
│  ├─ 01-why-traditional-functional-test-vector-flows-slow-down.md
│  ├─ 02-from-functional-test-instructions-to-jtag-vectors.md
│  ├─ 03-why-dp-ap-read-write-is-the-right-abstraction.md
│  ├─ 04-how-jtag-tdi-tms-tck-tdo-are-derived.md
│  ├─ 05-why-merging-multiple-wgl-files-improves-verification-efficiency.md
│  ├─ 06-key-parts-of-a-synthesizable-testbench.md
│  ├─ 07-clock-and-timing-offset-alignment-in-multi-pattern-integration.md
│  ├─ 08-bidirectional-pins-valid-bits-and-pattern-switching.md
│  ├─ 09-vcd-to-wgl-the-hard-part-is-sampling.md
│  ├─ 10-why-vcd-to-wgl-scripts-need-cpp-tools.md
│  └─ 11-how-vcd-to-wgl-connects-to-larger-test-flows.md
├─ demos/
│  └─ vcd_to_wgl_demo.cpp
└─ images/
