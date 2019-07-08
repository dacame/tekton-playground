# tekton-playground

This repo is about to test Tekton pipelines using a real example to Petclinic repo. It is [based on my current repository](https://github.com/dcanadillas/petclinic-kaniko) that builds Spring Petclinic application using Kaniko to build the docker container.

An example of Tekton pipelines to deploy the spring petclinic app:
- Build Maven app (Taks build)
- Build and push container (Task buildind and push with kaniko)
- Deploy to K8s cluster (Task for checking deployment and deploy with Kubectl)

There are some pipelines resources to use as inputs and outputs:
- Git repo for pet-clinic app
- Image where to put the container and where to gather from deploy