# L5 - Assembly Programming 1

[Lecture slides link](https://docs.google.com/presentation/d/1MCiXMiFU_-juLWtCAMQpGVCYo8OorCdi07UXzMjd7CA/edit?usp=sharing)

## Lecture

With storage and memory attached to our computer,
we're finally ready to write some programs.

### Machine Code and Assembly

We've already seen glimpses of how
CPU instructions are represented as bytes.
For example, we explored the behavior of the instruction `$EA`
in chapter 2.

It shouldn't come as a surprise that different bytes
produce different behaviors.
If we were determined enough,
we could look up a table of every possible instruction byte on the 6502,
and write an entire program with hand-picked bytes.
This is known as writing **machine code**,
and it is the very lowest layer of programming abstraction possible on most processors.

However, writing raw machine code is both tedious and difficult.
It would be much easier if, instead of remembering the byte values,
we could just write down an easy-to-remember name for each instruction.
This is the principle behind an **assembly language**:
we write programs in a simple text-based programming language,
which then is easy to translate back into machine code.

Once we write our program in an assembly language,
we use a program called an **assembler**
to translate the assembly back into machine code that can be directly run.

### Anatomy of an Instruction

If we take the `$EA` machine-code instruction as an example,
you may recall that we've already given it a name: `NOP`, short for "no operation."
This name is known as a **mnemonic**.

There are a total of 60 distinct instructions on the 65C02,
each of which has its own mnemonic.
Each of those instructions has a byte that encodes the instruction,
and this byte is known as the instruction's **opcode**.

Some instructions might also have one or two additional bytes after the opcode,
and these additional bytes are known as the **operand**.

### Rest of the Chapter

TODO:

## Assignment

There's no hardware changes this time!
Instead, you're going to fill in a program.

Make sure that you've run one of the `install_windows`, `install_macos`, or `install_linux` scripts,
as this will install DASM for you.

Open up `starter-code/sum_1_to_N.S`.
This program starts zeroing out the A register
and loading some number into the X register (in this case, 10).

Write code beneath `sum_loop` according to the comments,
and then deploy this program to your board.
Check previous chapters for the command if you don't remember.

Use the debugger to run your program.
If it worked, then once you get to `halt`,
the A register should contain the sum of the numbers from 1 to 10
(which will be displayed *in hexadecimal* as `37`).
