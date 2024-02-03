![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/9b4e9487-2155-4983-b4f8-f711b91a594b)
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/be921e0f-a48e-4641-ad90-1a514d3c9625)
# Shared VPC and VPC Network Peering in Google Cloud

## Shared VPC:

**For the Same Organization**

Shared VPC enables you to share a network across several projects within your Google Cloud Platform (GCP) organization. This approach allows an organization to connect resources from multiple projects to a common Virtual Private Cloud (VPC) network, utilizing internal IP addresses.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/a31b8229-2ca4-4c61-a90b-f07036bf68f7)

**Key Points:**
- Shared VPC is designed for organizations within the same GCP organization.
- It allows sharing a network across multiple projects.
- Resources from various projects can connect to a common VPC network.
- Internal IP addresses are used for communication.

## VPC Network Peering:

**For Same or Different Organizations**

VPC Network Peering allows the configuration of private communication across projects, whether they belong to the same or different organizations. This feature facilitates private RFC 1918 connectivity across two VPC networks, enabling communication between them.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3b1a8b9f-ec2a-45a1-97d7-e1605b2cf754)

**Key Points:**
- VPC Network Peering works for projects within the same or different organizations.
- It enables private communication across projects.
- Private RFC 1918 connectivity is established between two VPC networks.
- Connectivity is possible regardless of whether the networks belong to the same project or organization.

