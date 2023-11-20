---
title: About Virya cluster
date: 2023-11-19 22:30:00 -500
categories: [cluster, overview]
tags: [resources,cluster,gpu,slurm]
---

## Wthat is Virya

Virya is Concordia's University GPU-based HPC cluster. 

## Who can access Virya 
 
Only members of CSSE department: students, faculty, associates and guests can have access to the cluster.

### How to reqeust access?
 
To access the cluster for the first time, send an email to: <virya.help@concordia.ca> providing:
* students: ***full name*** and ***supervisor’s name***.
* Others: ***full name***, ***status at Concordia***

The cluster's administrator will reply with account credentials and access instructions.

## Overview

The cluster is ideal for GPU-centric deep learning and CUDA programs


### Key Components and resources

Cluster execution nodes (4) have combined:
* 24 GPUs (16x30GB and 16x20GB) internal memory 
* 600+ CPU cores  
* 3TB of RAM, and 
* 36TB SSD storage 


### Typical workflow with cluster

1. Login to the ***Submit*** node: ``` ssh <u_name>@virya.encs.concordia.ca ```
2. Check SLURM’s binaries are in the “PATH” ``` sbatch -V ``` 
	1. If not found, load them by running: ``` module load slurm/default ```
3. Upload data, and scripts, under **_/home/u_name_** directory. 
4. Submit a job using ***sbatch*** or ***salloc*** commands.

## Key Components
![img-description](virya_cluster.png) _Virya Cluster_

```bash
#!/bin/bash

#SBATCH -J <job-name>		 # job name
#SBATCH -n4                                     # of CPU cores
#SBATCH --mem=100M                             # memory reserved (mandatory)
#SBATCH -w virya3		# specific node to run the job on. 
#SBATCH --time=00:01:00		# time limit 
#SBATCH -o _%x%J.out                              # output (& error) file name
#SBATCH --mail-type=BEGIN,END       # when to send email notification
#SBATCH --mail-user=<test@domain.com>      # set email to be used 

source /etc/profile.d/modules.sh           # adding module binaries
module load cuda/default                         # adding CUDA library

path/to/script-to-be-executed.sh         # if no path specified the $PWD is used
echo “Done”                                                   # command to be executed

```
