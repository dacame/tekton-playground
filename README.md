# tekton-playground

An example of Tekton pipelines to deploy the spring petclinic app:
- Build Maven app (Taks build)
- Build and push container (Task buildind and push with kaniko)
- Deploy to K8s cluster (Task for checkin deployment and deploy with Kubectl)

There are some pipelines resources to use as inputs and outputs:
- Git repo for pet-clinic app
- Image where to put the container and where to gather from deploy