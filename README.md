# RV32E

The describe architecture is a RISC-V	architecture	with	the	following	features:	
	 •	16 general-purpose registers (x0–x15), where x0 is a dedicated zero register.
	 •	Registers	are	32	bits	wide	
	 •	Multiply	and	divide	instructions	are	 not present	
	 •	Single	and	double	precision	Floating	point	instructions	are not	present	
	 •	Atomic	instructions	are not	present	 

```sh
Jump    	Unconditional change
Branch  	Conditional change
```



## Instructions

| Instruction | Type | Description | RTL |
| ------ | ------ | ------ | ------ |
add rd, rs1, rs2 | R | Add | rd ← rs1 + rs2, pc ← pc+4
addi rd, rs1, imm | I | Add Immediate | rd ← rs1 + imm i, pc ← pc+4
and rd, rs1, rs2 | R | And | rd ← rs1 & rs2, pc ← pc+4
andi rd, rs1, imm | I | And Immediate | rd ← rs1 & imm i, pc ← pc+4
auipc rd, imm | U | Add Upper Immediate to PC | rd ← pc + imm u, pc ← pc+4
beq rs1, rs2, pcrel 13 | B | Branch Equal | pc ← pc + ((rs1==rs2) ? imm b : 4)
bge rs1, rs2, pcrel 13 | B | Branch Greater or Equal | pc ← pc + ((rs1>=rs2) ? imm b : 4)
bgeu rs1, rs2, pcrel 13 | B | Branch Greater or Equal Unsigned | pc ← pc + ((rs1>=rs2) ? imm b : 4)
blt rs1, rs2, pcrel 13 | B | Branch Less Than | pc ← pc + ((rs1<rs2) ? imm b : 4)
bltu rs1, rs2, pcrel 13 | B | Branch Less Than Unsigned | pc ← pc + ((rs1<rs2) ? imm b : 4)
bne rs1, rs2, pcrel 13 | B | Branch Not Equal | pc ← pc + ((rs1!=rs2) ? imm b : 4)
jal rd, pcrel 21 | J | Jump And Link | rd ← pc+4, pc ← pc+imm j
jalr rd, imm(rs1) | I | Jump And Link Register | rd ← pc+4, pc ← (rs1+imm i)&~1
lb rd, imm(rs1) | I | Load Byte | rd ← sx(m8(rs1+imm i)), pc ← pc+4
lbu rd, imm(rs1) | I | Load Byte Unsigned | rd ← zx(m8(rs1+imm i)), pc ← pc+4
lh rd, imm(rs1) | I | Load Halfword | rd ← sx(m16(rs1+imm i)), pc ← pc+4
lhu rd, imm(rs1) | I | Load Halfword Unsigned | rd ← zx(m16(rs1+imm i)), pc ← pc+4
lui rd, imm | U | Load Upper Immediate | rd ← imm u, pc ← pc+4
lw rd, imm(rs1) | I | Load Word | rd ← sx(m32(rs1+imm i)), pc ← pc+4
or rd, rs1, rs2 | R | Or | rd ← rs1 | rs2, pc ← pc+4
ori rd, rs1, imm | I | Or Immediate | rd ← rs1 | imm i, pc ← pc+4
sb rs2, imm(rs1) | S | Store Byte | m8(rs1+imm s) ← rs2[7:0], pc ← pc+4
sh rs2, imm(rs1) | S | Store Halfword | m16(rs1+imm s) ← rs2[15:0], pc ← pc+4
sll rd, rs1, rs2 | R | Shift Left Logical | rd ← rs1 << (rs2%XLEN), pc ← pc+4
slli rd, rs1, shamt | I | Shift Left Logical Immediate | rd ← rs1 << shamt i, pc ← pc+4
slt rd, rs1, rs2 | R | Set Less Than | rd ← (rs1 < rs2) ? 1 : 0, pc ← pc+4
slti rd, rs1, imm | I | Set Less Than Immediate | rd ← (rs1 < imm i) ? 1 : 0, pc ← pc+4
sltiu rd, rs1, imm | I | Set Less Than Immediate Unsigned | rd ← (rs1 < imm i) ? 1 : 0, pc ← pc+4
sltu rd, rs1, rs2 | R | Set Less Than Unsigned | rd ← (rs1 < rs2) ? 1 : 0, pc ← pc+4
sra rd, rs1, rs2 | R | Shift Right Arithmetic | rd ← rs1 >> (rs2%XLEN), pc ← pc+4
srai rd, rs1, shamt | I | Shift Right Arithmetic Immediate | rd ← rs1 >> shamt i, pc ← pc+4
srl rd, rs1, rs2 | R | Shift Right Logical | rd ← rs1 >> (rs2%XLEN), pc ← pc+4
srli rd, rs1, shamt | I | Shift Right Logical Immediate | rd ← rs1 >> shamt i, pc ← pc+4
sub rd, rs1, rs2 | R | Subtract | rd ← rs1 - rs2, pc ← pc+4
sw rs2, imm(rs1) | S | Store Word | m32(rs1+imm s) ← rs2[31:0], pc ← pc+4
xor rd, rs1, rs2 | R | Exclusive Or | rd ← rs1 ^ rs2, pc ← pc+4
xori rd, rs1, imm | I | Exclusive Or Immediate | rd ← rs1 ^ imm i, pc ← pc+4


