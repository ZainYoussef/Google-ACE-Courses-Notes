# Cloud Firestore: Fully Managed, Serverless, Cloud-Native NoSQL Database

**Overview:**
Cloud Firestore is a fast, fully managed, serverless, cloud-native, NoSQL document database that simplifies storing, syncing, and querying data for mobile, web, and IoT apps at a global scale.

**Key Features:**
- **Data Organization:**
  - Data stored in documents and organized into collections.
  - Sorting options and combined filtering available.

- **Data Synchronization:**
  - Utilizes data synchronization to update data on any connected device.
  - Caches actively used data, enabling read, write, listen, and query operations even offline. Syncs local changes to Firestore when the device is back online.

**Pricing Model:**
- Charged for each document read, write, and delete.
- Queries charged at one "document read" per query.
- Charges for storage consumption and certain types of network bandwidth.
- Free daily quota includes 50,000 document reads, 20,000 document writes, 20,000 document deletes, and 1 GB of stored data.

**Firestore Modes:**
- **Datastore Mode:**
  - Backward compatible with Cloud Datastore.
  - Improved storage layer with the same system behavior as Cloud Datastore.
  - Compatible with Datastore applications, strong consistency, and no entity group limits.

- **Native Mode:**
  - Introduces new features such as a strongly consistent storage layer, real-time updates, and a collection and document data model.
  - Access to new features requires using Cloud Firestore in Native mode.
  - Suggested usage: Datastore mode for new server projects, Native mode for new mobile and web apps.
  - Existing Cloud Datastore users will be automatically upgraded to Cloud Firestore in the future.

**Differences between Datastore Mode and Native Mode:**
| Feature            | Datastore Mode                 | Native Mode                          |
|--------------------|--------------------------------|--------------------------------------|
| Storage Layer      | Cloud Firestore                | Cloud Firestore                      |
| System Behavior    | Same as Cloud Datastore        | New features, strongly consistent    |
| Queries            | Strongly consistent             | Strongly consistent                  |
| Transactions       | No limit                       | No limit                             |
| Client Libraries   | Cloud Datastore client libraries| Cloud Firestore client libraries     |

**Benefits of Cloud Firestore:**
- **Scalable:**
  - Can scale to support applications from small to large.

- **Flexible:**
  - Document data model allows flexible data storage.

- **Durable:**
  - Uses automatic multi-region replication for data safety and availability.

- **Secure:**
  - Supports strong consistency and ACID transactions for data integrity.

- **Real-Time:**
  - Provides real-time updates for users to see the latest data.

**When to Use Cloud Firestore:**
- Good choice for applications that need to store and sync data across multiple devices, support real-time updates, scale to meet changing demands, and be highly available and durable.

**Cloud Firestore vs. Cloud Bigtable:**
- Both NoSQL databases from Google Cloud Platform.
- Cloud Firestore is suitable for applications that need to store and sync data across devices, support real-time updates, and be easy to use.
- Cloud Bigtable is suitable for applications that need to store large amounts of data, handle high throughput and low-latency queries, and be highly scalable.

---
Choosing Firestore:
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/99ceed31-a0fd-48d7-a3b8-c48c92d6e417)
