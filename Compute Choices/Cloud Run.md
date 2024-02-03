### Cloud Run Overview:

- **Serverless Container Platform:** Cloud Run enables the running of stateless containers via web requests or Pub/Sub events in a serverless environment.

- **Infrastructure Management:** No need to manage infrastructure; developers can focus solely on coding and application development.

- **Portability:** Cloud Run makes applications portable, allowing them to run consistently across different environments.

- **Automatic Scaling:** Provides automatic scaling capabilities, scaling up or down based on incoming traffic.

- **Resource Costing:** Charges users only for the resources consumed during container execution, with granularity of 100ms.

### Cloud Run Process:

1. **Write Code:** Developers write the application code.

2. **Build and Package:** The application is built and packaged into a container image.

3. **Artifact Registry and Deployment:** The container image is pushed to Artifact Registry, and Cloud Run handles the deployment.

### Cloud Run with Knative:

- **Built from Knative:** Cloud Run is built from Knative, offering the flexibility to run containers either fully managed with Cloud Run or within a Google Kubernetes Engine (GKE) cluster with Cloud Run on GKE.

- **Container-Based Workflow:** Supports both container-based and source-based workflows for application deployment.

### HTTPS Serving and Encryption:

- **Automatic HTTPS Handling:** Cloud Run handles HTTPS serving, simplifying the process for developers.

- **Focus on Web Requests:** Developers only need to focus on handling web requests, leaving Cloud Run responsible for encryption.

