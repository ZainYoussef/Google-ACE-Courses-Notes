# Compute Engine Overview

**Compute Engine: Infrastructure as a Service (IaaS)**

Google Compute Engine (GCE) is a part of Google Cloud that enables users to create and manage virtual machines (VMs) on Google's infrastructure. Here's an overview of key features and concepts related to Compute Engine:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/fa3a256e-e295-455f-8408-1a1cd790bb06)

## Key Features:

### 1. **Virtual Machines (VMs):**
   - VMs are created and run on Google's infrastructure.
   - Supports both Linux and Windows servers.
   - Offers predefined or customized VM instances based on vCPU, memory, and disk size requirements.
   - Provides images, either predefined by Google or customized by users.

### 2. **Access to VMs:**
   - VMs can be accessed using SSH for Linux and RDP (Remote Desktop Protocol) for Windows.
   - SSH requires a key pair, and RDP requires setting a Windows password.
   - Firewall rules are needed to allow communication on specific ports (e.g., TCP 22 for SSH, TCP 3389 for RDP).

### 3. **Machine Types:**
   - Predefined Machine Types: E.g., general purpose, compute-optimized, memory-optimized, and accelerator-optimized.
   - Custom Machine Types: Allows users to define VM configurations based on specific resource needs.

### 4. **Storage Options:**
   - **Boot Disk:** Attached to the VM, contains the operating system.
   - **Persistent Disks:** Not attached to the VM, can be resized. Three types: standard (HDD), SSD, and balanced (SSD).
   - **Local SSDs:** Physically attached to the VM, do not survive a reset.
   - **RAM Disks (tmpfs):** Temporary file storage in memory.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/6c9f6436-a354-4287-b0b8-890ebf8a894e)

### 5. **Compute Engine Pricing:**
   - Billed by the second with a minimum of 1 minute, even if the VM is not actively used.
   - Discounts available, including sustained-use discounts, committed-use discounts, and savings with preemptible and spot VMs.

### 6. **Preemptible & Spot VMs:**
   - **Preemptible VMs:** Can be preempted and terminated by Google if resources are needed elsewhere.
   - **Spot VMs:** Similar to preemptible VMs but with no maximum runtime.

### 7. **gcloud Command:**
   - Google Cloud SDK command for managing resources.
   - Example: `$ gcloud compute instances move` for moving a VM to a new zone.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/ed291f35-e5a1-4279-ac89-3e44912df8a1)
