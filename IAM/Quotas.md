# Google Cloud Quotas and Limits

Google Cloud projects are subject to quotas or limits to control the amount of resources that can be created or used. These quotas fall into the following categories:

1. **Allocation Quotas:**
   - Define how many resources can be created in a project.
   - Example: A project may be limited to having 15 Virtual Private Cloud (VPC) networks.

2. **Rate Quotas:**
   - Govern how quickly API requests can be made in a project.
   - Example: A limit of 5 administrative actions per second per project when using the Cloud Spanner API.

3. **Regional Quotas:**
   - Specify how many resources can be created in a particular region.
   - Example: A limit of 24 Central Processing Units (CPUs) per region.

## Purpose of Quotas

Quotas exist for several reasons:

- **Prevent Runaway Consumption:**
  - Mitigate excessive resource usage, especially in the event of errors or malicious attacks.

- **Avoid Billing Spikes:**
  - Prevent unexpected billing spikes by placing limits on resource creation.

- **Consider Resource Size:**
  - Ensure that the size of resources aligns with actual needs and requirements.

## Important Considerations

- Quotas represent the maximum allowable amount of resources for a specific type but do not guarantee their availability at all times.

