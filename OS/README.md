# Operating system
1. I/O
- A device communicates with a computer system by sending signals over a cable or even through the air.
- A device communicates with the machine via a connection **port**.
- If devices share a common set of wires, the connecton is called a bus. A bus is a set of wires and a rigidly defined protocol.
- When device A has a cable that plugs into device B, and
device B has a cable that plugs into device C, and device C plugs into a port on the computer, this arrangement is called a **daisy chain**.
- A **controller** is a collection of electronics that can operate a port, a bus, or a device.

a. Memory-mapped I/O:
- The processor communicates with the controller by reading and writing bit patterns in these registers.
- One way in which this communication can occur is through the use of special I/O instructions that specify the transfer of a byte or a word to an I/O port address.
- A memory-mapped I/O means the device-control registers mapped into the address space of the processor.
- The I/O device control typically consists of four registers:
    + The **data-in register** is read by the host to get input.
    + The **data-out register** is written by the host to send output.
    + The **status register** contains bits that can be read by the host. These bits indicate states, such as whether the current command has completed, whether a byte is available to be read from the data-in register, and whether a device error has occurred.
    + The **control register** can be written by the host to start a command or to change the mode of a device.
- The data registers are typically 1 to 4 bytes in size. Some controllers have FIFO chips that can hold several bytes of input or output data to expand the capacity of the controller beyond the size of the data register.

b. Interrupts
- The CPU hardware has a wire called the **interrupt-request line** that the CPU senses after executing every instruction.
- When the CPU detects that a controller has asserted a signal on the interrupt-request line, the CPU performs a state save and jumps to the **interrupt-handler routine** at a fixed address in memory.
- The interrupt handler determines the cause of the interrupt, performs the necessary processing, performs a state restore, and executes a return from interrupt instruction to return the CPU to the execution state prior to the interrupt.
- Most CPUs have two interrupt request lines. One is the **nonmarkable interrupt**, which is reserved for events such as unrecoverable memory errors. The second interrupt line is **maskable**: it can be turned off by the CPU before the execution of critical instruction sequences that must not be interrupted.
## Asynchronous programming
