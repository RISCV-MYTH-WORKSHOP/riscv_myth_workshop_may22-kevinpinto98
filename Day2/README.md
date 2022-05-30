## Day 2: Introdution to ABI and Basic Verification Flow

* Application Binary Interface (ABI) describes a low-level interface between two applications or between an application and an operating system. An example of what the ABI interface looks like can be seen in the image below.

![Program](../Images/abi_interface.png)

* ABI enables application programs to directly access the registers of the RISC-V architecture through system calls.

* The RISC-V architecture has 32 registers. Their ABI names as well as their usage is mentioned in the table below.

![Program](../Images/register_table.png)

In Day 2, we have written a c program for caculating the sum of number from 1 to 9 as well as it's assembly equivalent. The respective programs are shown side-by-side in the image below:

![Program](../Images/assembly_and_c_code_comparison.png)

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

![Program](../Images/compile_and_simulate_code.png)

![Program](../Images/disassembly_instruction_output.png)

Befor running the .sh script we will need to install a github repository. The steps involved in installing the github repo and running the .sh script are shown below:

![Program](../Images/git_clone_output_series.png)

![Program](../Images/sh_file_output.png)

The github repo cloned also contains hex format files. The files are depicted below:

![Program](../Images/firmware_file_contents_hex_format.png)

![Program](../Images/firmware32_file_contents_hex_format.png)



