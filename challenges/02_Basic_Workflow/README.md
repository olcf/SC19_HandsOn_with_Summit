[**Next**](../03)

<h1>Basic Workflow to Run a Job on Summit</h1>

In this challenge, you will perform the basic steps needed to compile and run a program on Summit. This will require you to set up your programming environment, compile a code, and launch a job (i.e., run the program) on Summit's compute nodes using a batch scheduler. 


<h2>Step 1: Setting Up Your Programming Environment</h2>
Many software packages and scientific libraries are pre-installed on Summit for users to take advantage of. Several packages are loaded by default when a user logs in to the system and additional packages can be loaded using environment modules. To see which packages are currently loaded in your environment, run the following command:

```
$ module list
``` 

> NOTE: The `$` in the command above represents the "command prompt" for the bash shell and is not part of the command that needs to be executed.

For this example program, we will use the PGI compiler. To load the compiler, issue the command:

```
$ module load pgi
```


<h2>Step 2: Compile the Code</h2>

Now that you've set up your programming environment for the code used in this challenge, you can go ahead and compile the code. First, move into the `vector_addition/` directory within the `challenges/02_Basic_Workflow/` directory

```
$ cd vector_addition
```

To compile the code, you'll use the provided `Makefile`, which is a file containing the set of commands to automate the compilation process. To use the `Makefile`, issue the following command within the `vector_addition/` directory

```
$ make
```

Based on the commands contained in the `Makefile`, an executable named `run` will be created.

<h2>Step 3: Running the Program</h2>
In order to run a program on Summit's compute nodes, you must submit a "job" to the batch scheduler (LSF is the scheduler on Summit). To do so, you'll use the `submit.lsf` batch script, which contains a set of commands to request 1 compute node and launch the `run` executable on that node with the job launcher (`jsrun` is the job launcher on Summit). To launch the job, issue the command

```
$ bsub submit.lsf
```

<h2>Step 4: Monitoring Your Job</h2>
Now that the job has been submitted, you can monitor its progress. Is it running yet? Has it finished? To find out, you can issue the command 

```
$ jobstat -u USERNAME
```
where `USERNAME` is your username. This will show you the state of your job to determine if it's running, eligible (waiting to run), or blocked. 


[**Next**](../03)
