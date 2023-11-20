---
title: About Virya cluster
date: 2023-11-19 22:30:00 -500
categories: [cluster, overview]
tags: [resources,cluster,gpu,slurm]
---

# About the Virya cluser 
 
Virya cluster is Concordia's University GPU-based HPC cluster. Only members of CSSE department (students, faculty, associates and guests) can have access to the cluster.

##Overview

The cluster is ideal for GPU-centric deep learning and CUDA programs


### Key Components and resources

Cluster execution nodes (4) have combined:
* 24 GPUs (16x30GB and 16x20GB) internal memory 
* 600+ CPU cores  
* 3TB of RAM, and 
* 36TB SSD storage 


### Workflow
Basic workflow while working with the cluster:
1. Login to Submit node: ``` bash ssh <u_name>@virya.encs.concordia.ca ```
2. Check SLURM’s binaries are in the “PATH” 
```bash 
sbatch -V 
``` 
If not found, load them by running: 
```bash 
module load slurm/default 
```
3. Upload data, and scripts, under ***/home/<u_name>*** directory. 
4. Submit a job using ***sbatch*** or ***salloc*** commands.

## Key Components
![img-description](virya_cluster.png) _Virya Cluster_
