# Google Cloud VPN Connectivity Options

Google Cloud VPN provides various connectivity options to securely connect your Google VPC (Virtual Private Cloud) network to an on-premises network. Let's explore some key aspects of Google Cloud VPN, including classic VPN, High Availability (HA) VPN, and associated configurations:

## Cloud VPN Overview:
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/45ef12c5-2ed2-478e-851e-491fc7b6fcf8)

- **Purpose:** Google Cloud VPN facilitates the secure connection between your Google VPC network and an on-premises network.

- **Classic VPN Topology:**

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/995112c4-6cfe-4be1-aeaa-039e4b97857d)

  - **Components:**
    - Subnets
    - VPC Routing
    - Routing Table
    - Cloud VPN Gateway (Regional External IP)
    - Internet
    - On-Premise VPN Gateway
  - **Requirements:**
    - 2 VPN Gateways (Cloud VPN Gateway and On-Premise Cloud VPN Gateway)
    - 2 VPN Tunnels
  - **SLA:** Provides a 99.9% Service Level Agreement (SLA).
## Configuration Considerations:

- **MTU (Maximum Transmission Unit):** Maximum MTU is 1460.

---
# **HA VPN (High Availability VPN):**
  - **Purpose:** HA VPN is a high-availability Cloud VPN solution that securely connects your on-premises network to your VPC network through an IPsec VPN connection.
  - **SLA:** HA VPN provides a 99.99% Service Level Agreement (SLA).
  - **Configuration:**
    - Regional per VPC
    - Two Interfaces with Separate Public IP Addresses
    - Two Public IP Addresses Automatically Chosen from Different Pools
    - Configurable with Two or Four Tunnels for 99.99% SLA
  - **Recommended Topologies:**
    - HA VPN Gateway to Peer VPN Devices
    - HA VPN Gateway to an AWS Virtual Private Gateway
    - Two HA VPN Gateways Connected to Each Other
   
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/ecf41fe3-bc92-4d66-b05c-86d6765d251f)

  - **99.99% Availability:**
    - Achieved when using 2 Peer VPN Gateways.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/dfe464eb-5987-4766-9b38-113f56617cf6)



## High Availability VPN (HA VPN) Configuration:
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3432ccf3-6a66-434f-9976-6171798c2f79)


HA VPN is designed to provide high availability and reliability. To achieve the 99.99% SLA, proper configuration of two or four tunnels from the HA VPN gateway to the peer VPN gateway or another HA VPN gateway is essential. Configurations can include an HA VPN gateway to peer VPN devices, an HA VPN gateway to an AWS virtual private gateway, or two HA VPN gateways connected to each other.

Google Cloud VPN, with its classic and HA VPN options, ensures secure and reliable connectivity, catering to different deployment scenarios and availability requirements.
