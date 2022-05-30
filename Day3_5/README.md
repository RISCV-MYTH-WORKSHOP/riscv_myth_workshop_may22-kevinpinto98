# RISC-V_MYTH_Workshop

For students of "Microprocessor for You in Thirty Hours" Workshop, offered by for VLSI System Design (VSD) and Redwood EDA, find here accompanying live info and links.

Refer to README at [stevehoover/RISC-V_MYTH_Workshop](https://github.com/stevehoover/RISC-V_MYTH_Workshop) for lab instructions.

Add your codes in the [calculator_solutions.tlv](calculator_solutions.tlv) and [risc-v_solutions.tlv](risc-v_solutions.tlv) files and **keep committing** to your repository after every lab.

## Day 3: Digital Logic with TL-Verilog and Makerchip
In Day 3, we have familiarized ourselves with the Makerchip IDE and the syntax of TL-Verilog. SOme features of TL-Verilog which make it unique are:

* Easy Pipelining
* Support for Timing Abstraction
* Familiar and Intuitive Syntax
* Enables faster development


In order to get comfortable with TL-Verilog we have implemnted several digitl ciruits some of which are shown here.

* Inverter

![Program](../Images/inverter_example.png)

* AND Gate

![Program](../Images/and_gate.png)

* OR Gate

![Program](../Images/or_gate.png)

* XOR Gate

![Program](../Images/xor_gate.png)

* Adder

![Program](../Images/adder_example.png)

* Mux

![Program](../Images/mux_example.png)

* Mux Vector

![Program](../Images/mux_vector_example.png)

* Pythagoras Theorem

![Program](../Images/pythagorean_example.png)

* Fibonacci Circuit Implementation

![Program](../Images/fibonacci_ciocuit_implementation.png)

* Pipeline Lab

![Program](../Images/lab_pipeline_example.png)

* Counter

![Program](../Images/counter_results.png)

* Calculator

![Program](../Images/pipeline_counter_and_calculator.png)

![Program](../Images/calculator_output.png)

![Program](../Images/final_calculator_diagram.png)

![Program](../Images/calculator_final_viz_window.png)

![Program](../Images/calculator_final_waveform1.png)

![Program](../Images/calculator_final_waveform2.png)

## Day 4: Basic RISC-V CPU Microarchitecture
In Day 4 we have implemented the basic microarchitecture for the RISC-V ISA. The figure below depicts the basic microarchitecture that we will be implementing today.

![Program](../Images/basic_microarchitecture.png)

The code for the non-pipelined microarchitecture can be found in the file "non_pipelined_riscv_core.tlv" in the folder "Day3_5".

The images below depict the relevant figures obtained during the compilation and simulation of the code in the Makerchip IDE.

![Program](../Images/diagram_not_pipelined.png)

* Viz Window at Cycle 0

![Program](../Images/viz_initial.png)

* Viz Window at the last cycle

![Program](../Images/viz_final.png)

* Waveform Snapshots

![Program](../Images/waveform_not_pipelined1.png)

![Program](../Images/waveform_not_pipelined2.png)

![Program](../Images/waveform_not_pipelined3.png)


## Day 5: Complete Pipelined RISC-V CPU Microarchitecture
In Day 5 we have added pipeline stages for the microzrchitecture implemented in Day 4. The code for it can be found in the file "risc-v_solutions.tlv" in the folder "Day3_5".

The images below depict the relevant figures obtained during the compilation and simulation of the code in the Makerchip IDE.

![Program](../Images/pipelined_cpu_diagram.png)

* Viz Window at Cycle 0

![Program](../Images/viz_pipelined_initial.png)

* Viz Window at the last cycle

![Program](../Images/viz_pipelined_final.png)

* Waveform Snapshots

![Program](../Images/waveform_pipelined1.png)

![Program](../Images/waveform_pipelined2.png)

![Program](../Images/waveform_pipelined3.png)

![Program](../Images/waveform_pipelined_4.png)
