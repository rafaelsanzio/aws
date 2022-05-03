# Secutiry Groups

    - They are fundamental of network secutiry in AWS
    - Control how traffic is allowed into or out of our EC2 Instances
    
    - Only contain allow rules
    - Can reference by IP or by security group

    - Are acting as a "firewall" on EC2
    - They regulate:
        - Access to ports
        - Authorised IP ranges - IPv4 and IPv6
        - Control of inbound network (from other to the instance)
        - Control of outbound network (from other to the instance)

    - Good to know
        - Can ve attached to multiple instances
        - Locked down to a region /VPC combination
        - Does live "ouside" the EC2, if traffic is blocked the EC2 instance won't see it
        - It is good to maintain one separate security group for SSH access
        - If your app is not accessible (time out), then it is a scurity group issue
        - If your app gives a "connection refused" error, then it is an app error or it is not launched
        - All inbound traffic is blocked by default
        - All outbound traffic is authorised by default

    - Classic ports
        - 22 = SSH (Secure shell) - log into a Linux instance
        - 21 = FTP (File Transfer Protocol) - upload files into a file share
        - 22 = SFTP (Secure File Transfer Protocol) - upload files using SSH
        - 80 = HTTP - access unsecured websites
        - 443 = HTTPS - access secured websites
        - 3389 = RDP (Remote Desktop Protocol) - log into a Windows instance
