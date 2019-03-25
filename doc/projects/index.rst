Projects
========
This page documents possible project ideas under the Kami/Coq verification umbrella. We feel it is prudent to divide the
projects into the following levels - 

1. **User projects**: These are projects which use Kami as a verification tool to model and design circuits and prove properties about them
2. **Implementation projects**: These projects are related to implementing features and extending the Kami system

User Projects
~~~~~~~~~~~~~

Verification of 3-stage processor pipeline
------------------------------------------
Processors are digital circuits that realize the von Neumann paradigm of computation in hardware. They execute a stream of instructions
read from a memory and can read and write to memory, either local to the processor or a global shared memory between multiple processors.

To ensure a clean separation of concerns between hardware designers and software programmers, the concept of an Instruction Set Architecture (ISA)
was proposed. The ISA provides a minimal set of instructions that a hardware should implement according to the specification and the programmer
should represent all computation by using this ISA. RISC-V is such an ISAm which is free and open-source with multiple open-source processor 
implementations available.

The main challenge with implementing processors is ensuring that the processor correctly executes the specification of the ISA, 
while implementing performance optimizations made to ensure that maximum concurrency and performance is extracted from hardware. This project statement will attempt to
tackle this problem.

The problem statement for this project is as follows - **Prove in Kami that a 3-stage pipelined RISC-V processor correctly refines an atomic processor model**. We first design an atomic processor, that executes each RISC-V atomically, one-at-a-time. This allows us to ensure that the specification is correct and hardware complexity is not introduced at this stage. Then we implement a 3-stage pipelined processor, where issues like instruction dependencies, pipeline stalls and others are introduced. Then we show that this 3-stage implementation correctly refines the atomic processor. This gives us the confidence that the pipelined processor will correctly execute any RISC-V program, upto the atomic specification

Implementation Projects
~~~~~~~~~~~~~~~~~~~~~~~
