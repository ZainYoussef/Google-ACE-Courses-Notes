# Google Cloud CDN (Content Delivery Network)

Google Cloud CDN, short for Content Delivery Network, is a service that utilizes Google's widely distributed edge points of presence to enhance content delivery for HTTP(S) load-balanced applications. It stores load-balanced content in proximity to users, improving response times and reducing serving costs through content caching at Google's network.
![image](https://github.com/ZainYoussef/Google-ACE-Courses-Notes/assets/85849430/9d64c7ba-56a7-47b3-8785-e8e46bb50f89)

## Key Features:

1. **Distribution Strategy:**
   - Google's globally distributed edge locations.
   - Proximity caching for HTTP(S) load-balanced content.

2. **Setup Ease:**
   - Enabling Cloud CDN is simple – just a checkbox during HTTP(S) load balancer backend setup.

3. **Scenario Illustration:**
   - Consider an HTTP(S) load balancer with two types of backends:
     - Managed VM instance groups in us-central1 and asia-east1.
     - A Cloud Storage bucket in us-east1.
   - A URL map guides content allocation based on backend suitability.

4. **Cache Mechanism:**
   - **Cache Miss Scenario:**
     - User in San Francisco makes the initial request.
     - If the San Francisco cache site cannot fulfill the request (cache miss), it seeks the content from a nearby cache or directs the request to the appropriate backend.

5. **Cache Modes:**
   - **USE_ORIGIN_HEADERS:**
     - Mandates valid cache directives and headers in origin responses.
   - **CACHE_ALL_STATIC:**
     - Automatically caches static content lacking no-store, private, or no-cache directives.
     - Caches valid caching directive-endowed origin responses.
   - **FORCE_CACHE_ALL:**
     - Unconditionally caches responses, disregarding origin-set cache directives.
     - Caution is advised with shared backends to avoid caching private or user-specific content like dynamic HTML or API responses.

Google Cloud CDN offers flexibility in caching strategies, allowing users to optimize content delivery based on their specific needs and caching policies.
