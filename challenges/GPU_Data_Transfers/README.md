# Transferring Data Between CPU and GPU

When writing a code to be run on a hybrid compute system (i.e., one with both CPUs and GPUs) such as Summit, you must consider that fact that the CPU and GPU are separate processors with separate memory associated with them. So, when running a program on such a system, control shifts between the CPU and GPU throughout the code and (because of the separate memory) data must be passed back and forth between the two processors as needed.

In this challenge, you will learn how to perform these data transfers with a simple vector addition program. The only parts of the code that are missing are the data transfers between CPU and GPU. Your task will be to look up the `cudaMemcpy` API and add in the data transfers.

## Basic Outline of the Code

The basic outline of the code is as follows:

* Allocate memory for arrays `A` and `B` on CPU (commonly called the "host")
* Allocate memory for arrays `d_A` and `d_B` on GPU (commonly called the "device")
* Initialize values of arrays `A` and `B` on CPU
* TODO: Transfer data from arrays `A` and `B` (on the CPU) to arrays `d_A` and `d_B` (on the GPU)
* Compute vector addition (`d_C = d_A + d_B`) on the GPU
* TODO: Transfer resulting data from array `d_C` (on the GPU) to array `C` (on the CPU)
* Verify results
* Free GPU memory for arrays `d_A`, `d_B`, and `d_C`
* Free CPU memory for arrays `A`, `B`, and `C`

## Add in Data Transfers

There are two places in the code (identified with the word `TODO`) where data transfers must be added. Find these two items and add in the necessary data transfers.

## Compile and Run the Program

Once you think you've added the correct lines to the code, try to compile and run it...

First, make sure you have the CUDA Toolkit loaded:

```c
$ module load cuda
``` 

Then, compile the code:

```c
$ make
```

If the code compiles, try to run it as shown below. If not, read the compilation errors and try to determine what went wrong.

```c
$ bsub submit.lsf
```

If the code ran correctly, you will see `__SUCCESS__`. If not, try to figure out what went wrong. As always, if you need help, feel free to ask.
