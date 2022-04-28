# Best Practices

    - Don't use the root account except for AWS account setup
    - One physical user = One AWS <b>user</b>
    - <b>Assign users to groups</b> and assign permissions to group
    - Create a <b>strong password policy</b>
    - Use and enforce the use of <b>Multi Factor Authentication (MFA)</b>
    - Create and use <b>Roles</b> for giving permissions to AWS services
    - Use <b>Access Keys for Programmatic Access (CLI/SDK)</b>
    - Audit permissions of your account with the IAM Credentials Report
    - <b>Never share IAM users & Access Keys</b>

# Summary

    - <b>Users</b>: mapped to a physical user, has a password for AWS Console
    - <b>Groups</b>: contains users only
    - <b>Policies</b>: JSON document that outlines permissions for users or groups
    - <b>Roles</b>: for EC2 instances or AWS services
    - <b>Security</b>: MFA + Password Policy
    - <b>Access Keys</b>: access AWS using the CLI or SDK
    - <b>Audit</b>: IAM Credential Reports and IAM Access Advisor
