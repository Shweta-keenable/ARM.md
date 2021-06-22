# ARM Istructions

ARM defines two separate instruction sets 
1- ARM state instruction set – 32-bit wide 
2-Thumb state instruction set – 16-bit wide N. 

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
 
 Syntax: <opcode>{<condition>}{<type> Rd,[Rn{,<offset>}] 
 <type> - H, HS, B, BS  
  Rd – source/destination register  
 Rn – Base address  
  <offset> - ‘Rm’ or #(0-4095) or ‘Rm,<shift>#n’ N. 
 
  
  
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
 
Instructions to read/write from/to CPSR or SPSR
   
   • Instructions: MRS, MSR 
   
   • Syntaxes: MRS{<cond>} Rd,<CPSR|SPSR> MSR{<cond>} <CPSR|SPSR>,Rm MSR{<cond>} <CPSR|SPSR>_<fields>,Rm MSR{<cond>}          <CPSR|SPSR>_<fields>,#immediate
   
   • Modifying CPSR, SPSR: Read, Modify and Write back technique o Read CPSR/SPSR using MRS o Modify relevant bits o Transfer to CPSR/SPSR using MSR • Note: 
   
   • In user mode all fields can be read, but flags alone can be modified N.
    hold information about the most recently performed ALU operation

    control the enabling and disabling of interrupts
   
    set the processor operating mode. 
 
 Multiple Load-Store Instructions 
   
   • Transfers data between multiple regs & mem in single instruction
   
   • Instructions: LDM and STM • Use: stack, block move, temporary store & restore 
   
   • Advantages: small code size, single instruction fetch from memory 
   
   • Disadvantages: can’t be interrupted, increases interrupt latency 
  
  
  
  
  
