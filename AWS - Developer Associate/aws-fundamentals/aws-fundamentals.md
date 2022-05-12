# AWS Fundamentals

    - Scalability
      - Scalability means that an application / system can handle greater loads by adapting
      - There are two kinds of scalability: Vertical and Horizontal
      - Scalability is linked but different to High Availability

      - Vertical
        - Means increasing the size of the instance
        - Example your app runs on t2.micro and scale to t2.large
        - Is very common for non distributed systems, such as a database
        - RDS, ElastiCache are example of scale verticaly
        - There is usually a limit to how much you can verticaly scale (Hardware limit)
        
        - Horizontal
          - Means increasing the number of instances / system for your application
          - Scaling implies distributed systems
          - This is very common for web apps / modern apps
          - It is easy to horizontallu scale thanks the cloud offerings such as Amazon EC2
    
    - High Availability 
      - Usually goes hand in hand with horizontal scaling
      - Means running your application / system in at least 2 data centers (AZ)
      - The goal of high availability is to survive a data center loss

      - Can be passive (for RDS Multi AZ)
      - Can be active (for horizontal scaling)

    - For EC2
      - Vertical scaling: increase instance size
      - Horizontal scaling: increase number of instances
      - High Availability: run instances of the same application across multi AZ 
