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





