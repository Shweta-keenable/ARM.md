# ARM Istructions

ARM defines two separate instruction sets 
1- ARM state instruction set – 32-bit wide 
2-Thumb state instruction set – 16-bit wide N. Mathivanan 

# ARM State Instruction Set

# Features 
3-address data processing instructions

Conditional execution of each instruction 

Shift and ALU operations in single instruction

Load-Store and Load-Store multiple instructions

#  Classes of instructions

Data processing instructions 

Branch instructions

Load-Store instructions 

Software interrupt instructions

Program status register instructions

Coprocessor instructions

# Data Processing Instructions
 Perform move, arithmetic, logical, compare and multiply operations 
 All operations except multiply instructions are carried out in ALU 
 Multiply instructions are carried out in multiplier block 
 Data processing instructions do not access memory 
  Instructions operate on two 32-bit operands, produce 32-bit result.
  
  Syntax: <opcode>{<cond>}{S} Rd, Rn, n ‘cond’- indicates flags to test, ‘S’ – set condition flags in CPSR ‘n’ may be ‘Rm’, ‘#const’
  or ‘ Rs, <shift|rotate> N’ Rd – destination, Rn – 1st operand, Rn/Rm/Rs remains unchangedN
  
  
 ## Load/Store instruction
  
  Single or multiple registers can be loaded and stored at one time.

Load and store single register instructions can transfer a 32-bit word, a 16-bit halfword, or an 8-bit byte between memory and a register. Byte and halfword loads can be automatically zero extended or sign extended as they are loaded.

Load and store instructions have three primary addressing modes:
  
  ## Branch instructions
  
  As well as allowing any data processing or load instruction to change control flow (by modifying the PC) a standard branch instruction is provided with 24-bit signed offset, allowing forward and backward branches of up to 32MB. Branch with Link (BL) allows efficient subroutine calls, and preserves the address of the instruction after the branch in R14 (the Link Register or LR). This allows a move instruction to put the LR in to the PC and return to the instruction after the branch.The third type of branch (BX) switches between ARM and Thumb instruction sets. The return address can be preserved in the LR as an option.
  
  
  ## Coprocessor
  There are three types of coprocessor instructions:

 coprocessor data processing instructions invoke a coprocessor specific internal operation

 coprocessor register transfer instructions allow a coprocessor value to be transferred to or from an ARM register

 coprocessor data transfer instructions transfer coprocessor data to or from memory, where the ARM calculates the memory address of the transfer. 
 
 ## Software interrupt instruction
 
  Software Interrupt instruction (SWI) is used to enter Supervisor mode, usually to request a particular supervisor function. The SWI handler reads the opcode to extract the SWI function number.

A SWI handler returns by executing the following irrespective of the processor operating state:

MOVS PC, R14_svc

This action restores the PC and CPSR, and returns to the instruction following the SWI.
 
## Program Status Registers
 
 The processor has one Current Program Status Register (CPSR), and five Saved Program Status Registers (SPSRs) for exception handlers to use. The Program Status Registers:

    hold information about the most recently performed ALU operation

    control the enabling and disabling of interrupts

    set the processor operating mode. 
 
  
  
  
  
  
  
  
  
  
