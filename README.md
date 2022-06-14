# High-Performance-Computing
Notes on High Performance Computing topics and such.

## Basic Definetions
* Core (processor) - A single unit that executes a single chain of instructions.
* Node - a single computer or server.
* Cluster - many nodes connected together which are able to coordinate between themselves.

## Slurm
"_Simple Linux Utility for Resource Management_" <br />
A Slurm script must do three things: <br />
1. Prescribe the resource requirements for the job
2. Set the environment
3. Specify the work to be carried out in the form of shell commands

Sample Slurm Script:
```#!/bin/bash
#SBATCH --job-name=myjob         # create a short name for your job
#SBATCH --nodes=1                # node count
#SBATCH --ntasks=1               # total number of tasks across all nodes
#SBATCH --cpus-per-task=1        # cpu-cores per task (>1 if multi-threaded tasks)
#SBATCH --mem-per-cpu=2G         # memory per cpu-core (4G is default)
#SBATCH --time=00:01:00          # total run time limit (HH:MM:SS)
#SBATCH --mail-type=begin        # send email when job begins
#SBATCH --mail-type=end          # send email when job ends
#SBATCH --mail-user=<YourNetID>@example.edu

module purge
module load anaconda3/2020.11
conda activate pytools-env

python myscript.py```
