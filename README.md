# IP 4 K8S EXPLANATION.

This is the explanation for the IP 4 project for Kubernetes deployment to GKE.

## MANIFESTS

I have divided my manifests in three su directories, that is client, ingress, server.

### 1. Client Manifests

The client manifest containes client-deployment and client services.

#### a) Client Deployment.

In the client-deployment, the kind is 'Deployment' and the which belongs to 'yolo' namespace.
It has one replica and the docker image used is from 'bixoloo/client:v1.0.2'.
The exposed port is 3000.

#### b) Client Service.

The client service is a kind of 'Service' and has a type of 'LoadBalancer'
The targetPort is set to 3000.
This is the port which will be pointed to the url with the ip address to be able to access the application.

### 2. Server Manifests

The server manifest contains the configurations for the backend application. It has deployment and services manifests.

#### a) Server Deployment.

In the client-deployment, the kind is 'Deployment' and the which belongs to 'yolo' namespace.
It has one replica and the docker image used is from 'bixoloo/client:v1.0.2'.
The exposed port is 3000.

#### b) Server Service.

The client service is a kind of 'Service' and has a type of 'LoadBalancer'
The targetPort is set to 5000.
This is the port which will be used by the nginx to direct traffic to the client. IP:http://34.31.72.126:3000/

kubectl create secret generic dbpassword --from-literal DBPASSWORD=123
