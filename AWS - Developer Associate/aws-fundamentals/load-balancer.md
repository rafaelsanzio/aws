# Load Balancer
  - Are servers that forward traffic to multiple servers (EC2 Instances) downstream
  - The idea is that the more users you have, the more the load is going to be balanced across EC2 Instances

  - Why use
    - Spread load across multiple downstream instances
    - Expose a single point of access (DNS) to your application
    - Seamlessly handle failures of downstream instances
    - Do regular health checks to your instances
    - Provide SSL termination (HTTPS) for your websites
    - Enforce stickiness with cookies
    - High availability across zones
    - Separate public traffic from private traffic

### ELB (Elastic Load Balancing)
  - Is a manager load balancer
  - It is integrated with many AWS services

  - Health check
    - Are crucial for LB
    - Enable the LB to know if instances it forwards traffic to are available to reply to requests
    - If the response is not 200 (OK), then the instance is unhealthy

### Types of LB on AWS

  - CLB (Classic Load Balancer)
    - Supports TCP, HTTP and HTTPS
    - Fixed hostname