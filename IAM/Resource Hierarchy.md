

# Resource Hierarchy in Google Cloud

The resource hierarchy in Google Cloud consists of four levels:

1. **Organization Node**
2. **Folders**
3. **Projects**
4. **Resources**

Policies can be applied to this hierarchy, and they are inherited downwards.

## Organization Node

- The topmost node of the resource hierarchy.
- Policies applied at this node affect the entire resource hierarchy through inheritance.
- Two special roles at this node:
  - Organization Admin
  - Project Creator

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/3776d6ce-b79f-4cae-9ceb-e99d4da4e6b9)

### Special Roles

- **Organization Admin**: Does not have permission to create projects.
- **Project Creator**: Can create projects within the organization.

## Folders

- Used for organizing and managing resources.
- Must belong to an organization to be created.

## Projects

- Resources belong to one project.
- Projects have:
  - **Project ID**: Immutable, globally unique, can be changed by you during creation.
  - **Project Name**: Mutable, not unique.
  - **Project Number**: Immutable, globally unique, assigned by Google.
 
---

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/aeac2cc5-6ca8-4c8a-ad7c-0f8e033886b1 )

![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/a7054789-c733-4fbd-ac0a-31705c6401fa)

---
