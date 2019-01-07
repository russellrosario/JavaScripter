+++
description = "Hardware, software, binary, CLI"
title = "Fundamentals"
draft = false
weight = 100
bref="Computers consist of two major elements: hardware and software. Hardware is any physical device used in or with your machine. Software is a set of instructions for a computer to perform specific operations"
toc = true
script = 'animation'
+++

<h3 class="section-head" id="h-Section1"><a href="#h-Section1">Hardware</a></h3>
  <div class="example">
    <dl>
      <dt>CPU</dt>
      <dd>The electronic circuitry within a computer that carries out the instructions of a computer program by performing the basic arithmetic, logic, controlling, and input/output (I/O) operations specified by the instructions. It consists of billions of transistors on the semiconductor material silicon. Transisters are assembled into logic gates (AND, OR, NOT) to make logical decisions based on the digital signals present on its inputs. </dd>
    </dl>
    <dl>
      <dt>Memory (RAM)</dt>
      <dd>Quick and temporary storage space for data. The CPU has exclusive access to RAM and processes data through memory rather than much slower storage devices. Once the process is over or the computer is shut down, the data from memory is wiped.
      <br/><i> CPUs also have a small cache which stores copies of frequently accessed RAM data for even faster retrieval. </i></dd>
    </dl>
    <dl>
      <dt>Input/Output (IO)</dt>
      <dd>Examples of input devices include the mouse and keybord. Output devices are monitors, printers, speakers, etc. A hard drive can be an input or output device depending on whether the CPU is reading or writing to the disk.
      <br/><i> There is also virtual memory which provides additional inactive memory from storage devices through a technique called paging. </i></dd>
    </dl>
    <dl>
      <dt>Motherboard</dt>
      <dd>The glue that connects all components together. It is connected to a power supply and contains expansion slots to allow for additional functionality. For example, a GPU can offload video processing from the CPU. </dd>
    </dl>
    <div style="text-align:center">
      <img src="https://www.javascripter.co/img/basics/hardware.gif">
    </div>
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section2"><a href="#h-Section2">Software</a></h3>
  <div class="example">
    <h5>The operating system (OS)</h5>
    <p>The operating system determines how to allocate resources (CPU and memory) for all the other applications running on your computer. Once an application is opened, the program is loaded into memory and it is called a "process".</p>
    <h5>Processes</h5>
    <p>Each process has a separate memory address space. It cannot efficiently communicate with other processes or access shared data in other processes. Switching from one process to another requires some time (relatively) for saving and loading registers, memory maps, and other resources.</p>
    <p>Every process needs 3 items:</p>
    <ul>
      <li><b>Register</b> - a part of the CPU that holds an instruction, a storage address, or other kind of data needed by the process</li>
      <li><b>Program counter</b> - (aka instruction pointer) keeps track of where a computer is in its program sequence</li>
      <li><b>Stack</b> - a data structure that stores information in memory about the active subroutines of a computer program and is used as scratch space for the process. It includes the <b>Heap</b> which is the dynamically allocated memory portion of the stack.</li>
    </ul>
    <h5>Threads</h5>
    <p>A process can have one thread or have many threads. A thread is the unit of execution within a process. Each thread will have its own stack but all the threads in the process share the same heap. This means that communication between threads is efficient. However, an error in one thread can affect the other threads in the same process.</p>
    <p>With a multithreaded process, the CPU can perform operations in parallel or concurrently.</p>
    <ul>
      <li><b>Parallelism </b> - Genuine simultaneous execution in a multi-core processor.</li>
      <li><b>Concurrency </b> - Interleaving of processes within one processor, giving the illusion of simultaneous execution.</li>
    </ul>
    <div style="text-align:center">
      <img src="https://www.javascripter.co/img/basics/threads.png">
    </div>
  </div>

  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

<h3 class="section-head" id="h-Section3"><a href="#h-Section3">Binary</a></h3>
  <div class="example">
    <p>Because a transmitter can only relay on and off, computers use the base-2 (binary) numeral system using only two symbols: "0" and "1".</p>
    <div style="text-align:center">
      <img src="https://www.javascripter.co/img/basics/binary.png">
    </div>
    <h5>Bit vs Byte</h5>
    <p>A <b>bit</b> is the basic unit of information representing either 0 or 1. <br/>
    A <b>byte</b> represents a string of 8 bits.<br/>
    A <b>kilobyte</b> is equal to 1,024 (2<sup>10</sup>) bytes and a <b>kilobit</b> is equal to 1,024 (2<sup>10</sup>) bits.<br/>
    A <b>megabyte</b> is equal to 1,024 (2<sup>100</sup>) bytes and a <b>megabit</b> is equal to 1,024 (2<sup>100</sup>) bits.<br/>
    </p>
    <p>A common misunderstanding relating to bits and bytes occurs when referring to data size and data speed. Speed is measured in bits and size is measured in bytes. This means that 4G service at 100 megabits per second (Mb/s) allows downloading at 12.5 megabytes per second (MB/s). <i>Note Mb vs MB.</i> </p>
    <h5>Software to binary</h5>
    <p>Since software is written in human readable code, there are a few different ways for a CPU to execute that code.</p>
    <ul>
      <li><b>Compilation </b> - Source code gets converted into binary or machine code by a compiler and saved as an executable.</li>
      <li><b>Interpretted </b> - The program executes at runtime by an interpretter that parses code line by line. It has the benefit of not having to be compiled, but is slower than running native machine code.</li>
      <li><b>Just-in-time compilation </b> - A combination of the two above approaches where the interpreter profiles the program and compiles the most frequently executed parts into native code at runtime.</li>
    </ul>
    <h5>Quantum computing</h5>
    <p>Qubits are 1s and 0s that rely on superposition to have states determined at the time of observation. This means that a qubyte (8 qubits) can have up to 256 different outcomes when executed at runtime.</p>
  </div>
  <div style="text-align:right"> <a href="#top">&#8593; Top</a></div>

  <h3 class="section-head" id="h-Section4"><a href="#h-Section4">Command line</a></h3>
  <div class="example">
    <p>The Command line interface (CLI) is a means of interacting with a computer program where the user (or client) issues commands to the program in the form of successive lines of text (command lines). Most users rely upon graphical user interfaces and menu-driven interactions with a mouse. However, many software developers, system administrators and advanced users still rely heavily on command-line interfaces to perform tasks more efficiently, configure their machine, or access programs and program features that are not available through a graphical interface.</p>
    <p>A Unix shell is a command-line interpreter or shell that provides a command line user interface for Unix-like operating systems. Bash is a Unix shell and command language that can be used for executing commands from the CLI. <i> Windows has their own their shell and command language. Install Git Bash on Windows to run these commands.</i></p>
    <img src="https://www.javascripter.co/img/basics/cli.png">
  </div>
<div style="text-align:right"> <a href="#top">&#8593; Top</a></div>