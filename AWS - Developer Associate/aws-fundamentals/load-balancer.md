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

  - ALB (Application Load Balancer)
    - Load balancing to multiple HTTP applications across machines (target groups)
    - Load balancing to multiple applications on the same machina (containers)
    - Support for HTTP/2 and WebSocket
    - Support redirects (HTTP and HTTPS)

    - Routing tables to different target groups
      - Based on path in URL
      - Based on hostname in URL
      - Base on Query String, Headers
    
    - ALB are a great fit for micro services & container-based application (Docker & ECS)
    - Has a port mapping feature to redirect to a dynamic port in ECS
    - In comparison, we would need multiple CLB per application

    - Target Groups
      - EC2 instances - HTTP
      - ECS rasks - HTTP
      - Lambda functions - HTTP Request is translated into a JSON event
      - IP Addresses - must be provate IPs

    - ALB can route to multiple target groups
    - Health checks are at the target group level

    - Fixed hostname
    - The application servers don't see the IP of the client directly
  
  - NLB (Network Load Balancer)
    - Forward TCP & UDP traffic to your instances
    - Handle millions of request per seconds
    - Less latencty

    - Has one static IP per AZ, and supports assigning Elastic IP
    - Are used for extreme performance, TCP or UDP traffic
    - Not included in the AWS free tier

    - Target Groups
      - EC2 Instances
      - IP Addresses: must be private IPs
      - Application Load Balancer