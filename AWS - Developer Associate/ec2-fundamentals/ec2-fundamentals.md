# EC2 - Elastic Compute Cloud

- It is one of the most popular AWS offering

- EC2: renting virtual machines
- EBS: storing data on virtual drives
- ELB: ditributing load across machines
- ASG: scaling the services using an auto-scaling group

- Sizing and Config options

    - OS: Linux, Mac, Windows
    - CPU: power and cores
    - RAM: random-access memory
    - Storage: network-attached (EBS & EFS) or hardware (EC2 instance store)
    - Network card: public IP address
    - Firewall rules: security group
    - EC2 User Data: configure art first launch

- EC2 User Data: It is possible to bootstarp our instances with a script

    - Installing updates
    - Installing software
    - Download common files from the internet
    - Anything you can think of
    - Runs at a root user

### EC2 Instances Types - https://aws.amazon.com/pt/ec2/instance-types/?trk=273714db-4e14-42ba-be75-e3e36c4bc786&sc_channel=ps&sc_campaign=acquisition&sc_medium=ACQ-P|PS-GO|Brand|Desktop|SU|Compute|EC2|BR|PT|Text&s_kwcid=AL!4422!3!589890540409!p!!g!!ec2&ef_id=Cj0KCQjwpcOTBhCZARIsAEAYLuU16opzaxN9BZ4WIlm7zkfZdLN0DDfOH_icrGKElkTPI0teMj6V1nIaAmc3EALw_wcB:G:s&s_kwcid=AL!4422!3!589890540409!p!!g!!ec2

- Naming convention
    - Example: m5.2xlarge
        - m: instance class
        - 5: generation
        - 2xlarge: size within the instance class

- EC2 Purchasing Options

    - On Demand
        - Pay for what you use
        - Has the highest cost but no upfront payment
        - No long-term commitment
        - Recommended for short-term and un-interrupted workloads

    - Reserved
        - Up 72% discount
        - Change the specific instance attributes (Instance Type, Region, Tenancy, OS)
        - Reservation period 1 to 3 years
        - Reserved instance's scope - Regional or Zonal
        - Recommended for stady-stage usage app (think database)
        - Convertible Reserved instance

    - Saving Plans
        - Get a discount based on long-term usage
        - Commit to a certain type of usage
        - Locked to a specific instace family and AWS region
        - Flexible across:
            - Instance size
            - OS
            - Tenancy (host, dedicated, default)

    - Spot Instances
        - Discount of up to 90%
        - Instances that you can lose at any point of time
        - The most cost-efficient instances

        - Useful for workloads that are resilient to failure
            - Batch jobs
            - Data analysis
            - Image proccessing

        - Not suitable for critical jobs or databases

    - Dedicated Instances
        - runs on hardware that's dedicated to you

    - Capacity Reservations
        - Reserve On-Demand instace capacity for a specific duration
        - Always have access to EC2 capacity, when you need
        - No time commitment, no billing discounts

        - Suitable for short-term, uninterrupted workloads that needs to be in a specific AZ
