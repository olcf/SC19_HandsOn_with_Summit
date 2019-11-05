[**Next**](../05)

<h1>Find the Missing Compiler Flag</h1>
OpenACC is a directive-based approach to programming for GPUs. Instead of using a low-level programming method like CUDA, where the programmer is responsible for transferring data between the CPU and GPU and writing GPU kernels, with a directive-based model, the programmer simply adds "hints" within the code which the compiler uses to transfer data and parallelize the code on the GPU. An additional benefit of this type of GPU programming model is that the code can be compiled for either a CPU or GPU simply by adding or removing compiler flags (whereas a CUDA code requires a GPU).

<br>

In this challenge, you will need to find the compiler flag that enables GPU support in a simple OpenACC vector addition program. The single `#pragma acc parallel loop` (which is the hint to the compiler) line is the only change needed to make this a GPU code. But without the correct compiler flag, that line will be ignored and a CPU-only executable will be created. 


<h2>Step 1: Set Up the Programming Environment </h2>

In order to run the provided OpenACC code, we will need to modify our programming environment. First, we will change the compiler to PGI:

```
$ module load pgi
```

Then, we will load the CUDA Toolkit:

```
$ module load cuda
```

<h2>Step 2: Find the Necessary Compiler Flag</h2>

Next, you will need to find the PGI compiler flag needed to compile the code with OpenACC-support. To do so, you can either search within the Summit User Guide or the PGI documentation. 

> NOTE: Compiler flags differ between different compilers so make sure you find the correct flag for the PGI compiler.

<h2>Step 3: Add the Compiler Flag to the Makefile and Compile</h2>

Now that you think you found the correct compiler flag, add it to the end of the `CFLAGS = -Minfo=all` line in the Makefile. Then, compile the code by issuing the following command:

```
$ make
```

If you added the correct flag, you should see evidence of it in the output from the compiler:

```
main:
     24, Generating Tesla code
         25, #pragma acc loop gang, vector(128) /* blockIdx.x threadIdx.x */
     24, Generating implicit copyout(C[:1048576])
         Generating implicit copyin(B[:1048576],A[:1048576])
```

<h2>Step 4: Run the Program</h2>

Now, test that you have correctly compiled the code with OpenACC-support by launching the executable on a compute node. To do so, issue the following command:

```
$ bsub submit.lsf
```

> NOTE: The submit.lsf script requests access to 1 compute node for 10 minutes and launches the executable on that compute node using the job launcher, `jsrun`.


Once the job is complete, you can confirm that you ran an a GPU by looking at the output file, `add_vec.JOBID`, where JOBID will be the number associated with your job. If you ran on a GPU, you'll see results from the NVIDIA profiler, such as

```
==6163== Profiling result:
            Type  Time(%)      Time     Calls       Avg       Min       Max  Name
 GPU activities:   62.26%  363.49us         2  181.74us  181.60us  181.89us  [CUDA memcpy HtoD]
                   31.17%  181.98us         1  181.98us  181.98us  181.98us  [CUDA memcpy DtoH]
                    6.57%  38.368us         1  38.368us  38.368us  38.368us  main_24_gpu
```


[**Next**](../05)
