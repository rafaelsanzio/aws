CI - Continuos Intregration

    - Code commit
    - Code build
    - Code pipeline

AWS CodeCommit - is managed source control system that can host private Git repositories and work with all Git-based tools.

AWS CodeBuild - is a managed service that compiles your source code, runs tests, produces deployable application artifacts.
    Those artifacts can be stored encrypted, using the AWS Key Management service.

    Ex: If we refer back to the CI/CD pipeline, you see that CodeBuild fits into the build phase, 
    and can also help with the test phase.

    Yml file: Yml stands for yaml ain't markup language, and it's used to store data in a human readable form.
    Yaml is commonly used for configuration files, and uses python style indentation to indicate nesting.