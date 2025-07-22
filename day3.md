Magic Viewing Inverter:
<img width="641" height="431" alt="Screenshot 2025-07-20 at 9 00 02 PM" src="https://github.com/user-attachments/assets/4ef4bf87-cff2-4908-85bc-17c8018a356b" />


ˆO Placer Revision

The Input/Output (IO) placer within the physical design flow determines the placement of pins on the chip's permimeter.

Default IO Mode: By default, the IO placer in OpenLane uses a "random equidistant mode". This setting uniformly spaces all IO cells around the chip perimeter.

Changing IO Mode: To modify this behavior, you can set the FP_IO_MODE environment variable. For example:

'''set ::env(FP_IO_MODE) 2'''

After setting this variable, the floorplan step must be re-run for the change to take effect.

FP_IO_MODE 2 and Hungarian Matching: When FP_IO_MODE is set to 2, OpenLane utilizes a Hungarian Matching Algorithm for IO pin placement. This is a combinatorial optimization method that aims to find the optimal assignment of IO pins to available sites, potentially allowing for overlapping pin locations in the initial unconstrained placement to achieve better overall design metrics (e.g., shorter routing).

SPICE Deck Creation for CMOS Inverter

A SPICE deck is a fundamental text-based file used for circuit simulation. It comprehensively describes the circuit's components and their interconnections.

Components of a SPICE Deck:

Netlist: A detailed list of all circuit components (e.g., transistors, resistors, capacitors) and their connections (nodes).

TAP Points: Specifies the nodes from which outputs are to be observed.

Input Stimuli: Defines the voltage or current waveforms applied to the circuit inputs for simulation.

CMOS Inverter Transistor Sizing:

For a CMOS inverter, the width (W) and length (L) of both the PMOS and NMOS transistors are crucial parameters.

Symmetrical Switching: To achieve symmetrical rising and falling transition times (i.e., balanced drive strengths), the PMOS transistor is typically designed to be 2 to 3 times wider than the NMOS transistor. This compensates for the inherent difference in electron and hole mobilities in silicon, where electrons (NMOS) have higher mobility than holes (PMOS).

SPICE Simulations:
<img width="998" height="1018" alt="Screenshot 2025-07-20 at 9 28 12 PM" src="https://github.com/user-attachments/assets/ca48f2d4-1458-40c9-89dc-974d8749e99d" />

After load silicon.
<img width="1008" height="987" alt="Screenshot 2025-07-20 at 9 50 26 PM" src="https://github.com/user-attachments/assets/f64d42de-f570-4318-971d-956b2d514dbe" />

DRC Check failed (must edit file to change rule to pass).
<img width="503" height="185" alt="Screenshot 2025-07-20 at 10 00 25 PM" src="https://github.com/user-attachments/assets/dfff2df1-6aea-42d1-b952-d172f1f8a28f" />
