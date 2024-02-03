# Google Cloud Load Balancers

A load balancer plays a crucial role in distributing user traffic across multiple instances of applications, reducing the risk of performance issues by evenly spreading the load. Google Cloud provides different types of load balancers to cater to various needs.

## Load Balancer Types:

### Global Load Balancers:

1. **Global HTTP(S) Load Balancer:**
   - Distributes HTTP and HTTPS traffic globally.
   - Suitable for users distributed worldwide who access the same application content.

2. **External HTTP(S) Classic Load Balancer:**
   - Classic version for external HTTP(S) traffic distribution.

3. **SSL Load Balancer:**
   - Distributes SSL/TLS traffic globally.

4. **TCP Load Balancer:**
   - Distributes TCP traffic globally.

### Regional Load Balancers:

1. **Regional External HTTP(S) Load Balancing:**
   - Distributes external HTTP(S) traffic within a specific region.

2. **Internal HTTP(S) Load Balancing:**
   - Distributes internal HTTP(S) traffic within a specific region.

3. **Internal TCP Proxy Load Balancing:**
   - Distributes internal TCP traffic within a specific region.

4. **Internal TCP/UDP Load Balancing:**
   - Distributes internal TCP/UDP traffic within a specific region.

5. **External TCP/UDP Load Balancing:**
   - Distributes external TCP/UDP traffic within a specific region.

6. **External Regional TCP Proxy Load Balancing:**
   - Distributes external regional TCP traffic with proxy support.

## Components:

### Backend Service:

- Defines load balancer behavior and how it distributes traffic across associated backend instance groups.
- Supports modern health checks, TCP, SSL, HTTP, HTTPS, HTTP/2, auto-scaling via managed instance groups, connection draining, and configurable failover policies.

### Target Pool:

- Outlines a collection of instances that receive incoming traffic from forwarding rules.
- Load balancer selects an instance from the target pool based on a hash of source and destination IP and port.
- Limited to 50 target pools within a single project.
- Each target pool can only be associated with a single health check.
- All instances within a target pool must reside within the same region.
