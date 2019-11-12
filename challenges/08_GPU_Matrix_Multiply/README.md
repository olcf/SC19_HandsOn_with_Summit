# Matrix Multiply on GPU Using cuBLAS

BLAS (Basic Linear Algebra Subprograms) are a set of linear algebra routines that perform basic vector and matrix operations on CPUs. Similarly, NVIDIA's cuBLAS library includes a similar set of routines that perform basic linear algebra operations on GPUs. 

In this challenge, you will be given a program that initilizes two matrices with random numbers, performs a matrix multiple on the two matrices on the CPU, performs the same matrix multiply on the GPU, then compares the results. Your task will be to look up the `cublasDgemm` routine and add it to the section of the code identified with a `TODO`.

## Add the Call to cublasDgemm

Look in the code `cpu_gpu_dgemm.c` and find the `TODO` and add in the `cublasDgemm` call.

## Compile the Code

Once you think you've correctly added the cuBLAS routine, try to compile the code.

First, make sure your programming environment is set up correctly for this program:

```c
$ module load cuda essl
```

Then, compile the code

```c
$ make
``` 

If the code compiles, try to run it. If not, look at the compilation errors to identify the problem.

## Run the Program

Once you've successfully compiled the code, try running it.

```c
$ bsub submit.lsf
```

If the CPU and GPU give the same results, you will see the message `__SUCCESS__`. If you do not receive this message, try to identify the problem. As always, if you need help, make sure to ask.
