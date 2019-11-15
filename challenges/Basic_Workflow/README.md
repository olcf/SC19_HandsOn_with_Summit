# Basic Workflow to Run a Job on Summit

The basic workflow for running programs on HPC systems is 1) set up your programming environment - i.e., the software you need, 2) compile the code - i.e., turn the human-readable programming language into machine code, 3) request access to one of more compute nodes, and 4) launch your executable on the compute node(s) you were allocated. In this challenge, you will perform these basic steps to see how it works.


## Setting Up Your Programming Environment
Many software packages and scientific libraries are pre-installed on Summit for users to take advantage of. Several packages are loaded by default when a user logs in to the system and additional packages can be loaded using environment modules. To see which packages are currently loaded in your environment, run the following command:

```
$ module list
``` 

> NOTE: The `$` in the command above represents the "command prompt" for the bash shell and is not part of the command that needs to be executed.

For this example program, we will use the PGI compiler. To load the compiler, issue the command:

```
$ module load pgi
```

## Compile the Code

Now that you've set up your programming environment for the code used in this challenge, you can go ahead and compile the code. First, make sure you're in the `Basic_Workflow/` directory:

```
$ cd ~/SC19_HandsOn_with_Summit/challenges/Basic_Workflow
```

> NOTE: The path above assumes you cloned the repo in your `/ccs/home/userid` directory.

Then compile the code. To do so, you'll use the provided `Makefile`, which is a file containing the set of commands to automate the compilation process. To use the `Makefile`, issue the following command:

```
$ make
```

Based on the commands contained in the `Makefile`, an executable named `run` will be created.

## Run the Program

In order to run the `run` program on Summit's compute nodes, you need to request access to one or more compute nodes and then launch the job on the node(s). The request and launch can be performed using the single batch script, `submit.lsf` (see below). If you open this script, you will see several lines with `#BSUB`, which are the commands to request compute nodes and define your job (i.e., "give me 1 compute node for 10 minutes, charge project TRN001 for the time, and name the job and output file `add_vec_cpu`). You will also see a `jsrun` command within the script, which launches the executable (`run`) on the compute node you were given. The flags given to `jsrun` essentially define how many processes and threads you want to run on your compute node (for more information on using the `jsrun` job launcher, please see challenge [jsrun\_Job\_Launcher](jsrun_Job_Launcher)).

To submit and run the job, issue the following command:

```
$ bsub submit.lsf
```

## Monitoring Your Job

Now that the job has been submitted, you can monitor its progress. Is it running yet? Has it finished? To find out, you can issue the command 

```
$ jobstat -u USERNAME
```

where `USERNAME` is your username. This will show you the state of your job to determine if it's running, eligible (waiting to run), or blocked. When you no longer see your job listed with this command, you can assume it has finished (or crashed). Once it has finished, you can see the output from the job in the file named `add_vec_cpu.JOBID`, where `JOBID` is the unique ID given to you job when you submitted it.

