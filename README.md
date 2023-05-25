# FirstKuberTry
Kubernetes Hello World Project

# Hello World Express Node.js Application

This is a simple Node.js application built with Express that provides an HTTP endpoint returning a "Hello World" message.

## Getting Started

### Prerequisites

- Node.js (version v18.16.0)
- npm (version 9.5.1)

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/oorhunn/FirstKuberTry.git
   npm install
   npm start
   ```
2. To build in Docker
    ```
    docker build -t my-node-app .
    ```

3. To push in kubernetes cluster in google cloud 
    ```
    docker tag <image_name> gcr.io/<project_name>/<image_name>

    gcloud docker push gcr.io/<project_name>/<image_name>

    kubectl expose deployment hello-app --name=hello-app-service --type=LoadBalancer --port 3000 --target-port 8080
    ```

### Notes:

- In order to register docker image to google cloud kubernetes engine you need to enable Google Container Registry. But Google Container Registery is depricated. In order to push local docker image to cluster you need to follow the instructions in Artifact Registery. https://cloud.google.com/artifact-registry/docs
    


