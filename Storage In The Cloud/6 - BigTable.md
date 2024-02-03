

# Cloud Bigtable: Fully Managed NoSQL Big Data Database

**Overview:**
Cloud Bigtable is Google's NoSQL big data database service, offering petabyte-scale, very low latency, and fully managed capabilities. It is suitable for applications not requiring transactional consistency.

**Key Features:**
- **Scalability and Low Latency:**
  - Fully managed NoSQL database with petabyte-scale and very low latency.
  - Great for operational and analytical applications, including IoT, user analytics, financial data analysis, and machine learning.

- **Integration with Big Data Tools:**
  - Integrates easily with popular big data tools like Hadoop, Cloud Dataflow, and Cloud Dataproc.
  - Supports the open-source industry-standard HBase API.

**Data Storage Model:**
- Cloud Bigtable stores data in massively scalable tables, each a sorted key/value map.
- Tables are composed of rows, each typically describing a single entity.
- Columns contain individual values for each row.
- Rows are indexed by a single row key.
- Columns related to each other are grouped into a column family.
- Each column is identified by a combination of the column family and a column qualifier.
- Each row/column intersection can contain multiple cells or versions at different timestamps.
- Tables are sparse; cells without data do not take up space.


![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/9b8d1b66-b7e2-4e59-a8e2-f041fe620dcb)

---
![bigtable-architecture](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/30bad62e-dd18-4727-946d-b2e7e67bef2a)

**Overall Architecture:**
- Cloud Bigtable tables are sharded into blocks of contiguous rows called tablets.
- Tablets are stored on Colossus, Google's file system, in SSTable format.
- SSTable provides a persistent, ordered, immutable map from keys to values.
- Cloud Bigtable adjusts to specific access patterns to distribute workloads evenly among nodes.
- Throughput scales linearly; adding nodes results in a linear scale of throughput performance.

**When to Use Cloud Bigtable:**
- Good choice if needing to store more than 1 TB of structured data, having a high volume of writes, requiring read/write latency of less than 10 milliseconds with strong consistency, or needing a storage service compatible with the HBase API.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/258b91f8-17bf-40c7-bc7d-38f2d6ac6517)
