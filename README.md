# Hello World Express Node.js Application

This is a simple Node.js application built with Express that provides an HTTP endpoint returning a "Hello World" message. You can visit the http://34.172.214.193:3000/ or simply use curl. This project is deployed in google cloud kubernetes cluster.

```
curl http://34.172.214.193:3000/
```

Expected curl response:

```
StatusCode        : 200
StatusDescription : OK
Content           : <!DOCTYPE html><html><head><title>Hello World</title><link rel="stylesheet"
                    href="/stylesheets/style.css"></head><body><h1>Hello World</h1></body></html>
RawContent        : HTTP/1.1 200 OK
                    Connection: keep-alive
                    Keep-Alive: timeout=5
                    Content-Length: 153
                    Content-Type: text/html; charset=utf-8
                    Date: Thu, 25 May 2023 20:09:50 GMT
                    ETag: W/"99-MXbdwifHnRoLyrqx0znE1aE+0r...
Forms             : {}
Headers           : {[Connection, keep-alive], [Keep-Alive, timeout=5], [Content-Length, 153], [Content-Type,
                    text/html; charset=utf-8]...}
Images            : {}
InputFields       : {}
Links             : {}
ParsedHtml        : mshtml.HTMLDocumentClass
RawContentLength  : 153
```

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
    


