Deployment Pipeline

    - Cloud Formation
    - Code Deploy

<b>AWS Systems Manager</b> - https://aws.amazon.com/systems-manager/

    - Gives you visibility and control of your infrastructure on AWS. Systems Manager provides a unified user interface so you can view operational data from multiple AWS services and allows you to automate operational tasks across your AWS resources. While there is not a hands on exercise using Systems Manager, we encourage you to explore it on your own. There is no additional charge for AWS Systems Manager. 

    - It is a managed service that simplifies resource and application management, shortens the time to detect and resolve 
    operational problems and makes it easy to operate and manage your running infrastructure.
    - Systems Manager operates on running infrastructure without having to destroy and create resources,

    - With AWS Systems Manager you can automate tasks on running EC2 instances. It provides some predefined automation 
    documents for common operational tasks out of the box but you can also create your own and customize to your own 
    specific needs such as installing monitoring agents, updating the operating systems, adding existing Windows 
    instances to an Active Directory Domain controller and many more.


<b>Advancing AWS CodeDeploy</b> 

    Appspec File 
        - is where you get the control over how your revision deployments are managed and what they do on your fleets.
        - isn't the actual document where you script the work being done by the CodeDeploy agent. Instead, it is the outline 
        of how the agent will perform its functions.

        - version: specific application or deployment
        - os: is for operating system (linux or windows)
        - files: This is optional and is only necessary if you are going to be copying files to the instances in your fleet.
            - source
            destination
        - permissions: This refers to the permissions you want to apply to the files being copied in the files section.
            Use of the files portion does not necessitate use of permissions. But the use of permissions does require 
            that you are using the files portion.
            - object: refers to the set of system files, folders, or directories that the specified permissions 
            are applied to after the file system objects are copied to the instance.

            - Additionally, permissions is only used for Linux deployments and is not used for Windows.
        - hooks: direct the CodeDeploy agent as to what it needs to do and when.
            - BeforeInstall and AfterInstall: are used for the scripts that you need to run before the installation happens 
            and after the installation is complete.
            - ApplicationStart and ApplicationStop
            - ValidateService: to run any scripts that you will use to test and make sure that everything 
            has been installed and started correctly.

        Each of these is used to run your specified script at the time of the utilized hook.

    Rolling Deployment

        - Red/Black and Blue/Green
            Both require you to create a second copy of your environment that's updated. And both use DNS or load-balancing 
            to move traffic from your original environment to the new environment.
            Both allow you to easily roll back simply by moving the traffic back to the original environment.
            The biggest difference between the two is that red/black is an instant cut-over and blue/green is a gradual cut-over.
            In the Blue/Green the benefit that you get is a smaller impact should errors start to occur, and you have 
            the same rollback ability that you get with the red/black deployment styles.

        - Rolling: is an in-place deployment style that allows you to keep the same number of instances, 
        but deploy only to some at a time. Your changes are enacted on a small set of instances at a time.
        And the deployment doesn't move forward until that group of instances is successful.

        - Canary instance:  is when you launch an instance in your already-existing environment, 
        but the new instance is updated. Using this method allows you to test features and changes with low impact to your 
        production environment, before launching full environments or initiating full deployments.

<b>Key notes</b>

    - Deployment Strategies
    AWS tools that can be used to help with this specifically AWS CodeDeploy, AWS CodePipeline, and AWS Systems Manager. 
    We looked at serveral deployment strategies focusing on In-place, Rolling, Red-Black, and Green-Blue.

    - AppSpec File
        - https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file-structure.html
        Examples: https://docs.aws.amazon.com/codedeploy/latest/userguide/reference-appspec-file-example.html
