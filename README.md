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

Set Up the Environment for Openlane
1. **Initiate the bash terminal with the command:**

    ```bash
    vsduser@vsdsquadron:~/Desktop/work/tools/openlane_working_dir/openlane$ docker
    ```

2. **Run interactive mode:**

    ```bash
    bash-4.2$ ./flow.tcl -interactive
    ```

3. **Import packages for OpenLane:**

    ```tcl
    % package require openlane 0.9
    ```
Start the Design
## Step 1 - To prepare the design
    prep -design picorv32a
>Design Preparation Done
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/a1a3168e-a9ca-47a8-80b5-2b95ac0bb9e4)

After preparation is finished, a new directory named with the current date will be created within the “runs” folder. This directory will contain all the essential subdirectories for storing results, reports, and other pertinent data.
>Runs folder will be created with current date
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/de5ab244-664a-47ec-8f00-3fb21b5e301d)

## Step 2- Run synthesis( Uses yosys and abc)
    % run_synthesis
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/87654604-7460-4c91-ab26-acd5015d89c7)

## Step 3 - Calculate the Flop Ratio
    Formula: Number of D-FlipFlops/ Total Number of Cells
    Here, 1613/14876 = 0.108 (10%)

![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/7314cfc7-b2b8-447c-876a-09e5d4ef115f)



## Good Floor Plan vs Bad Floor Plan and introduction to Library Cells

### Utilization Factor and Aspect Ratio
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/13c44392-ed22-4de6-80e8-6f7a7aea305c)
### Utilization Factor and Aspect Ratio

To determine the Utilization Factor and Aspect Ratio, it is essential to understand how the height and width of the core and die areas are defined.

#### Core Area

The core area of a chip is the region dedicated to placing all the logic cells and components. This is where the core logic of the chip resides. The dimensions of the core area (height and width) are primarily determined by the netlist of the design, which specifies the number of components needed to implement the logic.

#### Die Area

Surrounding the core area is the die area, which serves as the boundary for the chip. The die area is used for placing I/O (Input/Output) related components. The dimensions of the die area (height and width) are directly influenced by the dimensions of the core area. 

#### Utilization Factor

The Utilization Factor is a measure of how efficiently the core area is used for placing logic cells. It is calculated as the ratio of the area occupied by the logic cells to the total core area. A high Utilization Factor indicates that the core area is densely packed with logic cells, while a low Utilization Factor suggests that there is a lot of unused space within the core.

#### Aspect Ratio

The Aspect Ratio is the ratio of the height to the width of the core or die area. It is an important parameter in chip design as it affects the layout and routing of the components. A well-balanced aspect ratio ensures optimal performance and manufacturability of the chip.

> #### Consider the following Example-
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/b5253d89-c89e-4de6-b29a-b069b346002f)

> All the components are converted to their area specifications
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/c5d37b26-df3d-4a10-b6e3-67fd1f707062)

> A chip core and die
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/67c322a5-3bae-4e45-bc7e-de27e08b4f27)

>100% Utilization of the chip area
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/62275165-40e1-4d6b-8716-7bd0f7f71a61)

### Utilization Factor

The Utilization Factor is defined as the ratio of the core area occupied by the netlist to the total core area. For an effective floorplan, the Utilization Factor should never be '1'. When the Utilization Factor is '1', it indicates that there is no available space for adding additional logic, leading to a poor floorplan.

<p align="left">
Utilization Factor = <sup>Area occupied by netlist</sup>&frasl;<sub>Total core area</sub>
</p>

### Aspect Ratio

The Aspect Ratio is defined as the ratio of the height of the core to the width of the core. If the Aspect Ratio is '1', the core is square-shaped. If the Aspect Ratio is different from '1', the core is rectangular.

<p align="left">
Aspect Ratio = <sup>Height of the core</sup>&frasl;<sub>Width of the core</sub>
</p>

### Example Calculation

In this example, the calculations yield:

- **Utilization Factor**: 

<p align="left">
Utilization Factor = <sup>4 sq units</sup>&frasl;<sub>4 sq units</sub> = 1
</p>

- **Aspect Ratio**: 

<p align="left">
Aspect Ratio = <sup>2 units</sup>&frasl;<sub>2 units</sub> = 1
</p>

Here, the Utilization Factor is '1', indicating no additional space for extra logic, and the Aspect Ratio is '1', indicating that the core is square-shaped.

> 50% Utilization of the chip Area  
> ![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/bfc8fadd-b314-42d6-abc3-f5863d1ce963)

In this case:

<p align="left">
Utilization Factor = <sup>4 sq units</sup>&frasl;<sub>8 sq units</sub> = 0.5
</p>

<p align="left">
Aspect Ratio = <sup>2 units</sup>&frasl;<sub>4 units</sub> = 0.5
</p>

This indicates that the core is rectangular in shape.

#### Concept of Pre-placed Cells
Take a Combinational Circuit and separate it into 2 different parts to implement
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/6aba77f8-de0d-4309-8039-96d8d5d13e81)

Connect the design and extend the IO's. Convert it into Blackbox so we can't se what is implemented in the top netlist.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/3faa1dfb-bab5-4363-bf2f-a3a312dea84c)

Separate the 2 Blackbox. Advantage of doing it is that we can use the blackbox multiple times in the chip anywhere by instantiating it there.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/754beadb-2170-4d4f-bdec-8d974d06ed6d)

Designs of similar IPs are available to use in the design
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/5b708946-8061-4beb-9e98-3b86a50c8181)


#### Decoupling Capacitors
![Untitled design (12)](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/aeef5a7f-1f48-4e73-9d09-2a56ede59e5e)
When designing a chip, all blocks are placed within cells. Each cell receives a power supply voltage, denoted as `Vdd`. For logic levels, a logic 0 corresponds to a low voltage, while a logic 1 corresponds to a high voltage. 
As current travels through the wiring, which inherently has resistance, there is a resultant voltage drop, referred to as `Vdd'`. If `Vdd'` falls below the noise margin defined for the region, the signal can become undefined, potentially leading to dangerous situations where the signal may take any value.
To address this issue, decoupling capacitors are introduced into the design. These capacitors help maintain stable voltage levels and can discharge when necessary to ensure the voltage does not drop below the critical threshold.
> Here is how Decoupling capacitors are placed in the design. Once this is done the local communication of the blocks is taken care.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/c6bf4c02-c753-4a31-8777-1305f3cfa77c)

#### Power Planning
> Consider this design where all the blocks get power supply from a single source
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/7c24e866-255f-47e6-8840-57d964576a6a)

> Here, when all the capacitors are discharger together, there is a Ground Bounce which can lead to undefined state of the power.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/6b8d8621-9c27-4bfb-82d0-223e9396b581)

> Here when all the capacitors are to be charged the supply is not enough as it is from a single source, hence again there is a Voltage Drop which can lead to undefined state of voltage.
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/bfaa7fba-1fe3-44fc-89dc-8d89768dc094)

To solve this problem we introduce- Multiple power supply and ground. Hence the capacitors can take charge and discharge from nearest point
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/7e3e27c7-144b-460e-8aaf-95eef42fe1c1)

> The actual design would look like this-
![image](https://github.com/KaushalKulkarni2003/nasscom-vsd-openlane/assets/112880728/a993a3c2-70c4-49a8-8d2f-a0ff922883ae)

#### Floorplan
Run the command to do floorplan
```
% run_floorplan
```
Go to directory- Open the def file to see 
```
vsduser@vsdsquadron:~/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/11-07_20-02/results/floorplan$ less picorv32a.floorplan.def
```
![image](https://github.com/user-attachments/assets/7ec7876c-c810-4ec6-b42e-34b9a89c84d8)

According to floorplan def
```math
1000\ Unit\ Distance = 1\ Micron
```
```math
Die\ width\ in\ unit\ distance = 660685 - 0 = 660685
```
```math
Die\ height\ in\ unit\ distance = 671405 - 0 = 671405
```
```math
Distance\ in\ microns = \frac{Value\ in\ Unit\ Distance}{1000}
```
```math
Die\ width\ in\ microns = \frac{660685}{1000} = 660.685\ Microns
```
```math
Die\ height\ in\ microns = \frac{671405}{1000} = 671.405\ Microns
```
```math
Area\ of\ die\ in\ microns = 660.685 * 671.405 = 443587.212425\ Square\ Microns






 












