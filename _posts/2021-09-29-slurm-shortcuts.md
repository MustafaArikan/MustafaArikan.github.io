# Some shortcuts for slurm

Here's the table of contents:

1. TOC
{:toc}

## To be added

```
sinfo
```


## Get remaining time (time limit) of a job

```
squeue -h -j jodid -o %L
```

## Sort jobs by id

```
squeue -a | sort -t, -nk1
```



[See!](https://support.ceci-hpc.be/doc/_contents/SubmittingJobs/SlurmFAQ.html)

