[**Next**](../XX)

# Inspecting Jobs

Developing large, parallel, scalable applications is arguably the most demanding effort that end-users of HPC systems like Summit face. However, once an application is ready for production runs, a strong understanding of and familiarity with the user environment can be just as critical for a team to be productive.

The user environment includes interfaces to the batch scheduler, parallel job laucher, structure of available file systems, along with any other user-configurable parts of the system. This challenge will rely on interaction with Summit's batch scheduler, [IBM Spectrum LSF](https://www.ibm.com/support/knowledgecenter/en/SSWRJV_10.1.0/lsf_welcome/lsf_welcome.html).

## Monitoring jobs with LSF

As you may have already seen in Challenge 02, LSF provides the fundamental mechanisms to [submit batch jobs](https://docs.olcf.ornl.gov/systems/summit_user_guide.html#batch-scripts), [monitor their status](https://docs.olcf.ornl.gov/systems/summit_user_guide.html#monitoring-jobs) after they've been enqueued, and [control them if needed](https://docs.olcf.ornl.gov/systems/summit_user_guide.html#interacting-with-jobs). 

We won't be submitting any new jobs here, but rather looking at others that have already been run and gathering information about them. To do this, we'll primarily use the `bhist` command. 

(See the `bhist` manual page by running `man bhist` for a full list of command options.)

## Let's try to answer...
1.  How many jobs did Summit complete this morning from 00:00 (midnight) to 09:00 (9AM)?

2. How many unique users did these jobs from 00:00 - 9:00 this morning belong to?

3. Of the jobs that completed between 00:00 and 9:00 this morning, what's the job ID of the longest running job?
    1. How long was it pending (pre-execution), and how long did it run (actual execution time)?
    2. When was it submitted?


[**Next**](../XX)
