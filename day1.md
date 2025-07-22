What is RISC-V?

RISC-V is an instruction set architecture (ISA) which stands for reduced instruction set instead of CISC (complex instruction set). 

So a language would be converted into RISC-V from an machine/interpreter which is then converted into binary from an assembler which is then fed into the chip. The chip is inherently built with RISC-V so you can't do like another set because the chip wouldn't recognize/preform correctly.




SoC Design Using OpenLane
An Overview of Open-Source Digital ASIC Design Flow

Introduction

Modern digital ASIC (Application-Specific Integrated Circuit) design integrates various tools, standards, and processes. OpenLane provides an open-source platform that brings together these components for a full RTL-to-GDSII flow.

Key Elements of ASIC Digital Design
HDLs and RTL Design:
Hardware Description Languages (HDLs) like Verilog are used to model digital systems, including Register-Transfer Level (RTL) representations of IP blocks.
EDA Tools:
Electronic Design Automation (EDA) tools automate the transformation from RTL to layout.
Process Design Kit (PDK):
The PDK serves as the critical interface between the design team and the fabrication process. It contains:
Design rules
Device models
Standard cell libraries
I/O libraries
These files model the foundry’s manufacturing process and are typically shared under NDA.
In 2020, Google and SkyWater released the first open-source PDK for a 130nm process node—sufficient for moderate-speed and non-cutting-edge designs.
Industry Evolution
Historically, IC design and manufacturing were tightly integrated within companies. Today, the industry is more modular:

Fabless Design Companies: Focus solely on design.
Pure-Play Foundries: Specialize only in fabrication. (Like originally TSMC I think).



The RTL-to-GDSII Flow (Simplified)
1. Synthesis

Converts RTL to a gate-level netlist using cells from a Standard Cell Library (SCL).
Each standard cell includes multiple "views" (e.g., timing, layout, logic) for different stages of the flow.
2. Floorplanning & Power Planning

Chip Floorplanning: Divides the die into logical regions and places I/O pads.
Macro Floorplanning: Plans macro blocks, sets pin positions, defines row structures.
Power Planning: Ensures minimal IR drop by laying out power stripes and pins efficiently.
3. Placement

Positions standard cells on the silicon.
Global Placement: Optimizes cell placement holistically.
Detailed Placement: Fine-tunes the layout based on global output.
4. Clock Tree Synthesis (CTS)

Distributes the clock signal to all sequential elements (flip-flops, registers).
Ensures minimal clock skew using tree-like clock structures.
5. Routing

Connects placed cells using the available metal layers defined in the PDK.
Global Routing: Generates high-level wire guides.
Detailed Routing: Follows the guides to route each net precisely.
6. Signoff

Final verification to ensure manufacturability and correctness:

Physical Verification:
DRC (Design Rule Check): Verifies layout follows PDK rules.
LVS (Layout vs. Schematic): Confirms layout matches intended schematic.
Timing Analysis:
STA (Static Timing Analysis): Verifies all timing paths meet constraints and the design runs reliably.


<img width="959" height="588" alt="Screenshot 2025-07-15 at 10 04 55 PM" src="https://github.com/user-attachments/assets/1e41fade-ab4b-44fb-99f0-6fd0f9de71d1" />
<img width="830" height="527" alt="Screenshot 2025-07-15 at 10 01 21 PM" src="https://github.com/user-attachments/assets/3b1da225-34f7-478c-af86-aca9804ecbce" />
