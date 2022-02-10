Snakemake is a system for writing data analysis workflows. It is used to create reproducible and scalable data analysis. Workflows are described by a human readable python language. They can be scaled to server, cluster, grid and cloud environments and take advantage of the high perfomance computing capacity. Snakemake can intergrate with conda and help to deploy with different softwares used in bioinformatics. Snakemake works on Linux, Mac and Windows. It is a free software.

Snakemake is like writing a shell script, but instead of putting a series of commands into a script, one writes a set of rules into a file called a sankefile. The rules have to find inputs and outputs and actions. It then works out the correct order of rules to reach a given target, then runs them.

A snakefile contains 8 lines. The syntax of python is similar to that of snakemake. Snakemake builds up workflows from rules. It is all based on filename persons and wild card placements.

Snakemake runs the necessary jobs. If the job has been run and no new data has been added then snakemake will tell you nothing to be done. 

The main flags of snakemake include:
* `-p` which prints shell commands before it runs them
* `-n` only shows steps but does not run them. It is useful for testing workflows and you want to check that everything looks fine before you actually do any analysis.
* `-F` used for force running all steps
* `-j` runs multiple jobs in parallel


