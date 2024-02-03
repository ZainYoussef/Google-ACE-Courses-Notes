# Cloud SQL: Fully Managed Relational Databases

**Overview:**
Cloud SQL is a fully managed database service designed for hosting structured relational databases. It supports MySQL, PostgreSQL, or Microsoft SQL Server databases.

**Key Features:**
- **High Performance and Scalability:**
  - Up to 64 TB of storage capacity, 60,000 IOPS, and 624 GB of RAM per instance.

- **High Availability (HA):**
  - Configured with a primary instance and a standby instance synchronously replicated to each zone.

- **Connection Options:**
  - Offers various connection options, including private IP connections for enhanced security and performance.

- **Cost-Effective Solution:**
  - Suitable for relational database needs without the requirement for horizontal scaling or a globally available system like Cloud Spanner.
---
**HA Configuration:**
- Cloud SQL provides a high availability (HA) configuration with a primary instance and a standby instance. Users connect to the primary instance, and all writes are made there. In case of a primary instance failure, the standby instance is promoted, and users are automatically rerouted (failover).

**Backups and Point-in-Time Recovery:**
- Cloud SQL provides automated and on-demand backups with point-in-time recovery. This allows restoring the database to a specific point in time, even after a primary instance failure.

**Scaling Options:**
- You can scale up a Cloud SQL instance by increasing CPU cores and memory, though this requires a machine restart. Additionally, scaling out can be achieved by adding read replicas, which are copies of the primary instance used to improve performance and availability.

**Connecting to Cloud SQL:**
- [Details on connecting to Cloud SQL.]

**Choosing Cloud SQL:**
- For relational data workloads that don't involve analytics, the choice typically comes down to Cloud Spanner or Cloud SQL. If horizontal scaling or a globally available system isn't needed, Cloud SQL is a cost-effective solution.
