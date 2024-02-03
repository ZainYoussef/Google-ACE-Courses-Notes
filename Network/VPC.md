# Virtual Private Cloud (VPC) in Google Cloud

A Virtual Private Cloud (VPC) is a secure and isolated private cloud computing model hosted within a public cloud infrastructure, such as Google Cloud. It provides a private, secured virtual network for users to execute code, store data, host websites, and perform various tasks. Each Google Cloud project comes with a default network containing subnets, routes, and firewall rules.

## Key Features and Benefits of VPCs:

- **Security:** VPCs offer a secure and isolated virtual network environment.
  
- **Data Isolation:** Maintains the data isolation characteristic of private cloud computing.

- **Scalability:** Utilizes the advantages of public cloud scalability.

- **Convenience:** Offers the convenience of public cloud services.

## VPC Networks and Their Role:

VPC networks play a crucial role in facilitating connections between Google Cloud resources and both internal and external entities, including the internet. Key components include:

- **Network Segmentation:** Dividing the network into segments.
  
- **Firewall Rules:** Controlling access to instances using firewall rules.

- **Static Routes:** Directing traffic to specific destinations.

## Example on Subnets and VPCs:

Consider a scenario with a VPC in Google Cloud's us-east1 region. Two Compute Engine virtual machines (VMs) are created within this VPC, even in different availability zones. These VMs, part of the same subnet, can communicate as if they are on the same local network.

- **Flexibility Across Zones and Regions:** Subnets provide flexible network layouts spanning zones and regions while maintaining connectivity and resource sharing.

## Subnets:

A subnet is a segmented portion of an IP network, allowing the partitioning of an IP network into smaller, manageable sections. Key points:

- VPC Networks are applied at the global level.
  
- VPC Subnets are applied at the region level.

- Subnet Size: The subnet size can be increased by expanding the range of subnet IP addresses (e.g., from /20 to /16).

## Sharing VPC Networks:

Google VPCs can be connected to other networks in various ways:

- **Over the Internet (Using VPN):** Utilizing Cloud Router for dynamic exchange of route information.
  
- **Direct Peering:** Exchanging traffic between networks by placing the router in the same public data center as a Google Point of Presence (PoP).

- **Carrier Peering:** Providing direct access to an on-premise network through a service provider network.

- **Dedicated Interconnect:** Allowing one or more direct connections to Google, covered by a 99.99% SLA.

- **Partner Interconnect:** Connectivity between an on-premises network and a VPC network through a supported service provider, covered by a 99.99% SLA.

# Virtual Private Cloud (VPC) Objects in Google Cloud

## Projects, Networks, and Subnetworks

### Projects:

- A project contains the entire network infrastructure.
  
- Default quota for each project is 15 networks (VPC networks).
  
- Networks can be shared between projects, with consideration for non-overlapping subnet IPs.

- Networks can be peered with networks in other projects.

- Networks are a construct of all IP addresses and services within that network.

### Networks:

- Networks are global entities in Google Cloud.

- Three types of networks:
  1. **Default:** Automatically created for each new project.
  2. **Auto Mode:** Auto-generates subnets with predefined IP ranges.
  3. **Custom Mode:** Allows manual creation of subnets with user-defined IP ranges.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/6aa3aad5-d47d-4166-bafd-74774b7dbfc6)

- Auto mode networks can be converted to custom mode, but not vice versa.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3fad78e4-4f5e-4a2a-be56-0cd59ffca43e)

A & B are in the same network - use internal ip address

C & D are not in the same network - use external ip address

---
### Subnets:

- Subnets are regional entities in Google Cloud.

- Subnets can extend across zones in a region.

- Subnets are defined by an IP range, with four reserved IP addresses in the primary range.

- Subnet IP range can be expanded to make more room for instances (new range must be larger, prefix length smaller).

- Firewall rules can be applied within subnets to restrict and protect instances.

## IP Addresses

- Each virtual machine (VM) has two IP addresses: internal and optional external.

- External IP addresses can be ephemeral (from a pool), reserved (static), or user-assigned.

- External IP is unknown to the VM's OS.

## Routes and Firewall Rules

### Routes:

- Maps IP ranges to destinations.

- Every network has routes for instances to send traffic to each other and a default route for packets outside the network.

### Firewall Rules:

- Applied to the network as a whole; connections are allowed or denied at the VM instance level.

- Rules are stateful, and there are default and implied rules.
  
- Implied rules cannot be deleted or changed (allow all egress, deny all ingress with low priority).

## Network Pricing

- Pricing is based on egress data volume and IP address usage.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/0c6d09ea-7b46-4f35-918f-007fe62745b0)
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/1f1a218b-1672-451c-9754-adc72b6837bd)

## gcloud Commands

```bash
gcloud compute networks create vpc-demo --subnet-mode custom

gcloud compute networks subnets create vpc-demo-subnet2 \
  --network vpc-demo --range 10.2.1.0/24 --region us-central1
```
