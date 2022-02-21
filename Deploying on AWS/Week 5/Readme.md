<b>Monitoring</b>

    - CloudWatch
    - Unified logs are a very elegant and safe solution for troubleshooting, analytics, and insights 
    about what's going on with your servers

<b>CloudWatch Metrics and Logs</b> - https://aws.amazon.com/cloudwatch/

    - You can use Amazon CloudWatch to collect and track metrics, collect and monitor log files, set alarms, 
    and automatically react to changes in your AWS resources

    - Collect metrics from your application and the deployed resources
    - Metrics important to operational performance can be sent and stored using a simple API.

<b>AWS ElasticSearch</b> - https://aws.amazon.com/opensearch-service/

    - It makes it easy to deploy, secure, operate, and scale Elasticsearch for log analytics, full text search, 
    application monitoring, and more. Amazon Elasticsearch Service is a fully managed service that delivers 
    Elasticsearch’s easy-to-use APIs and real-time analytics capabilities alongside the availability, scalability, 
    and security that production workloads require.

    - is a NoSQL database that makes it easy to search and analyze your data.
    - it makes lots of sense to have your logs in Elasticsearch because it is a full text search database engine.
    - you can enable the integration between CloudWatch Logs and Amazon Elasticsearch and that's all you need 
    to have your logs ready to be visualized in Kibana.

<b>Key Topics</b>

    Monitoring your Pipeline
        - Monitoring your CI/CD pipeline. We use Amazon CloudWatch, AWS Elasticsearch and Kibana to create and 
        view metrics and dashboards.

    Amazon CloudWatch Events - https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/WhatIsCloudWatchEvents.html
        - It delivers a near real-time stream of system events that describe changes in Amazon Web Services (AWS) resources. 
        Using simple rules that you can quickly set up, you can match events and route them to one or more target 
        functions or streams. CloudWatch Events becomes aware of operational changes as they occur.
    
    Amazon CloudWatch Logs Metrics - https://docs.aws.amazon.com/AmazonCloudWatch/latest/logs/WhatIsCloudWatchLogs.html
        - You can use to monitor, store, and access your log files from Amazon Elastic Compute Cloud (Amazon EC2) instances, 
        AWS CloudTrail, Route 53, and other sources. You can then retrieve the associated log data from CloudWatch Logs.
        You can collect metrics from servers by installing the CloudWatch agent on the server. You can install the agent
        on both Amazon EC2 instances and on-premises servers, and on servers running either Linux or Windows Server.

    Kibana - https://aws.amazon.com/opensearch-service/the-elk-stack/kibana/
        - It is an open-source data visualization and exploration tool used for log and time series analytics, 
        application monitoring, and operational intelligence use cases. Kibana offers tight integration with Elasticsearch, 
        a popular analytics and search engine, which makes Kibana the default choice for visualizing data stored in Elasticsearch.