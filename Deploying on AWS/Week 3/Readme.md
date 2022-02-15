<b> CD - Continuos Delivery</b>

    - Cloud Formation
    - Code Deploy
    - Code Build

<b>Cloud Formation</b>

    - It can build infrastructure based on a declarative file specified by you. The service can receive a file 
    containing the infrastructure definition and create infrastructure components based on whatever is described.
    - We can use JSON or YAML for the syntax of template to create your stack in CF.
    - It can be used to orchestrate your entire infrastructure set.
    - CfnInit, allowing you to configure the operating system of EC2 instances that were created by the stack

<b>Cloud Deploy</b>

    - Able to reliably deploy your application packages to your running EC2 instances while maintaining control over uptime, 
    deployment strategies, and how your deployment reacts to successes and failures
    - It helps you to easily create repeatable deployments to push your code out to your instances whether on premise or in a AWS.
    - It also able to maintain control while making your job much easier by using the tools and features provided
    - Able to tell it specifically what to do with any of the updates you were pushing out to your fleet.

    - Application: this is simply an organizational structure that is used by CodeDeploy to group together related deployment groups.
    In Code Deploy is the collection of deployment groups that are grouped together for the reasons you decide.

    - Deployment group: is the way you group together your fleet of instances. Allows you to specify whether 
    by scaling group or tags what instances will make up a group.
    
    - Revision: is another method of organization. It is not just a change that you are making, 
    but it is the collection of the files and scriptsthat will be used during your deployment.

    - AppSpec file: This is the main configuration logic of how the agent executes the deployments on the instances.
    It contains locations for all of the installation files, scripts, and when to trigger specific actions.
    This gives you the ability to have control over installing and configuring your application environment on your instance.
    
    - Repository: is simply the location where you store everything needed for your deployment.
    
    - CodeDeploy agent: The agent is the worker function operating within the system of each instance.
    It is the one that gets the signal to execute a deployment from the CodeDeploy service, retrieves the files, 
    evaluates the AppSpec file, executes the scripts, and verifies the deployment with the CodeDeploy service.