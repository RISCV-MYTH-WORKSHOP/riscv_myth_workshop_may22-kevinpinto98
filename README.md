
# RISC-V_MYTH_Workshop

This repository documents all the work that was done during the course of the [RISC-V MYTH Workshop](https://github.com/stevehoover/RISC-V_MYTH_Workshop).

## Workshop Schedule
* Day 1: Introduction to RISC-V ISA & GNU Compiler Toolchain
* Day 2: Introduction to ABI and Basic Verification Flow
* Day 3: Digital Logic with TL-Verilog and Makerchip
* Day 4: Basic RISC-V CPU Microarchitecture
* Day 5: Complete Pipelined RISC-V CPU Microarchitecture

## Day 1: Introduction to RISC-V ISA & GNU Compiler Toolchain
In Day 1, I have written a simple c-program to calculate the sum of numbers from 1 to a given integer (n). The program is as follows:

![Program](Images/sum1ton_c-program.png)

Kindly note that I have modified the program that was presented in the lab to take input n from the user.

* To compile the c code using the gcc compiler use
> `gcc <.c file>`

* To execute the compiled c code we use

> `./a.out`

* Command to compile C code using RISC-V compiler. The .o file is the executable we want to create.
> `% riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o <.o file> <.c file>`

* To see the assembly code of the C program we are trying to run
> `riscv64-unknown-elf-objdump -d <.o file we created during compilation>`

* To see less of the assembly code run
> `riscv64-unknown-elf-objdump -d <.o file we created during compilation> | less`

* A variation of `riscv64-unknown-elf-gcc` is given below. The .o file is the executable we want to create.
> `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o <.o file> <.c file>`

* To see output of c program after compilation using the riscv compiler use the following command
> `spike pk <.o file we created during compilation>`

* We can use spike an a debugger as well
> `spike -d pk <.o file we created during compilation>`

* To make the PC (Program Counter) run till a particular command we use
> `: until pc 0 [address_of_command]`


The images below depict the results obtained after running the commands described above:

![Program](Images/c_compilation.png)

![Program](Images/riscv_compilation_main.png)

![Program](Images/riscv_compilation_main_Ofast.png)

![Program](Images/riscv_compilation_without_less.png)

![Program](Images/riscv_compilation1.png)

![Program](Images/riscv_compilation8.png)

![Program](Images/spike_command_output.png)

![Program](Images/spike_debugger.png)

![Program](Images/spike_debugger_usage.png)

![Program](Images/spike_debugger_usage2.png)

![Program](Images/spike_debugger_usage3.png)

![Program](Images/spike_debugger_usage4.png)

![Program](Images/spike_debugger_usage.png)

In addition to the program summing up numbers from 1 to n we also looked at programs that determined the range of values that could be represented by signed and unsigned numbers.

Let's begin by looking at the case of Signed Numbers. The images below are of the code and the simulation results obtained during compilaton and execution of the said code.

![Program](Images/signed_numbers_program.png)

![Program](Images/signed_program_output.png)

![Program](Images/signed_highest_program.png)

![Program](Images/signed_highest_output.png)

In addition to Signed numbers we also implemented the code for the case of Unsigned numbers as well. The results are as shown below:

![Program](Images/unsignedhighest_program.png)

![Program](Images/unsignedhighest_output.png)

The images below are also for the case of Unsigned numbers but in here we are calculating the smallest number that can be represented using unsigned numbers.

![Program](Images/unsignedhighest_output_negative.png)

![Program](Images/unsignedhighest_program_negative.png)


## Day 2: Introdution to ABI and Basic Verification Flow

* Application Binary Interface (ABI) describes a low-level interface between two applications or between an application and an operating system. An example of what the ABI interface looks like can be seen in the image below.

![Program](Images/abi_interface.png)

* ABI enables application programs to directly access the registers of the RISC-V architecture through system calls.

* The RISC-V architecture has 32 registers. Their ABI names as well as their usage is mentioned in the table below.

![Program](Images/register_table.png)

In Day 2, we have written a c program for caculating the sum of number from 1 to 9 as well as it's assembly equivalent. The respective programs are shown side-by-side in the image below:

![Program](Images/assembly_and_c_code_comparison.png)

Now let's discuss the commands used to compile and exceute the codes.

* Compiling the c code and assembly code together
> `riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o <.o file> <.c file> <.S file>`

* Executing the code compiled in the step above
> `spike pk <.o file>`

* To disassemble the code
> `riscv64-unknown-elf-objdump -d <.o file> | less`

* To run a .sh file run the following commands:
> `chmod 777 <.sh file>`

> `./<.sh file>`

The outputs of the first three commands are shown in the images below:

![Program](Images/compile_and_simulate_code.png)

![Program](Images/disassembly_instruction_output.png)

Befor running the .sh script we will need to install a github repository. The steps involved in installing the github repo and running the .sh script are shown below:

![Program](Images/git_clone_output_series.png)

![Program](Images/sh_file_output.png)

The github repo cloned also contains hex format files. The files are depicted below:

![Program](Images/firmware_file_contents_hex_format.png)

![Program](Images/firmware32_file_contents_hex_format.png)

## Day 3: Digital Logic with TL-Verilog and Makerchip
In Day 3, we have familiarized ourselves with the Makerchip IDE and the syntax of TL-Verilog. Some features of TL-Verilog which make it unique are:

* Easy Pipelining
* Support for Timing Abstraction
* Familiar and Intuitive Syntax
* Enables faster development


In order to get comfortable with TL-Verilog we have implemented several digital ciruits some of which are shown here.

* Inverter

![Program](Images/inverter_example.png)

* AND Gate

![Program](Images/and_gate.png)

* OR Gate

![Program](Images/or_gate.png)

* XOR Gate

![Program](Images/xor_gate.png)

* Adder

![Program](Images/adder_example.png)

* Mux

![Program](Images/mux_example.png)

* Mux Vector

![Program](Images/mux_vector_example.png)

* Pythagoras Theorem

![Program](Images/pythagorean_example.png)

* Fibonacci Circuit Implementation

![Program](Images/fibonacci_ciocuit_implementation.png)

* Pipeline Lab

![Program](Images/lab_pipeline_example.png)

* Counter

![Program](Images/counter_results.png)

* Calculator

![Program](Images/pipeline_counter_and_calculator.png)

![Program](Images/calculator_output.png)

![Program](Images/final_calculator_diagram.png)

![Program](Images/calculator_final_viz_window.png)

![Program](Images/calculator_final_waveform1.png)

![Program](Images/calculator_final_waveform2.png)

## Day 4: Basic RISC-V CPU Microarchitecture
In Day 4 we have implemented the basic microarchitecture for the RISC-V ISA. The figure below depicts the basic microarchitecture that we will be implementing today.

![Program](Images/basic_microarchitecture.png)

The code for the non-pipelined microarchitecture can be found in the file "non_pipelined_riscv_core.tlv" in the folder "Day3_5".

The images below depict the relevant figures obtained during the compilation and simulation of the code in the Makerchip IDE.

![Program](Images/diagram_not_pipelined.png)

* Viz Window at Cycle 0

![Program](Images/viz_initial.png)

* Viz Window at the last cycle

![Program](Images/viz_final.png)

* Waveform Snapshots

![Program](Images/waveform_not_pipelined1.png)

![Program](Images/waveform_not_pipelined2.png)

![Program](Images/waveform_not_pipelined3.png)


## Day 5: Complete Pipelined RISC-V CPU Microarchitecture
In Day 5 we have added pipeline stages for the microzrchitecture implemented in Day 4. The code for it can be found in the file "risc-v_solutions.tlv" in the folder "Day3_5".

The images below depict the relevant figures obtained during the compilation and simulation of the code in the Makerchip IDE.

![Program](Images/pipelined_cpu_diagram.png)

* Viz Window at Cycle 0

![Program](Images/viz_pipelined_initial.png)

* Viz Window at the last cycle

![Program](Images/viz_pipelined_final.png)

* Waveform Snapshots

![Program](Images/waveform_pipelined1.png)

![Program](Images/waveform_pipelined2.png)

![Program](Images/waveform_pipelined3.png)

![Program](Images/waveform_pipelined_4.png)

**Note:** The reports for Days 2 to 5 are also documented in the README.md files present in the folders of the respective days.

## Learning Outcomes
* Understanding the RISC-V ISA
* Using the RISC-V GNU Toolchain
* Syntax of TL-Verilog
* Implmentation of Combinational and Sequential Logic Circuits using TL-Verilog
* Building a pipelined RISC-V core

## Acknowledgements
- [Kunal Ghosh](https://github.com/kunalg123), Co-founder, VSD Corp. Pvt. Ltd.
- [Steve Hoover](https://github.com/stevehoover), Founder, Redwood EDA
- Shivam Potdar, TA
- Vineet Jain, TA
- Shivani Shah, TA