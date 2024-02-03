# Cloud Storage: Object Storage Service

Cloud Storage is a service that allows you to store objects, managing data as objects (object storage). Objects are stored in a package containing the binary form of the data and related metadata. Common data stored includes videos, pictures, and audio recordings.

Examples of use cases include serving website content, storing data for archival and disaster recovery, and distributing large data objects to end-users via Direct Download.

Cloud storage files are organized as buckets, where a bucket has a globally unique identifier and location.

Objects inherit the bucket, are immutable (cannot be edited), and can have versions.

## Durability and Availability:

All storage classes provide 11 nines of durability, ensuring data preservation. However, availability varies among classes and location types. Data availability depends on your chosen storage class and location type.

## Cloud Storage Components:

- **Buckets:** Globally unique, non-nested containers for objects.
- **Objects:** Files, documents, videos, etc., stored within buckets, with no minimum size for objects; scalability depends on quota.
- Access data via the `gcloud storage` command, JSON, or XML APIs.

## Access Control:

Access to buckets and objects in a project can be controlled using:
- Identity and Access Management (IAM) roles.
- Access Control Lists (ACLs).
- Signed URLs.
- Signed policy documents.

IAM roles provide broad control, ACLs offer finer-grained control, signed URLs grant time-limited access, and signed policy documents define upload permissions.

### ACLs and Signed URLs:

- **ACLs:** Define who (scope) can perform what actions (permissions) on buckets and objects. Limited to 100 ACL entries.
- **Signed URLs:** Create time-limited URLs that grant read or write access to Cloud Storage resources. Authenticated using a private key associated with a service account.

## Features:

- Use customer-supplied encryption keys to encrypt your data in virtual machines and Cloud Storage.
- Automatically delete or archive objects using Object Lifecycle Management.
- Object Versioning allows keeping multiple versions of the same object.
- You are charged for each version of an object.
- Directory synchronization to sync a VM directory with a bucket.
- Data Import and Export: Supports efficient data import/export, including services like Transfer Appliance, Storage Transfer Service, and Offline Media Import for handling large volumes of data.
- Strong Consistency: Provides strong global consistency for operations.
- Deletion Consistency: Object deletions are strongly consistent.
- Bucket and Object Listing Consistency: Ensures that new buckets or objects immediately appear in their respective lists.

## Storage Classes in Cloud Storage:

| Storage Class | Description                               | Minimum Storage Duration | Retrieval Costs        |
| ------------- | ----------------------------------------- | ------------------------- | ----------------------- |
| Standard      | Frequently accessed (hot data)            | No minimum                | No retrieval costs      |
| Nearline      | Infrequently accessed data                | 30 days                   | Some data access costs  |
| Coldline      | Infrequently accessed data                | 90 days                   | Higher data access costs|
| Archive       | Highly durable storage for archiving      | 365 days                  | Highest data access costs|

![Image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/866fc155-054c-46da-92ef-8d10cff5838b)
![Image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/0e8a93a8-a095-4687-ad4f-644fc85c63fd)

## Access Control List:

An access control list (ACL) is a mechanism to define who has access to your buckets and objects, as well as their level of access. In Cloud Storage, apply ACLs to individual buckets and objects. Each ACL consists of one or more entries, with a permission defining actions and a scope defining who can perform those actions.

![Image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/574141c5-ecb0-448a-be17-544c7938d7d1)

## Versioning:

Administrators have the option to allow each new version to overwrite the older one or keep track of changes by enabling "versioning" within a bucket. If versioning is enabled, Cloud Storage keeps a detailed history of modifications, including overwrites or deletes, of all objects in that bucket. If you don't turn on object versioning, by default, new versions will always overwrite older versions.

## Data Security:

Data traveling between a customer’s device and Google is encrypted by default using HTTPS/TLS (Transport Layer Security).

![Image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/d80e87c6-e298-48de-a7fd-c9bd0146993a)
