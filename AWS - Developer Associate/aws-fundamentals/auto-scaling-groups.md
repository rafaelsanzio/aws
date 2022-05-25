# Auto Scaling Groups (ASG)

- Scale out (add EC2 instances) to match an increased load
- Scale in (remove EC2 instances) to match an decreased load
- Ensure we have a minimum and maximum number of machines running
- Automatically Register new instances to a load balancer

- Attributes:
	- Lunch configs
		- AMI + Instance Type
		- EC2 User Data
		- EBS Volume
		- Security Groups
		- SSH Key Pair
	- Min Size / Max Size / Initial Capacity
	- Network + Subnets Information
	- Load Balancer Information
	- Scaling Policies

- Alarms
	- It is possible to scale an ASG based on CloudWatch alarm
	- An alarm monitors a metric (such as Average CPU)
	- Metrics are computed for the overall ASG instances
	- Base on the alarm: 
		- We can create scale-out policies (increase the number of instances)
		- We can create scale-in policies (decrease the number of instances)

- New Rules
	- It is now possible to define "better" auto scaling rules that are directly managed by EC2
		- Target Average CPU Usage
		- Number of requests on the ELB per instance 
		- Average Network In
		- Average Network Out
	- These rules are easier to set up and can make more sense

	- Custom Metric
		- Scale based on a custom metric (number of connected users)

### Main notes

- Scaling policies can be on CPU, Network, and can even be on custom metrics or based on a schedule
- ASGs use Launch config ot Launch Templates
- IAM roles attached to an ASG will get assigned to EC2 instances
- Having instances under ASG means that if they get terminated for any reason, the ASG will automatically create a new ones as a replacement
- ASG can terminate instances marked as unhealthy by an LB (and hence replace them)

### Scaling Policies

- Dynamic
	- Target Tracking Scaling
		- Ex: The average of ASG CPU to stay at around 40%
	- Simple / Step Scaling
		- When CloudWatch alarm is triggered (CPU > 70%), then add 2 units
		- When CloudWatch alarm is triggered (CPU < 30%), then remove 1 unit
	- Scheduled Actions
		- Anticipate a scaling based on known usage patterns

- Predictive
	- Continuously forecast load ans schedule scaling ahead

- Good Metrics
	- CPU Utilization: Average CPU utilization across your instances
	- Request Count Per Target: to make sure the number of requests per EC2 instances is stable
	- Average Network In / Out (if you are app is network bound)
	- Any custom metric (that you push using CloudWatch)

- Cooldowns
	- After a scaling activity happens, you are in the cooldown period (default 300s)
	- During the cooldown period, the ASG will not launch or terminate additional instances (to allow for metrics to stabilize)
