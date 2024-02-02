# Service Account in Google Cloud

A **service account** is a special type of account designed for applications, serving as an identity for server-to-server interactions. It is utilized to authenticate and authorize applications to access Google Cloud resources.

Service accounts are authenticated using cryptographic keys. Google-managed service accounts have two key pairs: a public key and a private key. The public key is stored in the Google Cloud Platform (GCP) metadata server, while the private key is securely stored by Google. When a service account requests access to a Google Cloud resource, it presents its public key, which is then verified by the GCP metadata server to grant access if valid.


## Service Account Management

Service accounts need to be managed, and the process includes:

1. **Creating a Service Account**: Navigate to IAM & admin → Service accounts.

2. **Assigning Roles**: A service account is an identity and can be given roles to define its permissions. For instance, providing a service account access to a compute instance through the InstanceAdmin role grants specific permissions.


## User-Created, Built-In, and Google Cloud APIs Service Accounts

There are three types of service accounts:

1. **User-Created Service Accounts**: Created by users and can be used to access Google Cloud resources.

2. **Built-In Service Accounts**: Created by Google for specific purposes, such as the Compute Engine default service account.

3. **Google Cloud APIs Service Accounts**: Used by Google Cloud APIs to access resources on your behalf.

It's important to note that if a user is granted access to a service account and the service account has specific permissions (e.g., through predefined roles like InstanceAdmin), the user can act as that service account, granting all associated permissions.


![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/0fbf166a-4dd1-4b2a-aadc-e3ff16d8fb4a)

---

