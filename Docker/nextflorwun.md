Nextflow seamlessly integrates with GitHub hosted code repositories and sharing platform. This feature allows you to manage your project code in a more consistent manner or use other people’s Nextflow pipelines, published through GitHub in a quick and transparent way.

When you launch a script execution with Nextflow, it will look for a file with the pipeline name you’ve specified. If that file does not exist, it will look for a public repository with the same name on GitHub (unless otherwise specified). If it is found, the repository is automatically downloaded to your computer and executed. This repository is stored in the Nextflow home directory, and thus will be reused for any further executions.

### Running a nextflow pipeline
There are two ways;
1. You can specify its qualified name after the `run` command. The qualified name is formed by two parts: the owner name and the repository name separated by a / character. For example
 
 ```
 nextflow run oronda/practice
 
```

2. You can specify the repository URL after the `run` command. For example

```
nextflow run http://github.com/oronda/practice
```

Any Git branch, tag or commit ID defined in a project repository, can be used to specify the revision that you want to execute when launching a pipeline by adding the `-r` option to the run command line.

