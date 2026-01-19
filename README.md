# Hosting a Calculator Application in Kubernetes Using kind

This is used to build and deploy a simple calculator web application using Docker and host it on a local Kubernetes cluster using kind.

## Steps to run

1. Install prerequisites:
   - Node.js(node -v)
   - Docker(docker --version)
   - kind(kind version)
   - kubectl(kubectl version --client)

2.Create web application using

  (index.html, script.js, styles.css, server.js, package.json)

3.Install Dependencies

  npm install

4.create a Dockerfile, kind-config.yaml

5.build the docker image

  docker build -t calculator-app:latest .

6.Create a kind cluster

  kind create cluster --config kind-config.yaml

7.Add Kubernetes files

  (deployment.yaml, service.yaml)

  kubectl apply -f deployment.yaml

  kubectl apply -f service.yaml

8.Load the Docker image into the kind cluster

  kind load docker-image calculator-app:latest

9.Verfiy the pods

  kubectl get pods

10.Open the app in browser:

  http://localhost:30080

11.To Delete Cluster

  kind delete cluster
