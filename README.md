# Digital VLSI SoC Design


## IC Design Components
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/c01d8274-2327-4970-8ce3-b7ef0bddb6cc)

## How a chip communicates between GPIO and other peripherals
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/9a4d5a84-3e9e-4bf1-b89e-820baa92519c)

- **IO Pads**: The interface terminals on a chip used for input and output signals to connect with external circuits.
- **Die**: The small block of semiconducting material on which a given functional circuit is fabricated.
- **Core**: The central part of the chip that contains the primary functional logic and processing units.
- **IP (Intellectual Property)**: Pre-designed and pre-verified blocks or components used in chip design to accelerate development and ensure reliability.
- **Macros**: Larger pre-designed and reusable functional units or blocks within a chip, such as memories or standard cells.

## Introduction to RISC-V

**ISA**: Instruction Set Architecture (ISA) acts as the interface between software and hardware, enabling communication with the computer. Typically, we write programs in high-level languages like C or Java, which the computer cannot directly understand. This is where ISA plays a crucial role. It translates these high-level codes from assembly language into binary, a format that machines can process. The most recent development in this field is the RISC-V ISA, which provides an open standard for implementing flexible and efficient instruction sets. RISC-V is notable for its simplicity and modularity, making it highly adaptable for various computing needs, from embedded systems to supercomputers.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/c2d4c685-936a-48d4-81bd-be9780c5b50d)

## Software Application to Hardware

1. **Software Applications**: Programs designed to perform specific tasks for users, such as word processing or web browsing.
2. **Operating System (OS)**: System software that manages computer hardware, software resources, and provides common services for application programs. Translates to C/C++ etc.
3. **Compiler**: A program that translates high-level source code written in programming languages into machine instructions. Compiler to (.exe) files.
4. **Assembler**: A tool that converts assembly language code into machine code, which can be executed by the computer's CPU. COnverts to binary 0s and 1s.
5. **Hardware**: The physical components of a computer system, including the CPU, memory, and input/output devices. RISC-V CPU
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/89bf67c6-997b-4e3e-aa91-e1e2864d27fa)


> Here we design the architecture in RTL Hardware for instructions and synthesize it. Next it is converted to gate level design and hardware is made.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/d3703455-9a6f-42f7-8b60-93a3d4c42673)

## Introduction to components of OpenSource Digital ASIC Design
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/23b7fcb7-c2b6-41f1-bfea-fff4cdca391d)
### 1. RTL Design
**Resources: GitHub, LibreCores**

RTL (Register Transfer Level) design involves defining digital circuits using HDLs like Verilog or VHDL. Open source repositories on GitHub and LibreCores offer numerous reusable RTL design modules, accelerating custom digital design development.

### 2. EDA Tools
**Tools: OpenLane, OpenROAD**

Open source EDA tools like OpenLane and OpenROAD are essential for digital ASIC design. OpenLane provides an end-to-end flow for synthesis, placement, and routing, while OpenROAD automates physical design, ensuring high-quality, manufacturable layouts.

### 3. PDK
**Example: SkyWater 130nm PDK**

The SkyWater 130nm PDK, developed with Google, is an open source Process Design Kit offering detailed process information and verified standard cell libraries. It enables affordable and accessible silicon-proven design for academic and community projects.

## RTL to GDSII Flow
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/7942c14c-d361-43e0-a89c-44b006abe6ff)

### 1. Synthesis
Transform RTL code into a gate-level netlist using a synthesis tool like Yosys. This process involves logic optimization and technology mapping.

### 2. Floor Planning
Define the chip's layout, including the placement of key blocks and IO pins. Create power and ground planes to ensure stable power distribution.

### 3. Power Planning
Design the power distribution network, ensuring adequate power delivery to all parts of the chip while minimizing IR drop and electromigration issues.

### 4. Placement
Place standard cells on the chip layout according to the netlist. Optimize cell placement to minimize wire length and improve performance.

### 5. Clock Tree Synthesis (CTS)
Create a balanced clock distribution network to ensure that clock signals reach all sequential elements simultaneously, minimizing clock skew.

### 6. Routing
Connect all the placed cells and IO pins with metal wires. Use a global router followed by a detailed router to optimize wire length and reduce congestion.

### 7. Sign-Off
Perform final verification steps, including Design Rule Checking (DRC), Layout Versus Schematic (LVS) checking, and timing analysis, to ensure the design meets all specifications and is ready for fabrication.

## OpenLane ASIC Flow
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/b27ef6c7-fb80-439c-8797-175c9a695fe7)
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/6f2fabce-cd0e-4aff-b7b1-1435a0bbfa37)
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/a3e6498e-858c-4a63-b34a-6f12798bab53)
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/495023cc-a3b4-43f5-9fa3-0b0d9d634374)

## Day 1 Lab
### Introduction to terminal commands
- ls -ltr : Show all files in chronological order in the current folder
- clear : Clears the terminal screen
- pwd : Tells current working directory
- cd : Change directories
> Current working Directory for Projects
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/d2419a19-8d95-4dc8-8c66-37a2ac9ecba2)

Initiate the bash terminal by command-

```
docker
```













