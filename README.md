# Auto-scaling_EC2_CloudFormation
W8Project Auto Scaling EC2's in CloudFormation.
This is for a project I did for Level Up in Tech.
Here's an article I wrote about the project.
https://medium.com/@jwood9799/infrastructure-as-code-iac-dd7f8ace9623


These were my instructions:
Create an autoscaling group using t2.micro EC2 instances across 2 public AZs in the default vpc. All EC2 instances should have Apache installed with the ability to check any EC2 created by the autoscaling group’s Public IP address and be able to produce a test page. Note: The code I have is for the Advanced and Complex parts of the project, so the public IP's will not be able to connect to the internet.

The instance min and max should be 2 and 5. Once the template is Launched successfully terminate two instances to see if the auto scaling group scales out.

Remember that you will need:

A web server security group that allows inbound traffic from HTTP from 0.0.0.0/0.
A Launch Template.
An Auto Scaling Group.

ADVANCED:
Add a target policy for the ASG to scale after cpu utilization is above 50%. After the autoscaling group has been created, find a stress tool to be able to stress an instance above 50% to see if your scaling policy works!

COMPLEX:

Add an Application Load Balancer as public facing and connect it to the Autoscaling group.
Ensure the ASG Security Group only allows traffic from the ALB.
Verify you are able to reach the website.
