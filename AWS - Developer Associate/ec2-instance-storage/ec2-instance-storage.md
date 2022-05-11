# EC2 Instance Storage

    - EBS Volume (Elastic Block Store)

        - Is a network drive you can attach to your instances while they run
        - It allows your instances to persist data, even after their termination
        - Only be mounted to one instance at a time (CCP level)
        - Are bound to a specific availability zone

        - It is a network drive (not a physical drive)
        - It is locked to an AZ (Availability Zone)
        - Have a provisioned capacity (size in GBs and IOPS)

        - Controls the EBS behaviour when an EC2 instance terminates
        - This can be controlled by thw AWS console | AWS CLI
        - Use case: preserve root colume when instance is terminated

    - EBS Snapshot

        - Make a backup (snapshot) of EBS Volume at a point in time
        - Not necessary detach volume to do snapshot, but recommended
        - Can copy snapshots across AZ or Region

        - EBS Snapshot Archive: move a snapshot to an archive tier, takes 24 to 72 hours
        - Recycle Bin for EBS Snapshot: setup rules to retain deleted snapshots, specify retention (1 day to 1 year)

    - Amazon Machine Image (AMI)

        - AMI are a customization of an EC2 Instance (software, config, OS, monitoring)
        - AMI are built for a specific region (can be copied across regions)

        - You can launch EC2 instances from:
            - A public AMI: AWS provided
            - Your own AMI: make and maintain yourselff
            - An AWS Marketplace AMI: an AMi someone else made

        - Process
            - Start an EC2 instance and customize it
            - Stop the instance for data integrity
            - Build an AMI - this will also create EBS snapshot
            - Launch instances from other AMIs
    
    - EC2 Instance Store

        - If you need a high-performance hardware disk
        - Better I/O performance
        - Lose their storage if they are stopped (ephemeral)
        - Good for buffer / cache / scratch data / temporary content
        - Risk of data loss if hardware fails
        - Backups and Replication are your responsability

    - EBS Volume Types

        - They are characterized in Size / Throughput / IOPS (I/O Ops per sec) 

        - GP2 / GP3 (SSD): General purpose SSD volume that balances price and performance for a wide variety of workloads
        - IO1 / IO2 (SSD): Highest-performance SSD volume for mission-critical low-latency or high-throughput workloads
        - ST1 (HDD): Low cost HDD volume designed for frequently accessed, throughput intensive workloads
        - SC1 (HDD): Low cost HDD volume designed for less frequently accessed workload

        - Only GP2/GP3 and IO1/IO2 can be used as boot volumes

        - General Purpose SDD 
          - Cost effective storage, low-latency
          - System boot volumes, virtual desktops, development and test environments
          - Sizes 1Gb to 16Tb
        
        - Provisioned IOPS (PIOPS) SDD
          - Critical bussiness applications with sustained IOPS performance
          - Or applications that needs more than 16k IOPS
          - Great for databases workloads (sensitive to storage performance and consistency)
        
        - Hard Drive Disk (HDD)
          - Cannot be a boot volume
          - 125 Mb to 16 Tb
          - Throughput optimized HDD (st1): Big data, data warehouse, log processing
          - Cold HDD: For data that is frequently accessed and scenarios where lowest cost is important
    
    - EBS Multi Attach - IO1/IO2
      - Attach the same EBS Volume to multiple ECS instances in the same AZ
      - EC2 instance has full read and write permissions to the volume
      - Use case: 
        - Achieve higher application availability in clustered Linux application 
        - Application must manage concurrent write operations
      - Must be a file system that's cluster-aware (not XFS, EX4)
    
    - EFS: Elastic File System
      - Manage NFS (network file system) that can be mounted on many EC2
      - It works with EC2 instances in multi AZ
      - Highly available, scalable, expensive (3x GP2), pay per use

      - Use cases: content management, web serving, data sharing, wordpress
      - Uses security group to control access in EFS
      - Compatible with Linux based AMI (not Windows)
      - Encryption at rest using KMS

      - File system scales automatically, pay-per-use, no capacity planning.
      
      - Performance and Storage
        - EFS Scale
        - Performance mode (set at EFS creation)
        - Throughput mode 
