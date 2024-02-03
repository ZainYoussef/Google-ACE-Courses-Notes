
## Containers and Their Purpose

Containers are a lightweight and portable way to package and run applications along with their dependencies. They provide an isolated user space for running application code without virtualizing the entire operating system or the entire machine. Key characteristics of containers include:

- **Isolation:** Containers isolate application processes and dependencies from each other.
- **Lightweight:** Containers are more lightweight than traditional virtual machines and can be created and shut down quickly.
- **Portability:** Containers are portable across different environments, ensuring consistent behavior.

Containers solve various problems, such as isolating dependencies, reducing resource wastage compared to virtual machines, and easing troubleshooting across different environments.

## Container Image

A container image is a package that includes an application and its dependencies. When an image runs, it becomes a container—an instance of the image. Container images are structured in layers, and a container manifest specifies the contents and loading sequence of a container.

- **Dockerfile:** A Dockerfile is a container manifest used to build container images. It contains instructions to create layers in the image.
- **Layers:** Each instruction in the Dockerfile creates a layer, and layers are read-only. The topmost writable layer, known as the container layer, allows changes during the container's runtime.
- **Docker:** Docker is a tool used to build container images and run containers.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/45a196f1-36e7-4af5-8341-7b1c5cfbd476)

## Dockerfile Commands

A Dockerfile consists of commands that define the layers in a container image:

1. **FROM:** Specifies the base layer (often from a public repository).
2. **COPY:** Creates a layer containing files copied from the build tool's current directory.
3. **RUN:** Builds the application and adds the results to a layer.
4. **CMD:** Specifies the command to run within the container at launch.

When writing a Dockerfile, the least likely to change instructions should be at the top, and those most likely to change should be at the bottom.

## Container Runtimes and Layers

- **Container Layer:** When launching a container, the container runtime adds a writable layer on top of underlying layers. This layer is ephemeral, and changes made to the running container are written to this writable layer.
- **Union File Systems:** Containers use union file systems to bundle everything needed into layers efficiently.

## Obtaining Container Images

Container images can be obtained or created from various sources, including:

- **Artifact Registry:** Store and download images.
- **Public Open Source Containers:** Available from open-source communities.
- **Docker Hub:** A public repository of container images.
- **Cloud Build:** A service for building container images.

## Linux Technologies Enabling Containers

Several Linux technologies enable containerization:

- **Linux Processes:** Each process has its virtual memory address space.
- **Linux Namespaces:** Control what an application can see, including process IDs, directory trees, IP addresses, etc.
- **Linux cgroups:** Control resource consumption, such as CPU time, memory, I/O bandwidth, etc.
- **Union File Systems:** Efficiently encapsulate applications and their dependencies.

---
# Kubernetes Overview

## Introduction to Kubernetes

Kubernetes is an open-source platform designed to manage and scale containerized workloads and services. It provides a robust solution for deploying, managing, and orchestrating containers, allowing for consistent application deployment across various environments, including on-premises, hybrid, and cloud-native setups.

Key Characteristics:
- **Orchestration:** Kubernetes orchestrates containers on multiple hosts, scales them as microservices, and facilitates easy deployment rollouts and rollbacks.
- **API-Driven:** It exposes a set of APIs to deploy containers on a cluster of nodes.
- **Cluster:** Comprises nodes that run containers, along with a control plane for coordination.

## Stateless and Stateful Applications

Kubernetes supports both stateless and stateful applications:
- **Stateless Application:** An application that doesn't require user and session data to be stored persistently.
- **Stateful Application:** An application that requires user and session data to be stored persistently.

## Declarative Configuration Management

Kubernetes follows a declarative configuration management approach, where users describe the desired state of the system, and Kubernetes ensures the deployed system conforms to that state despite failures. This approach leverages a watch loop to continuously monitor and reconcile the current state with the desired state.

## Kubernetes Object Model

- **Object:** A persistent entity representing the state of something running in a cluster.
- **Kind:** Represents the type of an object (e.g., pods).
  
Kubernetes objects have two crucial elements:
1. **Object Spec:** Defines the desired state of the object.
2. **Object Status:** Represents the current state of the object, provided by the Kubernetes control plane.

## Pods

- **Pods:** The foundational building block in Kubernetes and the smallest deployable Kubernetes object.
- A pod can contain one or more containers that are tightly coupled and share resources.
- Each pod is assigned a unique IP address.
- Containers within the same pod can communicate through localhost.

## Kubernetes Components

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/2722605d-3f10-4b4c-b2cb-77b3599752b8)

### Control Plane Components:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/67ae4def-c87c-42d0-8b89-15e33658f84e)

1. **kube-apiserver:** Accepts commands to view or change the cluster's state.
2. **etcd:** The cluster's database that reliably stores the state of the cluster.
3. **kube-scheduler:** Responsible for scheduling pods onto nodes.
4. **kube-controller-manager:** Monitors the cluster's state and attempts to make changes to achieve the desired state.

### Node Components:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/c592689e-8026-4a36-a39e-b8879fafc148)

1. **kubelet:** Connects to the kube-apiserver and interacts with the container runtime.
2. **Container Runtime:** Software used to launch containers from a container image.
3. **kube-proxy:** Maintains network connectivity among pods in a cluster.

## Object Management in Kubernetes

In Kubernetes, object management involves creating and maintaining entities such as pods, services, and deployments. This is achieved by defining the desired state of these objects using manifest files, which are typically written in YAML or JSON formats. Below are key points related to object management in Kubernetes:

### Manifest Files

1. **Definition:** Manifest files are ordinary text files that specify the configuration and desired state of Kubernetes objects. These files can be written in YAML or JSON.

2. **Content:** A manifest file for a pod, for example, may contain details such as the pod's name, labels, specifications for containers, and other relevant settings.

### Pod Creation

1. **Pod Creation:** To create a pod, you need to define a manifest file that describes the desired state of the pod. This includes specifying the pod's metadata, container images, volumes, and other settings.

2. **YAML Example:**
   ```yaml
   apiVersion: v1
   kind: Pod
   metadata:
     name: mypod
   spec:
     containers:
     - name: mycontainer
       image: nginx:latest
   ```

### Using Deployments

1. **Single Manifest vs. Deployment:** While you can use a single YAML manifest to create a single pod, it is often more practical to use higher-level abstractions like Deployments. Deployments allow you to define and manage multiple replicas of a pod with a single YAML file.

2. **Deployment YAML Example:**
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: mydeployment
   spec:
     replicas: 3
     selector:
       matchLabels:
         app: myapp
     template:
       metadata:
         labels:
           app: myapp
       spec:
         containers:
         - name: mycontainer
           image: nginx:latest
   ```

3. **Benefits of Deployments:**
   - **Scalability:** Easily scale the number of replicas.
   - **Rollouts/Rollbacks:** Perform controlled rollouts and rollbacks of updates.
   - **Self-healing:** Automatic replacement of failed pods.

### Declarative Configuration Management

1. **Declarative Approach:** Kubernetes follows a declarative configuration management approach. Users declare the desired state, and Kubernetes ensures the system's deployed state aligns with the declared state.

2. **Watch Loop:** Kubernetes continuously monitors the declared state and actively works to reconcile the current state with the desired state.
---
## Google Kubernetes Engine (GKE)

Google Kubernetes Engine (GKE) is a managed Kubernetes service provided by Google Cloud. It allows users to deploy and operate containerized applications at scale, utilizing Google's infrastructure. Here are key aspects of GKE:

### Managed Service

- **Fully Managed:** GKE is fully managed by Google, meaning Google takes care of maintenance tasks such as auto-upgrades, security patching, and overall cluster health.

- **Control Plane Management:** The control plane components, including the Kubernetes API server, resource controllers, scheduler, and cluster storage, are managed by Google.

### GKE Modes

#### Autopilot Mode

- **Overview:** Autopilot mode is designed for optimal cluster management with minimal manual intervention.

- **Key Points:**
  - **Cost-Effective:** Pay only for the resources used by Pods, not the underlying nodes.
  - **Production-Ready:** Adheres to Google's best practices for robust and battle-tested clusters.
  - **Enhanced Security:** Google handles security for cluster nodes and infrastructure.
  - **Operational Efficiency:** Continuous monitoring, reliable pod scheduling, and easy update configurations.
  - **Resource Consumption Optimization:** Google takes care of resource optimization.

- **Restrictions:**
  - **Limited Configuration Options:** Fewer configuration options compared to Standard mode.
  - **Restricted Node Access:** Limited features like SSH, privilege escalation, and certain node affinity.

#### Standard Mode

- **Overview:** Standard mode offers more flexibility in configuring Kubernetes but requires more manual management.

- **Key Points:**
  - **Configurational Control:** Provides fine-grained control over Kubernetes environment configurations.
  - **Management Responsibility:** Users are responsible for managing and optimizing the cluster.

- **Recommendation:** Use Autopilot mode unless specific high-level configuration control is needed.

### GKE Cluster Architecture

![gke-architecture](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/43a6be41-c0f7-4daa-8e9e-5f399e3a96f8)# Containers Overview


- **Nodes:** VMs grouped together to form a cluster, where applications are packaged into containers.

- **Control Plane:** Managed by Google and includes the Kubernetes API server, resource controllers, scheduler, and cluster storage.

- **Worker Nodes:** Managed by Google in Autopilot mode and user-managed in Standard mode.

### Regional Clusters

- **Advantage:** Regional clusters increase availability by replicating the control plane and nodes across multiple zones.

- **GKE Autopilot:** Always regional. GKE Standard allows the choice of regional, zonal, or multi-zonal clusters.

### Choosing a GKE Mode

- **Autopilot Mode:** Recommended for simplified management, enhanced security, and resource optimization.

- **Standard Mode:** Offers more control but requires greater management responsibility and incurs fixed infrastructure costs.

---

## Kubernetes and kubectl Overview

### Kubectl Command

Kubectl is a command-line tool used to manage and interact with Kubernetes clusters. Key points about kubectl:

- It communicates with the Kubernetes API server on the control plane.
- Requires proper configuration with the location and credentials of a Kubernetes cluster.
- Configuration is stored in a file in the home directory, typically at `$HOME/.kube/config`.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/48e0b42c-5a9c-4b8b-8797-3edf10aef4b8)

### Connecting to GKE Clusters

To connect kubectl to a Google Kubernetes Engine (GKE) cluster, use the `gcloud container clusters get-credentials` command. Example:

```bash
$ gcloud container clusters get-credentials [cluster name]
```
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3f13578e-33d6-4cbc-afdb-db40d960b396)

- Credentials are provided by GKE through the gcloud command.
- Configuration information is stored in the `.kube` directory in the home directory.



### Kubectl Syntax

The syntax for kubectl commands consists of the following elements:

- **Command:** Specifies the action (e.g., get, describe, logs, exec).
- **Type:** Defines the Kubernetes object (e.g., Pods, deployments, nodes).
- **Name:** Specifies the object's name.
- **Flags:** Optional flags for special requests or additional information.

Example:

```bash
$ kubectl describe deployment <deployment_name> -o=yaml
```

- `-o=yaml` outputs the result in YAML format.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/a7e12cb2-0c52-4d1f-b97a-d3e3f612b070)
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/ba7fe5b0-cd5a-4b5d-98ba-72e3a7736c47)

### Kubectl Use Cases

Kubectl is versatile and serves various purposes, including:

- Creating, viewing, and deleting Kubernetes objects.
- Exporting configuration files.
- Managing deployments, pods, and services.
- Inspecting cluster information.

### Use Cases and Commands

1. **Running a Container in a Pod:**
   ```bash
   $ kubectl run
   ```

2. **Viewing Running Pods:**
   ```bash
   $ kubectl get pods
   ```

3. **Scaling a Deployment:**
   ```bash
   $ kubectl scale deployment --replicas=3
   ```

   - Uses a Deployment config file to specify the desired state.

4. **Getting Deployment Configuration:**
   ```bash
   $ kubectl get deployments
   $ kubectl describe deployments
   ```

   - Displays the Deployment configuration file in YAML format.

5. **Creating a Kubernetes Cluster on GKE:**
   ```bash
   $ gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2
   ```

6. **Creating a Deployment:**
   ```bash
   $ kubectl create deploy "container"
   ```

   - Creates a deployment with a single pod containing the specified container.

7. **Exposing a Container to the Internet:**
   ```bash
   $ kubectl expose deployment "container-name"
   ```

   - Creates a service and an external load balancer with a public IP address.

8. **Viewing External IP Address:**
   ```bash
   $ kubectl get services
   ```

   - Displays the external IP address assigned to the container.

9. **Creating a GKE Cluster:**
   ```bash
   $ gcloud container clusters create "name"
   ```

   - Creates a cluster on Google Kubernetes Engine.

---
## Introspection Commands in Kubernetes

Introspection in Kubernetes involves gathering information about your application running in a cluster to aid in debugging. Here are four essential commands to help you gather information about your app: `get`, `describe`, `exec`, and `logs`. These commands are particularly useful when focusing on Pods, which are fundamental units in Kubernetes.

### 1. `kubectl get pods`

Use this command to check the status of your Pods. It displays the Pod's phase status, providing a high-level summary of its status:

- **Pending:** Pod has been accepted but is still being scheduled. Container images are not created yet.
- **Running:** Pod is successfully attached to a node, and all containers are created.
- **Succeeded:** All containers have finished running successfully.
- **Failed:** A container terminated with a failure and won't be restarting.
- **Unknown:** State of the Pod cannot be retrieved due to communication errors.
- **CrashLoopBackOff:** One of the containers in the Pod exited unexpectedly even after being restarted.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/0dd9ebc7-6ef9-4c07-8276-4b974dbcf552)

### 2. `kubectl describe pod`

To investigate a Pod in detail, use this command. It provides comprehensive information about the Pod, including labels, resource requirements, volumes, and detailed status for both the Pod and its containers.

Example:
```bash
$ kubectl describe pod [pod_name]
```

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/42d7da4b-c13a-4524-a526-1ff58e9e5157)

### 3. `kubectl exec`

For running commands inside a container, use the `kubectl exec` command. This is helpful for quick tasks like running a ping.

Example:
```bash
$ kubectl exec -it [pod_name] -- /bin/sh
```

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/a9d58f13-20e9-4b09-b214-3d4252aabf5d)

### 4. `kubectl logs`

To view what's happening inside a Pod, especially for troubleshooting, use the `kubectl logs` command. It displays standard output and standard error messages generated by the applications within the container. You can specify a particular container inside a multi-container Pod using the `-c` argument.

Example:
```bash
$ kubectl logs [pod_name]
```

### Note on `kubectl exec` for Interactive Shell

In some cases, you may need to work inside a Pod, such as installing additional tools. You can launch an interactive shell using the `-it` switch, connecting your shell to the container. However, it's not a best practice to install software directly into a container. Instead, consider building container images with the necessary software and redeploy them for long-term solutions.

Example:
```bash
$ kubectl exec -it [pod_name] -- /bin/sh
```

The `-i` argument tells kubectl to pass the terminal’s standard input to the container, and the `-t` argument tells kubectl that the input is a TTY. The interactive shell allows you to diagnose issues interactively.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/c50e8042-0135-44bc-814e-59d6bafe30df)

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/b336e09a-b16f-454b-a092-84b28fcad23f)
