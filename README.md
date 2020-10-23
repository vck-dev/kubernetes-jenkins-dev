# Kubernetes Jenkins Development cluster

Manifests for deploying a development cluster in Kubernetes. 

## Installing

These manifests assume that you alredy have a running kubernetes cluster running, either through kubeadm, KH or Minikube. Copy the files locally where you store your manifests. Run `kubectl apply -f jenkins-namespace.yaml` to create the namespace to store all resources. Once the namespace has been created, you can apply the remaining manifests individually, or using `kubeconfig apply -f .` to apply them all (namespace won't update after previously being connected.) Create a persistent volume that can be used to store your Jenkins data between deployments.

### jenkins-namespace.yaml
Create the namespace 'jenkins-dev' within the configured cluster

### jenkins-deployment.yaml
Generate the deployment of containers to run, labeled jenkins-dev

### jenkins-net.yaml
Generate the network components of the jenkins-dev cluster

### jenkins-service.yaml
Generate the appropriate service to connect to the cluster endpoint

### jenkins-pv.yaml
Generate the peristent volume used by Jenkins to store internal service data

### jenkins-pvc.yaml
Claim the persistent volume for storing data

### jenkins-ingress.yaml
Ingress controller to allow access to the Jenkins service externally
