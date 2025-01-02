# The NOP Computer

### Notation

The original version of the 6502 was released in 1975,
and programming syntax wasn't nearly as standardized as it is now.
For this class we'll be using the notation used by the 6502's documentation and all of the related tools,
shown in the table below.

| Name        | C Notation | 6502 Notation |
+-------------+------------+---------------+
| Decimal     | 42         | 42            |
| Binary      | 0b101010   | %101010       |
| Hexadecimal | 0x2A       | $2A           |

The important details is that `%` means **binary**, and `$` means **hexadecimal**.

Typically when writing large blobs of numbers (e.g. snippets of machine code) adding the `$` hurts readability,
so this book will omit the `$` for cases where there is no ambiguity.

### A Computer

what's a computer?

### The Data Bus

We've established that the CPU doesn't have enough space to store the whole program itself,
and the program must reside in some external storage.
Thus, somehow, the bytes of the program need to go from the storage into the CPU.

Moving the bytes is done quite simply by using eight wires, one for each bit in a byte.
This collection of eight wires is called the **data bus**,
and it can transfer a single byte of data at a time to or from the CPU.

TODO: Diagram

### The Address Bus

The simple setup with just a data bus has a problem:
how does the storage know which byte it should be sending?

Consider the following pseudocode:
```py
if virtual coin flip is heads:
    print "hello"
else:
    print "goodbye"
```

If the coin flip is heads, we need to be able to send over the bytes that will execute `print "hello"`,
but if the coin flip is tails, we need to send over a different set of bytes that will execute `print "goodbye"`,
and only the CPU knows which path is correct.

Thus, the CPU needs to be able to tell the storage what part of the program it wants next,
and this is done with a group of sixteen wires called the **address bus**.
Unlike the data bus, which can sometimes be bidirectional, the address bus is always driven by the CPU.

For storage devices, the address bus is very similar to an array index.
The storage device will look at the address bus, and it will place on the data bus whichever byte
If `$0000` is driven on the address bus, the very first byte in the storage will eventually appear on the data bus.
If `$0001` is driven on the address bus, the next byte of storage will eventually appear on the data bus, and so on.

TODO: Diagram.


## Hands-On Section

### Assignment

TODO: Schematic

TODO: Actual work

TODO: etc