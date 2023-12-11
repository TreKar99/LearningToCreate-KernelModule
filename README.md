# LearningToCreate-KernelModule
Learning how to add or remove a kernel module on Linux from 0. 

My problem was that i was in charge of doing a new kernel module, and i had no experience about that. There is a lot of information in internet but lot of people like me, most of that info doesn't work, because when we are working at kernel low level, the dependences and problems are higher.

I will showing how i managed to create my first kernel module:

1. I worked on a Ubuntu 22.04 (an stable version) in a virtual machine.

2. For adding a kernel module, you will need a c code and a Makefile to compile easier.
   Clone this repository to have the code (git clone).
   You will need this packages: **sudo apt-get install build-essential bc**

3. The c code is simple:
   -  init_module: function of module.h to add a kernel module.
   -  cleanup_module: function of module.h to remove a kernel module.
   -  MODULE_LICENSE: required by the kernel compiler.

4. Compile the kernel module in the directory with the command: **make**
  
5. Try adding the kernel module with the command: **sudo insmod ./first-kernel.ko**

6. Check that everything gone well with:
   - lsmod: listing the modules and search for first_kernel.
   - dmesg: printk function prints messages in kernels log, and you have to see the FIRST KERNEL message.

7. To remove the kernel, put the command: **sudo rmmod first_kernel**
