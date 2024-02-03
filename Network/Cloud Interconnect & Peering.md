# Networking Connectivity Options in Google Cloud

Google Cloud offers a range of networking connectivity options to cater to various needs. Here's an overview of key connectivity options:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/568741a8-8b66-41de-8904-ea6fd9170be1)

## Layer 3 Connection (Peering):
- **Purpose:** Provides access to G Suite services.
- **Connectivity Type:** Layer 3.
- **Communication:** Establishes private connections for accessing G Suite services.

## Layer 2 Connection (Interconnection):
- **Purpose:** Uses VLANs and provides connectivity to internal IP addresses.
- **Connectivity Type:** Layer 2.
- **Communication:** Utilizes VLANs for connectivity, allowing communication to internal IP addresses.

## Dedicated Connection:
- **Purpose:** Direct connection to Google's network.
- **Connectivity Type:** Direct physical connection.
- **Requirements:** On-premise network must physically meet Google's network in supported colocation facility locations.

## Shared Connection:
- **Purpose:** Connects to Google's network through a partner.

## Google's Requirements and Connectivity:
- **Dedicated Interconnect:** For direct physical connection, meeting Google's network in supported colocation facility locations.
- **Direct Peering:** For connectivity to Google properties like YouTube, meeting Google's requirements.

--- 
# Dedicated Interconnect and Partner Interconnect in Google Cloud

## Dedicated Interconnect:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/9b96c063-5fd2-4042-9675-88a4591a053a)

Dedicated Interconnect provides a direct physical connection from on-premise networks to Google Cloud. Key features include:

- **Physical Connection Requirement:** On-premise network must physically meet Google's network in supported colocation facility locations.

- **BGP Session:** Exchange of routes between networks requires a BGP (Border Gateway Protocol) session between the on-premise router and the Cloud Router in Google Cloud.

- **SLA (Service Level Agreement):**
  - **99.9% Availability:** Suitable for non-critical applications tolerating some downtime.
  - **Requirements:**
    - At least two Interconnect connections.
    - At least one Cloud Router.
    - Each Interconnect connection must be attached to the Cloud Router.

  - **99.99% Availability:**
    - At least four Dedicated Interconnect connections, two in one metro and two in another.
    - At least two Cloud Routers in distinct Google Cloud regions.
![999-availability](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/b9ba70b3-b9cf-4845-9fd3-ce89df0510c5)
---
## Partner Interconnect:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/07f3aea8-f6bd-4243-b4e6-f300fffd7b83)

Partner Interconnect provides connectivity from on-premise to Google Cloud through a supported service provider. Features include:

- **Use Case:** Useful if on-premise cannot physically reach the dedicated colocation facility.
  
- **Service Provider Connection:** Service providers have existing physical connections to Google's network colocation facilities.

- **SLA (Service Level Agreement):**
  - **99.9% Availability:**
    - At least two VLAN attachments in a single Google Cloud region, in separate edge availability domains.
    - Attachments must connect in one metropolitan area.
    - At least one Cloud Router connected to both VLAN attachments.
![999-layer2](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/7543d9f6-3a6b-44f3-968e-52cebc9c0f5c)

  - **99.99% Availability:**
    - At least four VLAN attachments, two per Google Cloud region.
    - VLAN attachments in one region connect to a Partner Interconnect connection in one metro, and attachments in the other region connect to a connection in another metro.
    - Global dynamic routing mode for the VPC network.
    - One or more routers in on-premise network based on hardware and availability requirements.
--- 
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/cac89351-3f88-43be-863b-539a20f277d7)
---
#Choosing network service:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/115f8267-9e59-4749-b782-14008b63d769)
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/5d0fe897-f3c0-4aed-8d12-262021c1c363)
