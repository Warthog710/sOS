# sOS
sOS (Save Our System) is a custom built 32bit multitasking operating system. The MSDOS like OS is written in C and a little Assembly. It currently supports process scheduling with time quantum's, system calls, interprocess communication through mailboxes with message queues, and process synchronization through semaphores.

### Notes:
sOS is designed to be compiled through the SPEDE enviroment. In light of this, you will need both SPEDE host to compile the OS and SPEDE target to run it. These both can be ran in VirtualBox. The images for each virtual machine are provided below. Once installed and both are running, please follow the instructions below to build and run sOS.<br>
<a href="https://drive.google.com/file/d/1LIFpfBHor0UUO6wvJF4CWyJ1BT32prks/view?usp=sharing">SPEDE Host</a>
<a href="https://drive.google.com/file/d/1cGNbNunXd0d8n0grEIp4JIwHSEk9KOkq/view?usp=sharing">SPEDE Target</a>


### Building sOS:
1. Run ``spede-mkmf`` to create a makefile on the SpedeTarget if one does not exist. Change the variable *OS_NAME* to *sOS*<br><br>
2. Either use ``make`` or ``make debug`` to generate the OS image (.dli file)
    * Note: ``make clean`` can be used to remove the files generated by the makefile<br><br>
3. Run ``flash sOS.dli`` followed by ``download`` to load the onto SpedeTarget<br><br>
4. Run ``flint`` followed by `g` to run the OS on the target machine.
    * If you wish to debug the OS run ``gdb`` followed by ``continue`` to debug.
        * Note: best used with an OS image created with ``make debug``