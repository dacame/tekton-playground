# Tekton-Playground

This repo is about to test Tekton pipelines using a real example to Petclinic repo. It is [based on my current repository](https://github.com/dcanadillas/petclinic-kaniko) that builds Spring Petclinic application using Kaniko in a Jenkins pipeline executed in Kubernetes.

So, this example of Tekton pipelines build the Spring Petclinic as follows:
- Creates a Tekton task to build the application using Maven
- Creates a Tekton taskt to build the container using Kaniko
- Creates a Tekton task to deploy the container in the Kubernetes namespace (we are using the Tekton one as default)
- Define and creates the Tekton `pipeline` to orchestrate previous defined tasks
- Creates the `pipelineresources` object to be used as inputs and outputs of the tasks
- Run the pipeline through the `pipelinerun` object than instantiate the pipeline to be run

## Tekton structure of this repo

One of the main Tekton advantages, among others, is the ability of decoupling stages of a pipeline (Tekton tasks), so it is possible to run isolated and parametrized. Then, a pipeline is a way to orchestrate different tasks depending on the use case.

So, in this repo we will find the following files/directories:
- Example `Hello World` files to understand Tekton components in an easy way:
  - `hello-world-run.yaml`: Pipeline run instantiation
  - `helloworld-task.yaml`: Tasks definition
  - `helloworld-taskrun.yaml`: Task run instantiation 

There are some pipelines resources to use as inputs and outputs:
- Git repo for pet-clinic app
- Image where to put the container and where to gather from deploy