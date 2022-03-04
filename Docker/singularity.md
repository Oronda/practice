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
