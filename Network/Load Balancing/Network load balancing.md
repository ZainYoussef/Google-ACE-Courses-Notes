# Regional Load Balancing in Google Cloud

**Regional Load Balancer Overview:**

Regional Load Balancer in Google Cloud is a non-proxied load balancing service where all traffic is passed through the load balancer without being proxied. Unlike a global load balancer, a regional load balancer is limited to balancing traffic between VM instances within the same region.

**Key Characteristics:**

1. **Regional Scope:**
   - Limited to VM instances within the same region.
   - Traffic is balanced regionally, ensuring low-latency communication within a specific geographic area.

2. **Non-Proxied Load Balancing:**
   - All traffic passes through the load balancer without being proxied.
   - Direct routing of traffic to backend instances.

3. **Traffic Balancing:**
   - Balances traffic between VM instances in the same region.

4. **Architecture Approaches:**
   - Two common approaches for the architecture of a regional load balancer:
      - **Back-End Service-Based Approach:** Involves defining back-end services that specify how the load balancer behaves and distributes traffic across associated instance groups.
      - **Target-Pool-Based Approach:** Utilizes target pools, which are collections of instances that receive incoming traffic from forwarding rules.

**Use Cases:**

- Ideal for scenarios where applications are deployed within a specific region, and low-latency communication between instances is crucial.

**Comparison with Global Load Balancer:**

- Contrary to global load balancers that distribute traffic globally across regions, regional load balancers focus on balancing traffic within a designated region.

**Advantages:**

- Low-latency traffic routing within the same region.
- Simplified architecture for applications with regional deployments.
- Non-proxied load balancing for direct communication between clients and backend instances.

**Considerations:**

- Limited to VM instances within the same region.
- Suited for applications with regional requirements rather than global distribution.

