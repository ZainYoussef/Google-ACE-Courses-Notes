# Google Cloud HTTP(S) Load Balancing Overview

Google Cloud HTTP(S) Load Balancing is a sophisticated solution implemented at the edge of Google's global network in Points of Presence (PoP) around the world. It operates as a Layer 7 load balancer, functioning at the application layer, and serves as a global load balancer for both HTTP and HTTPS traffic. Here is an overview of its key characteristics and components:

## Key Features:

1. **Layer 7 Load Balancer:**
   - Operates at the application layer of the OSI model.
   - Provides advanced capabilities for handling HTTP and HTTPS traffic.

2. **Global Load Balancer:**
   - Balances user traffic globally.
   - Utilizes Google's extensive global network infrastructure.

3. **Port Configuration:**
   - HTTP traffic is load balanced on port 80 or 8080.
   - HTTPS traffic is load balanced on port 443.

## Traffic Flow:

1. **User Request:**
   - User traffic is directed to the closest Point of Presence (PoP) to the user.

2. **Global Load Balancing:**
   - Load balancing occurs over Google's global network.

3. **Backend Selection:**
   - The request is then directed to the closest backend that has sufficient available capacity.

## Configuration Flow:

- **Global Forwarding Rule → Target Proxy → URL Map → Backend Service**

### Components:

1. **Global Forwarding Rule:**
   - Directs incoming requests to the appropriate target proxy.

2. **Target Proxy:**
   - Determines how to handle incoming requests and forwards them to the correct URL map.

3. **URL Map:**
   - Defines how to route requests to the appropriate backend service based on path rules and host rules.

4. **Backend Service:**
   - Specifies how traffic is distributed among its associated backends.

## Use of Ports:

- **HTTP Traffic:** Load balanced on port 80 or 8080.
- **HTTPS Traffic:** Load balanced on port 443.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/725ee183-7e42-4d97-b895-17fba73e1386)

## Configuration Steps:

1. **Global Forwarding Rule:**
   - Configured to define how global traffic should be directed.

2. **Target Proxy:**
   - Specifies how to handle and forward incoming requests.

3. **URL Map:**
   - Defines rules for routing requests based on paths and hosts.

4. **Backend Service:**
   - Specifies the backend instances and how traffic should be distributed.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/2abe8604-4683-4e8c-ad37-dc1926f66e33)

---
# Google Cloud Cross-Region Load Balancing and Content-Based Load Balancing

## Cross-Region Load Balancing:
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/41f8f536-6295-45c6-9715-e8149085ed95)

In Google Cloud, cross-region load balancing enables a project to have a single global IP address, allowing users to access it from different locations such as North America and EMEA (Europe, the Middle East, and Africa). Here's an overview of how cross-region load balancing works:

1. **Global Forwarding Rule:**
   - Incoming requests are directed to a global forwarding rule.

2. **Target HTTP Proxy:**
   - The global forwarding rule directs requests to the target HTTP proxy.

3. **URL Map:**
   - The target HTTP proxy checks the URL map to determine which backend service should handle the request.

4. **Backend Service:**
   - The project has a single backend service with two back ends—one in US Central 1A and one in Europe West 1D.
   - Each backend consists of a managed instance group.

5. **Load-Balancing Decision:**
   - The load-balancing service determines the approximate origin of the request from the source IP address.
   - It considers the locations of instances, their capacity, and current usage.

6. **Traffic Distribution:**
   - If instances closest to the user have available capacity, the request is forwarded to those instances.
   - Incoming requests are evenly distributed across all available backend services and instances in a given region.

7. **Fallback to Next Closest Region:**
   - If there are no healthy instances with available capacity in a region, the load balancer sends the request to the next closest region with available capacity.

8. **Cross-Region Load Balancing:**
   - This approach ensures efficient distribution of traffic across regions based on proximity and availability.

## Content-Based Load Balancing:

Content-based load balancing is a specialized form of HTTP load balancing that allows traffic to be split between backend services based on content types, such as web or video traffic. Key points include:
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/006aea25-90b5-4333-adc9-2555a069466d)

1. **Type Determination:**
   - The load balancer examines the URL header of the request to determine the type of traffic (web or video).

2. **Backend Services:**
   - There are two backend services—one for web traffic and one for video traffic.

3. **Traffic Routing:**
   - If the request is for a video, it is sent to the backend video service.
   - For other types of requests, the load balancer sends the traffic to the web service backend.

4. **Separation of Traffic:**
   - This separation allows for different handling and caching strategies for web and video traffic.

5. **Single Global IP Address:**
   - All of this is achieved using a single global IP address, simplifying user access to the application.
---
# Google Cloud HTTP(S) Load Balancer, SSL Certificates, and Network Endpoint Groups (NEGs)

Google Cloud's HTTP(S) Load Balancer is a powerful service that operates at the edge of Google's network, distributing user traffic to the closest available backend with sufficient capacity. Let's explore some key aspects of HTTP(S) Load Balancer, SSL certificates, and Network Endpoint Groups (NEGs).

## HTTP(S) Load Balancer:

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/fc904a2e-5249-4633-8ab3-99c524417c42)

1. **Termination Point for SSL Sessions:**
   - HTTPS Load Balancer terminates SSL sessions at the load balancer.
   - Client SSL sessions conclude at the load balancer, reducing the load on backend instances.

2. **Target HTTPS Proxy:**
   - HTTPS Load Balancer uses a target HTTPS proxy.
   - It requires at least one signed SSL certificate installed on the target HTTPS proxy.

3. **SSL Certificate Requirement:**
   - An HTTPS Load Balancer necessitates a valid SSL certificate for secure communication.
   - SSL certificates help establish secure connections with clients.

4. **QUIC Transport Layer Protocol:**
   - HTTP(S) Load Balancers support the QUIC transport layer protocol.
   - QUIC enhances the performance and security of web applications.

## Use Case: Dynamic and Static Content Separation:

- A common use case involves segregating traffic based on content type:
  - **Dynamic Content:** Requests for dynamic content, such as data, are directed to a backend service.
  - **Static Content:** Requests for static content, like images, are sent to a backend bucket.

## Network Endpoint Groups (NEGs):

- Network Endpoint Groups are configuration objects specifying a group of backend endpoints or services. Here are some types of NEGs:

1. **Zonal NEG:**
   - Tied to a specific zone.
   - Suitable for regional deployments.

2. **Internet NEG:**
   - Used for internet-facing services.
   - Appropriate for scenarios where backend instances are not in Google Cloud.

3. **Serverless NEG:**
   - For serverless environments.
   - Suitable for Cloud Functions or Cloud Run services.

4. **Hybrid Connectivity NEG:**
   - Used in hybrid cloud setups.
   - Supports connections across on-premises and cloud environments.

5. **Private Service Connect NEG:**
   - For use with Google's Private Service Connect feature.
   - Enables private connectivity between services.

