Singularity is a free, cross-platform and open-source computer program that performs operating-system-level virtualization also known as containerization.

One of the main uses of Singularity is to bring containers and reproducibility to scientific computing and the high-performance computing (HPC) world.

The need for reproducibility requires the ability to use containers to move applications from system to system.

Using Singularity containers, developers can work in reproducible environments of their choosing and design, and these complete environments can easily be copied and executed on other platforms.

### Loading the module
In order to use the container you will need to load the Singularity module on your HPC resource.

```
module load singularity
```

### Differences between Docker and Singularity
1. Singularity is available on the compute nodes not login nodes like in docker.

2. Singularity can be used to download images from a docker repository and convert to a singularity image (container), but the reverse is not true.

### Downloading containers
One can use the command;

```
singularity pull docker://biocontainers/<singularity_name>
```

### Running container commands
Since singularity is not available on the login nodes, you can use the HPRC VNC portal app to launch an interactive session on a compute node and run commands found in the container using singularity.

Execute a command that is available in the singularity image file. FOr example;

```
singularity exec /sw/hprc/sw/bio/containers/blast_2.2.31.sif blastp -h
```

Run the image file to explore available software and this will start a prompt so you can test software commands that are found in the image. An exapmle is;

```
singularity run /sw/hprc/sw/bio/containers/blast_2.2.31.sif
```

Singularity downloads include the .sif image as well as a cached copy both the same size.


