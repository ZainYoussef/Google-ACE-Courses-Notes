
# Identity and Access Management (IAM)

IAM in Google Cloud involves managing who can do what on which resources. The key IAM objects include:

- Organization
- Folders
- Projects
- Resources
- Roles
- Members

## IAM Roles

Roles define the "WHAT" in IAM. There are three types:

1. **Basic Roles**: Owner, Editor, Viewer, Billing Admin (affect all resources in a Google Cloud project).

2. **Predefined Roles**: More specific predefined actions.

3. **Custom Roles**: Even more specific, applied at the organization node and the project. They provide the least privilege and are not managed by Google.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/b0ff278b-3a53-4cc8-a41d-69380304903f)

IAM policies can be applied to service accounts as they are considered principles. Predefined roles come with several permissions to make them meaningful.

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3c386221-1c4f-473b-b4b6-cc3e2fb84e97)

## IAM Members

Members represent the "WHO" in IAM. They can be:

- Google Accounts
- Service Accounts
- Google Groups
- Google Workspace Domains
- Cloud Identity Domains

Google Accounts are for individuals, while Service Accounts belong to applications. Google Groups and Google Workspace Domains represent collections of accounts in different contexts.

## IAM Policies

Policies consist of bindings that bind members to roles. Roles are named lists of permissions. An allow policy grants permissions, controlling access to Google Cloud resources. Deny policies set guardrails on access, preventing certain principals from using specific permissions.

## IAM Conditions

IAM Conditions enforce conditional, attribute-based access control for resources, granting access only if configured conditions are met.

## Organization Policies

Organization policies configure restrictions for an organization, controlling project creation, user permissions, and resource access.

## Integration with Other Systems

- **Google Cloud Directory Sync**: Synchronizes users and groups from existing Active Directory or LDAP systems with Cloud Identity, using the same usernames and passwords.

- **Single Sign-On Authentication**: Allows using existing identity systems to authenticate users to Google Cloud, simplifying the sign-in process and improving security.

---
