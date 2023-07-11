# General Description
Sample program to declare and sum the elements of an array, keep in mind ending the program is done by writing the 01000100 number into the $GPR register.
# Instruction Set Architecture (ISA)
The instruction set architecture (ISA) of the processor includes the following 6 instructions: 
1.   	GET: Load a value from memory into the general-purpose register.
●        Example: GET 0001 (loads the value at address 0001 into the general-purpose register)
 
2.   	SET: Store a value from the general-purpose register into memory.
●        Example: SET 0001 (stores the value in the general-purpose register at address 0001)
 
3.   	PUSH: Add a value from memory to the value in the general-purpose register.
●        Example: PUSH 0001 (adds the value at address 0001 to the value in the general-purpose register)
 
4.   	PULL: Subtract a value from memory from the value in the general-purpose register.
●        Example:  PULL 0001 (subtracts the value at address 0001 from the value in the general-purpose register)
 
5.   	JUMP: Jump to a specific memory address.
●        Example:  JUMP 0010 (sets the program counter to address 0010)
 
 
6.   	JUMPZ: Jump the instruction, if the value of the register is 0.
•	Example: JUMPZ

# Binary Format
1. GET: The GET instruction has the following format: GET $GPR, address Binary format:
7	6	5	4	3	2	1	0
0	0	0	0	0	0	0	1
The first 3 bits (000) can be used to identify the instruction as a GET instruction. The next 5 bits can be used to encode the memory address to be loaded into the GPR.

2.	SET: The SET instruction has the following format: SET $GPR, address Binary format:
7	6	5	4	3	2	1	0
0	0	0	0	0	0	1	0
The first 3 bits (001) can be used to identify the instruction as a SET instruction. The next 5 bits can be used to encode the memory address where the value in the GPR will be stored.

3.	PUSH: Binary format:
7	6	5	4	3	2	1	0
0	0	0	0	0	1	0	0
The first 3 bits (001) can be used to identify the instruction as a PUSH instruction. The next 5 bits can be used to encode the memory address from which the value will be added to the value in the GPR.




4.	PULL: The PULL instruction has the following format: PULL $GPR, $GPR, address Binary format:
7	6	5	4	3	2	1	0
0	0	0	0	0	1	0	1
The first 3 bits (010) can be used to identify the instruction as a PULL instruction. The next 5 bits can be used to encode the memory address from which the value will be subtracted from the value in the GPR.

5.	JUMP: The JUMP instruction has the following format: 

| 7 |	6 |	5 |	4 |	3 |	2 |	1 |	0 |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | 0 |

The first 3 bits (100) can be used to identify the instruction as a JUMP instruction. The next 5 bits can be used to encode the memory address to which the program counter will be set.
 
6.	JUMPZ instruction has the following format: 

| 7 |	6 |	5 |	4 |	3 |	2 |	1 |	0 |
|---|---|---|---|---|---|---|---|
| 0 | 0 | 0 | 0 | 1 | 0 | 0 | 1 |


The first 3 bits (101) can be used to identify the instruction as a JUMPZ instruction. The next 5 bits can be used to encode the memory address to which the program counter will be set if the value in the GPR is 0.

# Code binary format
