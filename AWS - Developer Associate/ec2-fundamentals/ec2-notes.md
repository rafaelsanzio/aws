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

    - EC2 Instances Types - https://aws.amazon.com/pt/ec2/instance-types/?trk=273714db-4e14-42ba-be75-e3e36c4bc786&sc_channel=ps&sc_campaign=acquisition&sc_medium=ACQ-P|PS-GO|Brand|Desktop|SU|Compute|EC2|BR|PT|Text&s_kwcid=AL!4422!3!589890540409!p!!g!!ec2&ef_id=Cj0KCQjwpcOTBhCZARIsAEAYLuU16opzaxN9BZ4WIlm7zkfZdLN0DDfOH_icrGKElkTPI0teMj6V1nIaAmc3EALw_wcB:G:s&s_kwcid=AL!4422!3!589890540409!p!!g!!ec2

    - Naming convention
        - Example: m5.2xlarge
            - m: instance class
            - 5: generation
            - 2xlarge: size within the instance class
