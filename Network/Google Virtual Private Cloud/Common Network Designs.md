# Enhancing Availability and Globalization in Google Cloud

## Enhancing Availability:

If your application demands enhanced availability, deploying two virtual machines across multiple zones within the same subnet is a recommended strategy. By utilizing a single subnet with a specific rule (e.g., 10.2.0.0/16), you can allocate virtual machines to distinct zones within that subnet. This approach improves availability without introducing additional complexities to the security setup.

**Key Points:**
- Deploy two virtual machines across multiple zones in the same subnet for enhanced availability.
- Utilize a single subnet with specific rules to allocate virtual machines to distinct zones.
- Improve availability without complicating the security setup.

## Globalization:

While the previous design distributed resources across various zones within a single region, opting to distribute resources across different regions offers an even higher level of independence from failures. This strategy provides isolation against a variety of infrastructure, hardware, and software failures, resulting in resilient systems with resources strategically placed across diverse failure domains.

**Key Points:**
- Distribute resources across different regions for a higher level of independence from failures.
- Isolate against infrastructure, hardware, and software failures.
- Create resilient systems with resources strategically placed across diverse failure domains.

## Cloud NAT for Controlled Internet Access:

Assigning internal IP addresses to VM instances whenever feasible is advisable. Google Cloud offers Cloud NAT, a managed network address translation service, to facilitate this. Cloud NAT allows the provisioning of application instances without public IP addresses while enabling controlled and efficient internet access. This setup enables private instances to access the internet for essential tasks like updates, patching, and configuration management.

**Key Points:**
- Assign internal IP addresses to VM instances for controlled internet access.
- Use Cloud NAT for provisioning application instances without public IP addresses.
- Enable private instances to access the internet for essential tasks securely and efficiently.
