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
```
#### Load generated floorplan def in magic tool and explore the floorplan.

```
# Change directory to path containing generated floorplan def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/floorplan/

# Command to load the floorplan def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &
```
> Review Floorplan in Magic
![image](https://github.com/user-attachments/assets/b529ddb7-c499-4f75-b3fc-9c696fa0d577)
#### Instruction for using Magic

```markdown
# Design Alignment Instructions

## Centering the Design

1. Press `S` to select the entire design.
2. Press `V` to vertically align it to the middle of the screen.

## Zooming In on a Specific Area

1. Left-click and drag to select the desired region.
2. Right-click to bring up the context menu.
3. Press `Z` to zoom in on the selected area.

## Getting Details of a Cell

1. Move your cursor to the cell of interest.
2. Press `S` to select the cell.
3. In the `tkcon` window, enter the command `what` to display cell details.
```
![image](https://github.com/user-attachments/assets/859db23d-01d1-4bc0-8043-85b9b44508fb)

> Standard cells kept in the lower part of design
![image](https://github.com/user-attachments/assets/d5a74429-d228-4cb4-a883-59bf6c0b28da)

### Placement in VLSI Design

Placement is a critical step in VLSI (Very Large Scale Integration) design, determining the physical positions of standard cells or logic elements within a chip or block.
```
% run_placement
```
![image](https://github.com/user-attachments/assets/ba0c9546-a5d5-464f-b968-1fbb9ff3c466)


```
# Change directory to path containing generated floorplan def
cd Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/17-03_12-06/results/placement/

# Command to load the floorplan def in magic tool
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```

#### Global Placement

- **Objective:** Assign general locations to movable objects (cells).
- **Flexibility:** Some overlaps between placed objects are allowed during this stage.
- **Goal:** Achieve a rough layout that meets area constraints.

#### Detailed Placement

- **Objective:** Refine the object locations obtained from global placement.
- **Constraints:** Enforce non-overlapping constraints and ensure cells are placed on legal cell sites.
- **Impact:** The quality of detailed placement has a significant effect on subsequent routing stages.

> Result of placement
![image](https://github.com/user-attachments/assets/7c6180a3-b21d-460f-8776-0546c9a06e7b)

### Day 3

#### IO Placer Concept
Io Placer has usually 4 types. We can change its type by changing the variable in the floorplan.tcl file in configuration directory.
![image](https://github.com/user-attachments/assets/c20935d2-8000-4ed4-b5f9-4d2478f2b0a2)
![image](https://github.com/user-attachments/assets/215ccf71-c290-477a-98a8-b545798a7af0)
> Here the IO Pin arrangement is changed now
![image](https://github.com/user-attachments/assets/f80fc80a-fde5-4d50-ac51-9f4ded08ccad)
> Previous floorplan with variable set to 1 by default

#### SPICE Deck Creation-
![image](https://github.com/user-attachments/assets/19b455ee-810e-4abd-9129-1359744a6482)
- Component COnnectivity
- Component Values
- Component Nodes
- Name Nodes

The order in the syntax is as follows-
`<component_name> <drain> <gate> <source> <substrate> W=<width> L=<length>`
![image](https://github.com/user-attachments/assets/a6fe70a4-ba5a-4ed0-b9b7-21a6ddb4792e)
Here the width and length were same for NMOS and PMOS.
But in general the PMOS ratio of W/L should be `n` times the NMOS ratio. The comparison explains the DC out vs in characterstics of the MOSFET.
> We can see that as the PMOS ratio is 2.5 times NMOS now the curve is shifted towards middle rather than previous is left. The curve is at 1.25 i.e. centre hence it is more preferable than First one. To find switching threshold Vm plot a line with x=y and find the intersection point with the curve.
![Untitled design (13)](https://github.com/user-attachments/assets/b5ea6f48-4e5d-44d4-8b96-f3bd5c00f140)

Dynamic Analysis of CMOS Inverter- Transient analysis where we give input pulse as shown and tran command
![image](https://github.com/user-attachments/assets/564fae49-258b-4738-874b-29c49d31ba87)

#### Git clone the vsdstdcelldesign repository
```
# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Clone the repository with custom inverter design
git clone https://github.com/nickson-jose/vsdstdcelldesign

# Change into repository directory
cd vsdstdcelldesign

# Copy magic tech file to the repo directory for easy access
cp /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech 

# Check contents whether everything is present
ls

# Command to open custom inverter layout in magic
magic -T sky130A.tech sky130_inv.mag &
```
> CMOS Inverted Layout
![image](https://github.com/user-attachments/assets/150965e8-af8a-48a3-9f2d-273f5b4ac32e)

#### Inception of Layout and CMOS Fabrication Process
##### 16 Mask CMOS Process
1. Selecting a substrate
       - P-type selected and substrate doping should be less than well doping
       - ![image](https://github.com/user-attachments/assets/b4b1fc4f-85fd-45f8-aa81-7ac42a4882b1)

2. Creating active region for transistors
   - Add SiO2 for insulator, Si3N4 and photoresist
   - Create Mask 1
   - ![image](https://github.com/user-attachments/assets/b70ee72e-e7b2-437f-b33a-88b01da0b347)
   - Now it is washed out in developing solution to remove photoresist
   - ![image](https://github.com/user-attachments/assets/b89e8ab3-2099-407d-a3b7-0b87dbd294dd)
   - Now it is placed in oxidation furnace at about 1100 degree celsius for 4-6 hours
   - ![image](https://github.com/user-attachments/assets/2ff36c31-dc01-48ae-b856-d6aeb530a3ea)
   - Next Si3N4 is etched off using Phosphoric acid

3. N-well and P-well creation
    - Same mask process is used to isolate a part and Boron(P-type element) is used to create a P-well by Ion Implantation process
    - ![image](https://github.com/user-attachments/assets/5e83e910-9e3a-4dad-bc24-39f06918d4bd)
    - Similar process is used to create N-well using Phosphoros(N-type) element.
    - Next it is put into driving furnace and the wells are driven down. It is called twin tub process.
    - ![image](https://github.com/user-attachments/assets/946c3b85-b720-4f2c-9281-031817a84393)
      
4. Formation of gate
   - Gate is one of the main element because it controls the threshold voltage of a transistor
   - Similar process is used to form n and p layer using Boron and Arsenic at low voltage
   - ![image](https://github.com/user-attachments/assets/388d9932-1d3b-41ca-a60d-22d6cb970dd8)
   - ![image](https://github.com/user-attachments/assets/389e51a0-7829-4e54-ae83-7a89d42e2945)
   - Now here we have created Low Resistance gate by adding additional impurities in the doping process
   - ![image](https://github.com/user-attachments/assets/040de682-a695-41e3-b858-cf4177e5e02f)

5. Lighly Doped Drain(LDD) Formation
   - Here we create certain structure of source and drain to get high performance
   - Here P+/N+ are for PMOS and NMOS, P-/N- are for LDD and N/P layers are wells
   - ![image](https://github.com/user-attachments/assets/2f531057-c649-47e6-9050-28760671c03d)
   - ![image](https://github.com/user-attachments/assets/e9f14c1f-cfe2-455d-a1c1-3d38e0ca5617)
   - ![image](https://github.com/user-attachments/assets/6ed6d55d-c844-4465-ac0e-0a2df677074f)
   - N-implant and P- type is created now
   - ![image](https://github.com/user-attachments/assets/03572521-059a-446a-a037-783ef7b1f765)
   - Plasma anisotropic etching is done now for creating side wall spacers
   - ![image](https://github.com/user-attachments/assets/7c0858db-05df-4ef9-82a5-30e2230e10ea)
   - ![image](https://github.com/user-attachments/assets/483b0284-58fd-45e6-9702-23beea20d3d4)
   
6. Source and Drain Formation
   - Add a thin layer of screen osxide to avoid effect of channeling. During implantation if the vector velocity of ion matches crystalline structure of P-type substrate, the ions mught do deep inside the substrate without getting blocked. We try to reduce randomization of ions.
   - ![image](https://github.com/user-attachments/assets/022ce320-c930-4e4e-95b6-55d421dd972a)
   - High temperature annealing is done now.
   - ![image](https://github.com/user-attachments/assets/b412ba00-ac48-4b06-bbe3-657e28c71197)

7. Steps to form contacts and interconnects(local)
   - Contacts are important because that is the only thing accessible to the user for controlling the electrical characterstics on PMOS/NMOS
   - Etch thin oxide in HF
   - Deposit Titanium through sputtering
   - ![image](https://github.com/user-attachments/assets/aa02fc48-3f51-48ac-b6aa-f63b89b44c18)
   - Low resistance contacts are made now- TiS2
   - ![image](https://github.com/user-attachments/assets/4fa58ec0-73c8-46ac-8595-09f1ec2339f5)
   - TiN for local connection
   - ![image](https://github.com/user-attachments/assets/46ecf6a4-bf29-4851-8661-d93d61c01f7a)
   - Mask process is used with Mask 11 here to form interconnects
   - ![image](https://github.com/user-attachments/assets/15f2d4ab-bef2-4359-8313-3ea19e6c2a96)
   
8. Higher Level Metal Formation
    - As the surface is non-planar it is not ideal to form metal contacts there
    - Deposit thick layer of SiO2 with P. Phosphoros acts as protection for mobile Sodium Ion. Boron is used to reduce the temperature of surface
    - ![image](https://github.com/user-attachments/assets/6afb7b97-3491-49de-84ba-318791f1944b)
    - ![image](https://github.com/user-attachments/assets/9318b515-b436-4a66-a11a-414d1b666ce5)
    - Repeat Mask process with Mask 12.
    - ![image](https://github.com/user-attachments/assets/710021af-13b0-4f69-8a0a-772e8adb6551)
    - Deposit TiN layer as it acts as good adhesive layer to SiO2
    - ![image](https://github.com/user-attachments/assets/6a015d26-3b95-4abf-848f-8e4923c168bc)
    - ![image](https://github.com/user-attachments/assets/d2e82b8d-5fe0-4097-98d5-95aba3bf9ca6)
    - ![image](https://github.com/user-attachments/assets/45b3590a-63f4-46e9-881e-6c913241484f)
    - Use Mask 14 to drill similar holes
    - ![image](https://github.com/user-attachments/assets/4183df44-e7d0-454c-9fde-abb4b38a95c1
    - Repeat similar steps to form layers
    - ![image](https://github.com/user-attachments/assets/8a40190b-f0eb-4122-9c04-49d29e35c2d1)
    - Final 16 Mask is used to drill contact holes.
    - ![image](https://github.com/user-attachments/assets/1e86651c-ffae-4136-aa6c-59aeba1ab1ac)


## Lab Continued

> Checking the layers
![image](https://github.com/user-attachments/assets/f77abae3-e9ad-458a-aa6c-5e9a482ccb71)

> Check if there is connection between Vdd and source of PMOS
![image](https://github.com/user-attachments/assets/2e593936-1631-4fc3-887e-7f37ed9e9698)

> Similarly check with Ground and NMOS also
![image](https://github.com/user-attachments/assets/25d89fa0-0784-48a0-8bc4-cb6184bcf3b0)

> Difference between a Layout and Abstract. Usually when we buy an IP from vendor we can only see the abstract as the vendor won't show his propritory logic.
![image](https://github.com/user-attachments/assets/47aceed4-5074-4cc6-9a39-14356e7060e6)

How do we know the logical function of this invertor?
-> For that we will frst extract to spice and then simulate it in ngspice

1. Open tkon window. write command `extract all`
2. Next type `ext2spice cthresh 0 rthresh 0`
3. And final `ext2spice`
4. Inside vsdstdcell directory do `ls -ltr` and see new spice file created
5. Do `vim sky130_inv.spice`

To make the connections proper in spice file check this diagram fro reference-
![image](https://github.com/user-attachments/assets/070d391c-1c39-42ee-a59e-9834ae81cbf4)

> Initial SPICE File
![image](https://github.com/user-attachments/assets/7e5a2073-bfda-487d-a619-71b98bf0e552)

> Final Edited SPICE File
![image](https://github.com/user-attachments/assets/e4d77d4c-aeda-4195-81f3-9cb6da938010)

> To launch ngspice enter command `ngspice sky130_inv.spice`
![image](https://github.com/user-attachments/assets/d3600e76-5fce-4f1a-9c13-eeb5edcc9534)

> Enter command `plot y vs time a` to check the graph. We have adjusted the capacitor values to reduce spikes
![image](https://github.com/user-attachments/assets/7361cafc-a184-4289-8492-50dc99567ee5)

#### Parameters for Characterization

1. Rise Time
    - The time taken for the output waveform to transition from 20% to 80% of its maximum value. (x1-x0)
    - x0 = 2.18047e-09, y0 = 0.66
    - x1 = 2.2413e-09, y1 = 2.64
    - Rise time= 2.24-2.18 = 0.04ns
2. Fall Time
    - The time taken for the output waveform to fall from 80% to 20% of its minimum value. (x1-x0)
    - x0 = 4.0522e-09, y0 = 2.64
    - x1 = 4.09398e-09, y0 = 0.660377
    - Fall Time = 4.093-4.052 = 0.041ns
3. Propagation Delay
    - The time taken for a 50% transition at the output (0 to 1) corresponding to a 50% transition at the input (1 to 0).
    - x0 = 2.15012e-09, y0 = 1.65005
    - x1 = 2.20807e-09, y0 = 1.65
    - Propagation Delay= 2.20-2.15 = 0.05ns
4. Cell Fall Delay
    - The time taken for a 50% transition at the output (1 to 0) corresponding to a 50% transition at the input (0 to 1).
    - x0 = 4.05e-09, y0 = 1.65004
    - x1 = 4.07615e-09, y0 = 1.65
    - Cell Fall Delay = 4.07 - 4.05 = 0.02ns


#### Find problem in the DRC section of the old magic tech file for the skywater process and fix them
1. Change to main directory- `cd`
2. Download the Lab files- `wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz`
3. Extract the compressed file- `tar xfz drc_tests.tgz`
4. Go to lab folder- `cd drc_tests`
5. Check the files present in the folder- `ls -ltr`
6. View magiccrc file- `vim .magicrc`
7. Open magic tool by command- `magic -d XR &`

> Screenshot of magicrc file-
![image](https://github.com/user-attachments/assets/a4baa5a7-3100-4a9f-9ba8-3ee7f70f196b)

> check for DRC violation, Command- ```drc why ```
![image](https://github.com/user-attachments/assets/36c0128f-d66d-42fe-8937-d5a780ea7b33)

> Load the poly.mag file. Give command inside tckon window ```load poly ```
![image](https://github.com/user-attachments/assets/5621bc35-ad1a-460a-b6a1-97c94030210d)

> Fix the commands inside the sky130 using vim editor tech file. We choose allpolynonres as it is the most suitable.
![image](https://github.com/user-attachments/assets/3f3d043e-f2f7-4fa7-92d0-b267d642ada7)
![image](https://github.com/user-attachments/assets/c16ed026-f463-4f04-af2f-ff4219cf341d)
> We were having a width of only 0.30um which is violating the defined poly.9 rule
![image](https://github.com/user-attachments/assets/034de343-2a38-45d5-b709-721079ab36d8)

Load the tech file in tckon window- ```tech load sky130A.tech ```
Check the drc error by selecting the area- ``` drc check ```
Check for more error- ``` drc why ```

> Before changes
![image](https://github.com/user-attachments/assets/bc9e7e48-9d97-45d8-b97b-42b9613e8abc)
> After changes
![image](https://github.com/user-attachments/assets/a0863850-ecd6-47d3-a67a-0c37d8d7beb3)

Now load nwell mag, Command- ``` load nwell.mag```
Type- ```cif ostyle drc``` in tckon window
![image](https://github.com/user-attachments/assets/cf921357-5163-4f4d-9d23-f8e383d6cfa9)
Type - ``` cif see dnwell_shrink``` to see the area
![image](https://github.com/user-attachments/assets/2333416d-0977-4be3-98c0-4a068c5d7ae0)
Type - ```feed clear``` to clear the area
See the missing area by- ```cif see nwell_missing```
![image](https://github.com/user-attachments/assets/44c4ca57-058d-4711-8535-7843c02da049)
Clear the feed again
![image](https://github.com/user-attachments/assets/306f6632-608c-48fc-a03e-f0c01ebd2efc)

Make the changes in tech file
![image](https://github.com/user-attachments/assets/3b7e28c8-66cc-4070-af9f-c1f8695b2993)

Check again using given commands in tckon window. We get error again because the whole nwell is untapped
![image](https://github.com/user-attachments/assets/2be47601-ff2a-459c-a515-fa5d7395d515)

Once we put nsubstratecontact. The error is resolved
![image](https://github.com/user-attachments/assets/01fb3a67-d70b-44f1-a025-27d1fb77f2d9)

By adding nsubstratecontact, that error is resolved.
![image](https://github.com/user-attachments/assets/0310634d-5759-4ec1-90ac-c70e102030c7)


### Day 4 - Pre-layout timing analysis and importance of good clock tree

- Open this design again under vsdstdcelldesign- ```magic -T sky130A.tech sky130_inv.mag```
- Tracks file - ```vsduser@vsdsquadron:~/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/openlane/sky130_fd_sc_hd$ less tracks.info``` The first number is offset and second is pitch in the file for tracks with various layers.
- ![image](https://github.com/user-attachments/assets/e69d0f4f-8566-44d9-bc61-c7d9008db7ff)
- Add grid to the layout- ```grid 0.46um 0.34um 0.23um 0.17um```
- ![image](https://github.com/user-attachments/assets/3a1faf85-f63b-4d4c-97e4-9ee7330583ed)
- Condition checked-
- ![image](https://github.com/user-attachments/assets/df3f99b0-9436-46a4-b542-437c71f45f20)
- Width of std cell should be odd multiple of x-pitch- 0.46*3= 1.380um. Verified
- ![image](https://github.com/user-attachments/assets/7ea5ead2-cc00-4203-b726-8005ab0c4526)
- Save it in tckon window- ```save sky130_vsdinv.mag```
- When ports are created on layers they are created as PIN in the lef file.
- Make lef file ```lef write```
- ![image](https://github.com/user-attachments/assets/a307869b-6056-4c4d-8759-d5118548c67a)

Copy lef file to picorv32 src folder- ```cp sky130_vsdinv.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src``` from vsdstdcelldesign directory

Make the changes in config.tcl file inside picorv32-
```
# Design
set ::env(DESIGN_NAME) "picorv32a"

set ::env(VERILOG_FILES) "./designs/picorv32a/src/picorv32a.v"
set ::env(SDC_FILE) "./designs/picorv32a/src/picorv32a.sdc"

set ::env(CLOCK_PERIOD) "5.000"
set ::env(CLOCK_PORT) "clk"


set ::env(CLOCK_NET) $::env(CLOCK_PORT)

set ::env(FP_CORE_UTIL) 65
set ::env(FP_IO_VMETAL) 4
set ::env(FP_IO_HMETAL) 3


set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]


set filename $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/$::env(PDK)_$::env(STD_CELL_LIBRARY)_config.tcl
if { [file exists $filename] == 1} {
        source $filename
}
```

*Now start the openlane in docker with interactive mode. Refer Day 1 notes for starting it.
For starting the design form previos one and not to create a new one, command-
```
./flow.tcl -interactive

package require openlane 

running a specific design which in our case is 'picorv32a'
prep -design picorv32a -tag <folder name which you want to continue> -overwrite

set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```
Our inverter cell in used-
![image](https://github.com/user-attachments/assets/701d978b-bec8-4a4e-9d3f-8a12dd5ae6ce)

Synthesis Successfull- ![image](https://github.com/user-attachments/assets/12917ee0-5ebd-45a1-a02e-ca6961ec7247)

Note down current values to check after improving the design
![image](https://github.com/user-attachments/assets/bbdf6c94-7c34-4333-825a-9ad322267301)
![image](https://github.com/user-attachments/assets/916a92e9-a6b7-4710-88cb-dc2657730b16)

#### Power aware CTS
Is it possible to change the buffer with the gates directly?
![image](https://github.com/user-attachments/assets/c77cf351-fb7d-427c-bbc0-cacaf7d9a3ce)
![image](https://github.com/user-attachments/assets/f98e1212-c772-4c83-a358-0b5502c9bccc)
![image](https://github.com/user-attachments/assets/6d1d6cb2-d0b5-49fc-bfa6-daa497f7ab11)

![image](https://github.com/user-attachments/assets/ed10053f-8bd4-4221-abcc-46c049ed37ee)

#### Lab continued to fix slack
Commands to open OpenLane
```
# Change directory to openlane flow directory
cd Desktop/work/tools/openlane_working_dir/openlane

# alias docker='docker run -it -v $(pwd):/openLANE_flow -v $PDK_ROOT:$PDK_ROOT -e PDK_ROOT=$PDK_ROOT -u $(id -u $USER):$(id -g $USER) efabless/openlane:v0.21'
# Since we have aliased the long command to 'docker' we can invoke the OpenLANE flow docker sub-system by just running this command
docker
```
```
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```

![image](https://github.com/user-attachments/assets/eccdb84f-5995-47e7-acb2-5b1992428675)

To solve the above error- Execute these commands separately
```
init_floorplan
place_io
tap_decap_or
```
![image](https://github.com/user-attachments/assets/de860919-1797-4173-b038-298cd5634975)
Now run command ```run_placement```
![image](https://github.com/user-attachments/assets/6e3bfb26-8b34-4d83-97a5-19599a421d4f)

Run magic inside lacement directory inside results on picorv32a
![image](https://github.com/user-attachments/assets/4b2dd7f4-4a8c-484f-9d2c-a68c250bd37d)
```
magic -T /home/vsduser/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &
```
VSD_INV used here-
![image](https://github.com/user-attachments/assets/5d149c48-05f0-4992-90e8-5bdeb78f8497)

#### Time Analysis with ideal clocks
Combinational Delay= Clock period- Setup Time
![image](https://github.com/user-attachments/assets/68ad772c-60a4-4e45-9646-481c2c9091bd)
![image](https://github.com/user-attachments/assets/3e659454-45ff-4df0-a3a7-ab0ed9bd5e6e)
![image](https://github.com/user-attachments/assets/cf5d6f8b-bc4e-4b69-a069-541dabff4e12)
![image](https://github.com/user-attachments/assets/d17ca74e-1f32-4f94-bdd6-8273555bf31f)

#### Do Post-Synthesis timing analysis with OpenSTA tool.
Start the docker and commands-
```
# Now that we have entered the OpenLANE flow contained docker sub-system we can invoke the OpenLANE flow in the Interactive mode using the following command
./flow.tcl -interactive

# Now that OpenLANE flow is open we have to input the required packages for proper functionality of the OpenLANE flow
package require openlane 0.9

# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```
![image](https://github.com/user-attachments/assets/7f85ee12-5f10-4608-8728-faf96b8ecde5)
Write this code in the file named- `pre_sta.conf` for STA analysis in `openlane` directory

```
set cmd units -time ns -capcitance pF -current mA -voltage V -resistance kOhm -distance um
read liberty -max /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib
read liberty -max /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib
read liberty -max /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/runs/22-07_14-48/results/synthesis/picorv32a.synthes
is.v
link_design picorv32a
read sdc /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src/base.sdc
report_check -path_delay min_max -delay min_max -fields {slew trans new cap input_pin}
report_tns
report_wns
```
my_base.sdc-
```
set ::env(CLOCK_PORT) clk
set ::env(CLOCK_PERIOD) 24.73
#set ::env(SYNTH_DRIVING_CELL) sky130_vsdinv
set ::env(SYNTH_DRIVING_CELL) sky130_fd_sc_hd__inv_8
set ::env(SYNTH_DRIVING_CELL_PIN) Y
set ::env(SYNTH_CAP_LOAD) 17.653
set ::env(IO_PCT) 0.2
set ::env(SYNTH_MAX_FANOUT) 6

create_clock [get_ports $::env(CLOCK_PORT)]  -name $::env(CLOCK_PORT)  -period $::env(CLOCK_PERIOD)
set input_delay_value [expr $::env(CLOCK_PERIOD) * $::env(IO_PCT)]
set output_delay_value [expr $::env(CLOCK_PERIOD) * $::env(IO_PCT)]
puts "\[INFO\]: Setting output delay to: $output_delay_value"
puts "\[INFO\]: Setting input delay to: $input_delay_value"

set_max_fanout $::env(SYNTH_MAX_FANOUT) [current_design]

set clk_indx [lsearch [all_inputs] [get_port $::env(CLOCK_PORT)]]
#set rst_indx [lsearch [all_inputs] [get_port resetn]]
set all_inputs_wo_clk [lreplace [all_inputs] $clk_indx $clk_indx]
#set all_inputs_wo_clk_rst [lreplace $all_inputs_wo_clk $rst_indx $rst_indx]
set all_inputs_wo_clk_rst $all_inputs_wo_clk

# correct resetn
set_input_delay $input_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] $all_inputs_wo_clk_rst
#set_input_delay 0.0 -clock [get_clocks $::env(CLOCK_PORT)] {resetn}
set_output_delay $output_delay_value  -clock [get_clocks $::env(CLOCK_PORT)] [all_outputs]

# TODO set this as parameter
set_driving_cell -lib_cell $::env(SYNTH_DRIVING_CELL) -pin $::env(SYNTH_DRIVING_CELL_PIN) [all_inputs]
set cap_load [expr $::env(SYNTH_CAP_LOAD) / 1000.0]
puts "\[INFO\]: Setting load to: $cap_load"
set_load  $cap_load [all_outputs]
```

Run the sta command-
```
# Change directory to openlane
cd Desktop/work/tools/openlane_working_dir/openlane

# Command to invoke OpenSTA tool with script
sta pre_sta.conf
```
![image](https://github.com/user-attachments/assets/dd011163-1dad-4bf2-87ed-158e93879a3e)

More is the input skew more is delay and high is capacitance more is delay.
More fanout is causing more delay we can add parameter to reduce fanout and do synthesis again
Commands-
```
# Now the OpenLANE flow is ready to run any design and initially we have to prep the design creating some necessary files and directories for running a specific design which in our case is 'picorv32a'
prep -design picorv32a -tag 25-03_18-52 -overwrite

# Adiitional commands to include newly added lef to openlane flow
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Command to set new value for SYNTH_MAX_FANOUT
set ::env(SYNTH_MAX_FANOUT) 4

# Command to display current value of variable SYNTH_DRIVING_CELL to check whether it's the proper cell or not
echo $::env(SYNTH_DRIVING_CELL)

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis
```
> High fan out
![image](https://github.com/user-attachments/assets/d412b9df-4033-48c8-9bf1-2030b6b431ad)

Commands to  perform analysis and optimize timing by replacing with OR gate of drive strength 5

```
# Reports all the connections to a net
report_net -connections _11643_

# Checking command syntax
help replace_cell

# Replacing cell
replace_cell _13690_ sky130_fd_sc_hd__or2_2

# Generating custom timing report
report_checks -fields {net cap slew input_pins} -digits 4
```
![image](https://github.com/user-attachments/assets/2e97665f-8464-473a-bb9b-8883d6f03415)

#### Clock Tree Synthesis(Tool- TritonCTS (OpenRoad))
![image](https://github.com/user-attachments/assets/5ab39df0-d6b7-4796-888d-e9eefe3f6106)
Mid point is calculated and then the clock is divided
![image](https://github.com/user-attachments/assets/64705858-d10d-4759-80e5-f15e89891984)
When step signal is given it has slope due to RC networks
![image](https://github.com/user-attachments/assets/1fb93707-4d74-4925-8a5f-9fa2edeaf15e)
Hence, repeaters are placed in the network.

![image](https://github.com/user-attachments/assets/2d6d36bd-7406-4fdf-9837-e1da03ae0692)
![image](https://github.com/user-attachments/assets/cb195f8f-7f47-4c33-80bb-1f4cff986e32)

Commands-
```
# Now once again we have to prep design so as to update variables
prep -design picorv32a -tag <directory> -overwrite

# Addiitional commands to include newly added lef to openlane flow merged.lef
set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

# Command to set new value for SYNTH_STRATEGY
set ::env(SYNTH_STRATEGY) "DELAY 3"

# Command to set new value for SYNTH_SIZING
set ::env(SYNTH_SIZING) 1

# Now that the design is prepped and ready, we can run synthesis using following command
run_synthesis

# Follwing commands are alltogather sourced in "run_floorplan" command
init_floorplan
place_io
tap_decap_or

# Now we are ready to run placement
run_placement

# Incase getting error
unset ::env(LIB_CTS)

# With placement done we are now ready to run CTS
run_cts
```
![image](https://github.com/user-attachments/assets/cc1848fe-47b3-46de-8529-62e2ad03a33e)

#### Real Time clocks
- ![image](https://github.com/user-attachments/assets/84b1bf84-c8a4-4450-ae73-00d390a5d57f)
- ![image](https://github.com/user-attachments/assets/b3f4e1cc-fac3-44d2-8589-75213e045a3c)
- ![image](https://github.com/user-attachments/assets/6ee2c961-11fe-4ca3-9af7-53252f612d16)
- ![image](https://github.com/user-attachments/assets/6dc65e10-be2b-4569-be5e-22928c47c788)

#### Analyze timing analysis using OpenSTA (openroad)
````
# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/11-07_20-02/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/11-07_20-02/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/11-07_20-02/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Check syntax of 'report_checks' command
help report_checks

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Exit to OpenLANE flow
exit
````

![image](https://github.com/user-attachments/assets/21f5c6a9-ebd9-4ab8-920a-acf1f6ed6a4d)

##### OpenLANE flow to do OpenROAD timing analysis after changing `CTS_CLK_BUFFER_LIST`

```
# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Removing 'sky130_fd_sc_hd__clkbuf_1' from the list
set ::env(CTS_CLK_BUFFER_LIST) [lreplace $::env(CTS_CLK_BUFFER_LIST) 0 0]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Checking current value of 'CURRENT_DEF'
echo $::env(CURRENT_DEF)

# Setting def as placement def
set ::env(CURRENT_DEF) /openLANE_flow/designs/picorv32a/runs/11-07_20-02/results/placement/picorv32a.placement.def

# Run CTS again
run_cts

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Command to run OpenROAD tool
openroad

# Reading lef file
read_lef /openLANE_flow/designs/picorv32a/runs/11-07_20-02/tmp/merged.lef

# Reading def file
read_def /openLANE_flow/designs/picorv32a/runs/11-07_20-02/results/cts/picorv32a.cts.def

# Creating an OpenROAD database to work with
write_db pico_cts1.db

# Loading the created database in OpenROAD
read_db pico_cts.db

# Read netlist post CTS
read_verilog /openLANE_flow/designs/picorv32a/runs/11-07_20-02/results/synthesis/picorv32a.synthesis_cts.v

# Read library for design
read_liberty $::env(LIB_SYNTH_COMPLETE)

# Link design and library
link_design picorv32a

# Read in the custom sdc we created
read_sdc /openLANE_flow/designs/picorv32a/src/my_base.sdc

# Setting all cloks as propagated clocks
set_propagated_clock [all_clocks]

# Generating custom timing report
report_checks -path_delay min_max -fields {slew trans net cap input_pins} -format full_clock_expanded -digits 4

# Report hold skew
report_clock_skew -hold

# Report setup skew
report_clock_skew -setup

# Exit to OpenLANE flow
exit

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)

# Inserting 'sky130_fd_sc_hd__clkbuf_1' to first index of list
set ::env(CTS_CLK_BUFFER_LIST) [linsert $::env(CTS_CLK_BUFFER_LIST) 0 sky130_fd_sc_hd__clkbuf_1]

# Checking current value of 'CTS_CLK_BUFFER_LIST'
echo $::env(CTS_CLK_BUFFER_LIST)
```































 










   
   









































 












