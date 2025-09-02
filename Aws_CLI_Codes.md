# AWS Cloud

## EC2 (Elastic Compute Cloud)

List all instances
````
aws ec2 describe-instances
````
Start an instance
````
aws ec2 start-instances --instance-ids <id>
````
Stop an instance
````
aws ec2 stop-instances --instance-ids <id>
````
Terminate an instance
````
aws ec2 terminate-instances --instance-ids <id>
````
Create a key pair
````
aws ec2 create-key-pair --key-name <name>
````
List security groups
````
aws ec2 describe-security-groups – List security groups
````
