# Restored F80 compiler code for CP/M
At one time, W. Cirsovius disassembled Microsoft assembler M80 (MACRO-80 3.44 09-Dec-81), MS-Linker L80 and several other programs and posted the resulting code on his website. Unfortunately, the Microsoft F80 compiler was not included in this list, and in 2014 I made an attempt to fill this gap. I wanted to restore the code of one of the latest compilers. For this reason, I chose FORTRAN-80 Ver. 3.4 Copyright 1978, 79, 80 (C) By Microsoft Created: 19-Feb-85. In addition, this is one of the compilers that in the listing produces code in Z80 assembler. At that moment, I did not yet know that this particular compiler had a bug.

The Fortran-80 compiler consists of eight modules. Module boundaries were determined by comparing the disassembled code of several F80.COM executables. The modules differed slightly and were located in different places. It is most likely that each of the modules was placed in an individual file.

To speed up the compiler, a ready-made symbol table image with Intrinsic functions FORTRAN language is copied from the data area to upper memory. Then the necessary variables are initialized, the compiler parameters are read, and it proceeds to the process of processing the source code.
The compiler is single-pass and for this reason presents its own rules for the location of statements.

The file f80_ram.pdf shows the memory allocation during compiler operation and the structure of the symbol table.

The disassembled source program is partly commented and resides in a single f8.mac file. However, this does not prevent it from being assembled into an object file using the command

m80 f8,f8=f8

and then compose

l80 f8,f8/n/e

The resulting f8.COM executable is completely identical to the original F80.COM

Perhaps, based on this program, someone will find and fix the error of this compiler. I keep the disassembled program for later improvements. 

Andrey Nikitin


