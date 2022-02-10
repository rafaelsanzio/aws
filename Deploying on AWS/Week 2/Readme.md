CI - Continuos Intregration - https://aws.amazon.com/devops/continuous-integration/

    - Code commit
    - Code build
    - Code pipeline

AWS CodeCommit - https://aws.amazon.com/codecommit/

    - A fully managed source control service that makes it easy for companies to host secure and highly scalable private Git repositories
    
    - It is managed source control system that can host private Git repositories and work with all Git-based tools.

AWS CodeBuild - https://aws.amazon.com/codebuild/
    
    - A fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy

    - It is a managed service that compiles your source code, runs tests, produces deployable application artifacts.
    Those artifacts can be stored encrypted, using the AWS Key Management service.

    Ex: If we refer back to the CI/CD pipeline, you see that CodeBuild fits into the build phase, 
    and can also help with the test phase.

    Yml file: Yml stands for yaml ain't markup language, and it's used to store data in a human readable form.
    Yaml is commonly used for configuration files, and uses python style indentation to indicate nesting.

    - Build phase
    - Test phase

AWS CodePipeline - https://aws.amazon.com/codepipeline/

    - A continuous integration and continuous delivery service for fast and reliable application and infrastructure updates

    - On every code commit, we can initiate the CI/CD workflow, taking the code update through the automated tests

    - Source: This can retrieve our code from CodeCommit, or other sources like S3 and GitHub are also supported.
    - Build: This can be AWS CodeBuild doing something like building my Java code, or a third party integration like Jenkins, or CloudBees.
    - Test: this could be CodeBuild, running some unit tests against my code, or a third party integration like BlazeMeter, is also supported.
    - Deploy: we have chosen Elastic Beanstalk. We could use other AWS services like, AWS CloudFormation, AWS CodeDeploy, or third parties.


Key Notes: 

Continuous integration is a DevOps software development practice where developers regularly merge their code changes into a central repository, after which automated builds and tests are run. Continuous integration most often refers to the build or integration stage of the software release process and entails both an automation component (e.g. a CI or build service) and a cultural component (e.g. learning to integrate frequently). The key goals of continuous integration are to find and address bugs quicker, improve software quality, and reduce the time it takes to validate and release new software updates.

AWS CodeCommit is a fully-managed source control service that makes it easy for companies to host secure and highly scalable private Git repositories. CodeCommit eliminates the need to operate your own source control system or worry about scaling its infrastructure. You can use CodeCommit to securely store anything from source code to binaries, and it works seamlessly with your existing Git tools.

AWS CodeBuild is a fully managed build service that compiles source code, runs tests, and produces software packages that are ready to deploy. With CodeBuild, you don’t need to provision, manage, and scale your own build servers. CodeBuild scales continuously and processes multiple builds concurrently, so your builds are not left waiting in a queue. You can get started quickly by using prepackaged build environments, or you can create custom build environments that use your own build tools. With CodeBuild, you are charged by the minute for the compute resources you use.

AWS CodePipeline is a continuous integration and continuous delivery service for fast and reliable application and infrastructure updates. CodePipeline builds, tests, and deploys your code every time there is a code change, based on the release process models you define. This enables you to rapidly and reliably deliver features and updates. You can easily build out an end-to-end solution by using our pre-built plugins for popular third-party services like GitHub or integrating your own custom plugins into any stage of your release process. With AWS CodePipeline, you only pay for what you use. There are no upfront fees or long-term commitments.