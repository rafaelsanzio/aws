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
