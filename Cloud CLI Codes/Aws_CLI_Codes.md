# AWS Cloud
## EC2 (Elastic Compute Cloud)

- aws ec2 describe-instances – List all instances
- aws ec2 start-instances --instance-ids <id> – Start an instance
- aws ec2 stop-instances --instance-ids <id> – Stop an instance
- aws ec2 terminate-instances --instance-ids <id> – Terminate an instance
- aws ec2 create-key-pair --key-name <name> – Create a key pair
- aws ec2 describe-security-groups – List security groups# S3 (Simple Storage Service)

# S3 (Simple Storage Service)

- aws s3 ls – List buckets
- aws s3 mb s3://<bucket> – Create a bucket
- aws s3 cp <file> s3://<bucket>/ – Upload a file
- aws s3 rm s3://<bucket>/<file> – Delete a file
- aws s3 rb s3://<bucket> --force – Delete a bucket
- aws s3 sync <local-dir> s3://<bucket>/ – Sync local and S3

# IAM (Identity and Access Management)

- aws iam list-users – List IAM users
- aws iam create-user --user-name <name> – Create a user
- aws iam attach-user-policy --user-name <name> --policy-arn <policy> – Attach a policy
- aws iam list-roles – List IAM roles
- aws iam create-role --role-name <name> --assume-role-policy-document file://policy.json – Create a role
- aws iam list-policies – List policies

# VPC (Virtual Private Cloud)

- aws ec2 describe-vpcs – List VPCs
- aws ec2 create-vpc --cidr-block <CIDR> – Create a VPC
- aws ec2 delete-vpc --vpc-id <id> – Delete a VPC
- aws ec2 create-subnet --vpc-id <id> --cidr-block <CIDR> – Create a subnet
- aws ec2 describe-security-groups – List security groups
- aws ec2 describe-internet-gateways – List internet gateways

# Lambda (Serverless Computing)

- aws lambda list-functions – List all Lambda functions
- aws lambda create-function --function-name <name> --runtime <runtime> --role <role> --handler <handler> – Create a function
- aws lambda update-function-code --function-name <name> --zip-file fileb://<file>.zip – Update function code
- aws lambda delete-function --function-name <name> – Delete a function
- aws lambda invoke --function-name <name> output.json – Invoke a function

# Amazon EKS (Elastic Kubernetes Service)

- aws eks list-clusters – List EKS clusters
- aws eks describe-cluster --name my-cluster – Describe an EKS cluster
- aws eks create-cluster --name my-cluster --role-arn arn:aws:iam::account-id:role/EKSRole --resources-vpc-config subnetIds=subnet-xxxxxxx,securityGroupIds=sg-xxxxxxx – Create an EKS cluster

- aws eks update-kubeconfig --name my-cluster – Configure kubectl to use the EKS cluster
- kubectl get nodes – Check worker nodes
- kubectl get pods -A – List running pods
  
# Amazon ECS (Elastic Container Service)

- aws ecs list-clusters – List ECS clusters
- aws ecs list-services --cluster my-cluster – List ECS services
- aws ecs describe-services --cluster my-cluster --services my-service – Describe an ECS service

# AWS CloudFormation

- aws cloudformation list-stacks – List all stacks
- aws cloudformation create-stack --stack-name my-stack --template-body file://template.yml – Create a stack CI/CD (CodePipeline, CodeBuild, CodeDeploy)

# AWS CodePipeline

- aws codepipeline list-pipelines – List all pipelines
- aws codepipeline start-pipeline-execution --name my-pipeline – Start a pipeline execution

# AWS CodeBuild

- aws codebuild list-projects – List all CodeBuild projects
- aws codebuild start-build --project-name my-project – Start a build

# AWS CodeDeploy

- aws deploy list-applications – List all CodeDeploy applications
- aws deploy create-deployment --application-name MyApp --deployment-group-name MyDeploymentGroup --s3-location bucket=my-bucket,key=app.zip,bundleType=zip -Deploy an application

# Security & Compliance

- aws cloudtrail describe-trails – List CloudTrail logs
- aws secretsmanager list-secrets – List all secrets
- aws secretsmanager get-secret-value --secret-id my-secret – Retrieve a secret

# Monitoring & Logging (CloudWatch)

- aws cloudwatch list-metrics – List available metrics
- aws cloudwatch put-metric-alarm --alarm-name cpu-high --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 80 --comparison-operator GreaterThanThreshold --dimensions Name=InstanceId,Value=i-xxxxxxxxxx --evaluation-periods 2 --alarm-actions arn:aws:sns:region:account-id:my-topic – Create a CloudWatch alarm

- aws logs describe-log-groups – List all log groups
- aws logs get-log-events --log-group-name my-log-group --log-stream-name my-log-stream – Retrieve log events Networking (VPC, ELB, Route 53)

# Amazon VPC

- aws ec2 describe-vpcs – List all VPCs
- aws ec2 describe-subnets – List all subnets

# Elastic Load Balancer (ELB)

- aws elbv2 describe-load-balancers – List all load balancers

# Amazon Route 53

- aws route53 list-hosted-zones – List hosted zones

# Amazon ECR (Elastic Container Registry)

- aws ecr get-login-password | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com – Authenticate Docker with ECR
- aws ecr list-repositories – List all ECR repositories

# AWS Systems Manager (SSM)

- aws ssm describe-instances – List managed instances
- aws ssm send-command --document-name "AWS-RunShellScript" --targets "Key=instanceIds,Values=i-xxxxxxxxxx" --parameters commands="sudo apt update" – Run a command on an EC2 instance

# AWS Auto Scaling

- aws autoscaling describe-auto-scaling-groups – List Auto Scaling groups
- aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-asg --desired-capacity 3 – Update the desired capacity
- aws autoscaling set-desired-capacity --auto-scaling-group-name my-asg --desired-capacity 2 – Manually scale an Auto Scaling group

# AWS Elastic Beanstalk

- aws elasticbeanstalk describe-environments – List all environments
- aws elasticbeanstalk create-application --application-name my-app – Create an application
- aws elasticbeanstalk update-environment --environment-name my-env --version-label new-version – Deploy a new version

# AWS Step Functions

- aws stepfunctions list-state-machines – List all state machines
- aws stepfunctions start-execution --state-machine-arn arn:aws:states:region:account-id:stateMachine:MyStateMachine – Start a state machine execution
- aws stepfunctions describe-execution --execution-arn arn:aws:states:region:account-id:execution:MyStateMachine:MyExecution – Get execution details

# AWS Glue (ETL Service)

- aws glue get-databases – List all Glue databases
- aws glue get-tables --database-name my-database – List all tables in a database
- aws glue start-job-run --job-name my-glue-job – Start a Glue job

# AWS SNS (Simple Notification Service)

- aws sns list-topics – List all SNS topics
- aws sns publish --topic-arn arn:aws:sns:region:account-id:MyTopic --message "Test Message" – Publish a message to an SNS topic

# AWS SQS (Simple Queue Service)
- aws sqs list-queues – List all SQS queues
- aws sqs send-message --queue-url https://sqs.region.amazonaws.com/account-id/my-queue --message-body "Hello World" – Send a message

# AWS Outposts(Managed on-prem cloud/On-premises AWS)

## List and Describe Outposts

- aws outposts list-outposts # List all AWS Outposts
- aws outposts get-outpost --outpost-id <outpost-id> # Get details of a specific Outpost
- aws outposts get-outpost-instance-types --outpost-id <outpost-id> # List instance types in an Outpost

# Manage Outpost Resources

- aws outposts list-sites # List all Outpost sites
- aws outposts list-orders # List Outpost orders
- aws outposts list-outpost-instances --outpost-id <outpost-id> # List EC2 instances in an Outpost

# Deploy and Configure Outposts

- aws outposts create-order --line-items "[{\"catalogItemId\": \"item-id\", \"quantity\": 1}]" --outpost-id <outpost-id> # Order an Outpost
- aws outposts update-outpost --outpost-id <outpost-id> --name <new-name> # Update Outpost configuration

# Networking and Storage on Outposts

- aws outposts list-outpost-network-devices --outpost-id <outpost-id> # List network devices in an Outpost
- aws s3 ls --outpost-id <outpost-id> # List S3 buckets on an Outpost
- aws s3 mb s3://<bucket-name> --outpost-id <outpost-id> # Create an S3 bucket in Outpost

# Deploy EC2 Instances in Outposts

- aws ec2 run-instances --image-id <ami-id> --instance-type <type> --subnet-id <outpost-subnet-id> # Launch an EC2 instance in Outpost

# Automate Outpost Deployments with CloudFormation

- aws cloudformation deploy --template-file outpost-config.yml --stack-name my-outpost-stack # Deploy Outpost resources using CloudFormation

# Monitor Outposts with CloudWatch

- aws cloudwatch list-metrics --namespace AWS/Outposts # List Outpost-related CloudWatch metrics
- aws cloudwatch get-metric-data --metric-name CPUUtilization --namespace AWS/Outposts # Monitor CPU usage of Outpost instances

# Integrate Outposts with CI/CD

- aws codepipeline list-pipelines # List all CI/CD pipelines
- aws codepipeline start-pipeline-execution --name <pipeline-name> # Start a deployment pipeline for Outposts
- aws codebuild start-build --project-name <build-project> # Start a build process for Outposts workloads
- aws deploy create-deployment --application-name <app-name> --deployment-group-name <group-name> --s3-location bucket=<bucket-name>,key=<app.zip>,bundleType=zip

# Deploy an application to an Outpost

## Security and Compliance for Outposts

- aws iam create-role --role-name <role-name> --assume-role-policy-document file://policy.json # Create an IAM role for Outpost management
- aws secretsmanager list-secrets # List stored secrets for Outposts
- aws secretsmanager get-secret-value --secret-id <secret-name> # Retrieve a stored secret
- aws cloudtrail describe-trails # List AWS CloudTrail logs for security auditing
- aws guardduty list-findings # Detect security threats related to Outposts

# Delete or Deactivate an Outpost

# AWS Cloud
## EC2 (Elastic Compute Cloud)

- aws ec2 describe-instances – List all instances
- aws ec2 start-instances --instance-ids <id> – Start an instance
- aws ec2 stop-instances --instance-ids <id> – Stop an instance
- aws ec2 terminate-instances --instance-ids <id> – Terminate an instance
- aws ec2 create-key-pair --key-name <name> – Create a key pair
- aws ec2 describe-security-groups – List security groups# S3 (Simple Storage Service)

# S3 (Simple Storage Service)

- aws s3 ls – List buckets
- aws s3 mb s3://<bucket> – Create a bucket
- aws s3 cp <file> s3://<bucket>/ – Upload a file
- aws s3 rm s3://<bucket>/<file> – Delete a file
- aws s3 rb s3://<bucket> --force – Delete a bucket
- aws s3 sync <local-dir> s3://<bucket>/ – Sync local and S3

# IAM (Identity and Access Management)

- aws iam list-users – List IAM users
- aws iam create-user --user-name <name> – Create a user
- aws iam attach-user-policy --user-name <name> --policy-arn <policy> – Attach a policy
- aws iam list-roles – List IAM roles
- aws iam create-role --role-name <name> --assume-role-policy-document file://policy.json – Create a role
- aws iam list-policies – List policies

# VPC (Virtual Private Cloud)

- aws ec2 describe-vpcs – List VPCs
- aws ec2 create-vpc --cidr-block <CIDR> – Create a VPC
- aws ec2 delete-vpc --vpc-id <id> – Delete a VPC
- aws ec2 create-subnet --vpc-id <id> --cidr-block <CIDR> – Create a subnet
- aws ec2 describe-security-groups – List security groups
- aws ec2 describe-internet-gateways – List internet gateways

# Lambda (Serverless Computing)

- aws lambda list-functions – List all Lambda functions
- aws lambda create-function --function-name <name> --runtime <runtime> --role <role> --handler <handler> – Create a function
- aws lambda update-function-code --function-name <name> --zip-file fileb://<file>.zip – Update function code
- aws lambda delete-function --function-name <name> – Delete a function
- aws lambda invoke --function-name <name> output.json – Invoke a function

# Amazon EKS (Elastic Kubernetes Service)

- aws eks list-clusters – List EKS clusters
- aws eks describe-cluster --name my-cluster – Describe an EKS cluster
- aws eks create-cluster --name my-cluster --role-arn arn:aws:iam::account-id:role/EKSRole --resources-vpc-config subnetIds=subnet-xxxxxxx,securityGroupIds=sg-xxxxxxx – Create an EKS cluster

- aws eks update-kubeconfig --name my-cluster – Configure kubectl to use the EKS cluster
- kubectl get nodes – Check worker nodes
- kubectl get pods -A – List running pods
  
# Amazon ECS (Elastic Container Service)

- aws ecs list-clusters – List ECS clusters
- aws ecs list-services --cluster my-cluster – List ECS services
- aws ecs describe-services --cluster my-cluster --services my-service – Describe an ECS service

# AWS CloudFormation

- aws cloudformation list-stacks – List all stacks
- aws cloudformation create-stack --stack-name my-stack --template-body file://template.yml – Create a stack CI/CD (CodePipeline, CodeBuild, CodeDeploy)

# AWS CodePipeline

- aws codepipeline list-pipelines – List all pipelines
- aws codepipeline start-pipeline-execution --name my-pipeline – Start a pipeline execution

# AWS CodeBuild

- aws codebuild list-projects – List all CodeBuild projects
- aws codebuild start-build --project-name my-project – Start a build

# AWS CodeDeploy

- aws deploy list-applications – List all CodeDeploy applications
- aws deploy create-deployment --application-name MyApp --deployment-group-name MyDeploymentGroup --s3-location bucket=my-bucket,key=app.zip,bundleType=zip -Deploy an application

# Security & Compliance

- aws cloudtrail describe-trails – List CloudTrail logs
- aws secretsmanager list-secrets – List all secrets
- aws secretsmanager get-secret-value --secret-id my-secret – Retrieve a secret

# Monitoring & Logging (CloudWatch)

- aws cloudwatch list-metrics – List available metrics
- aws cloudwatch put-metric-alarm --alarm-name cpu-high --metric-name CPUUtilization --namespace AWS/EC2 --statistic Average --period 300 --threshold 80 --comparison-operator GreaterThanThreshold --dimensions Name=InstanceId,Value=i-xxxxxxxxxx --evaluation-periods 2 --alarm-actions arn:aws:sns:region:account-id:my-topic – Create a CloudWatch alarm

- aws logs describe-log-groups – List all log groups
- aws logs get-log-events --log-group-name my-log-group --log-stream-name my-log-stream – Retrieve log events Networking (VPC, ELB, Route 53)

# Amazon VPC

- aws ec2 describe-vpcs – List all VPCs
- aws ec2 describe-subnets – List all subnets

# Elastic Load Balancer (ELB)

- aws elbv2 describe-load-balancers – List all load balancers

# Amazon Route 53

- aws route53 list-hosted-zones – List hosted zones

# Amazon ECR (Elastic Container Registry)

- aws ecr get-login-password | docker login --username AWS --password-stdin <aws_account_id>.dkr.ecr.<region>.amazonaws.com – Authenticate Docker with ECR
- aws ecr list-repositories – List all ECR repositories

# AWS Systems Manager (SSM)

- aws ssm describe-instances – List managed instances
- aws ssm send-command --document-name "AWS-RunShellScript" --targets "Key=instanceIds,Values=i-xxxxxxxxxx" --parameters commands="sudo apt update" – Run a command on an EC2 instance

# AWS Auto Scaling

- aws autoscaling describe-auto-scaling-groups – List Auto Scaling groups
- aws autoscaling update-auto-scaling-group --auto-scaling-group-name my-asg --desired-capacity 3 – Update the desired capacity
- aws autoscaling set-desired-capacity --auto-scaling-group-name my-asg --desired-capacity 2 – Manually scale an Auto Scaling group

# AWS Elastic Beanstalk

- aws elasticbeanstalk describe-environments – List all environments
- aws elasticbeanstalk create-application --application-name my-app – Create an application
- aws elasticbeanstalk update-environment --environment-name my-env --version-label new-version – Deploy a new version

# AWS Step Functions

- aws stepfunctions list-state-machines – List all state machines
- aws stepfunctions start-execution --state-machine-arn arn:aws:states:region:account-id:stateMachine:MyStateMachine – Start a state machine execution
- aws stepfunctions describe-execution --execution-arn arn:aws:states:region:account-id:execution:MyStateMachine:MyExecution – Get execution details

# AWS Glue (ETL Service)

- aws glue get-databases – List all Glue databases
- aws glue get-tables --database-name my-database – List all tables in a database
- aws glue start-job-run --job-name my-glue-job – Start a Glue job

# AWS SNS (Simple Notification Service)

- aws sns list-topics – List all SNS topics
- aws sns publish --topic-arn arn:aws:sns:region:account-id:MyTopic --message "Test Message" – Publish a message to an SNS topic

# AWS SQS (Simple Queue Service)
- aws sqs list-queues – List all SQS queues
- aws sqs send-message --queue-url https://sqs.region.amazonaws.com/account-id/my-queue --message-body "Hello World" – Send a message

# AWS Outposts(Managed on-prem cloud/On-premises AWS)

## List and Describe Outposts

- aws outposts list-outposts # List all AWS Outposts
- aws outposts get-outpost --outpost-id <outpost-id> # Get details of a specific Outpost
- aws outposts get-outpost-instance-types --outpost-id <outpost-id> # List instance types in an Outpost

# Manage Outpost Resources

- aws outposts list-sites # List all Outpost sites
- aws outposts list-orders # List Outpost orders
- aws outposts list-outpost-instances --outpost-id <outpost-id> # List EC2 instances in an Outpost

# Deploy and Configure Outposts

- aws outposts create-order --line-items "[{\"catalogItemId\": \"item-id\", \"quantity\": 1}]" --outpost-id <outpost-id> # Order an Outpost
- aws outposts update-outpost --outpost-id <outpost-id> --name <new-name> # Update Outpost configuration

# Networking and Storage on Outposts

- aws outposts list-outpost-network-devices --outpost-id <outpost-id> # List network devices in an Outpost
- aws s3 ls --outpost-id <outpost-id> # List S3 buckets on an Outpost
- aws s3 mb s3://<bucket-name> --outpost-id <outpost-id> # Create an S3 bucket in Outpost

# Deploy EC2 Instances in Outposts

- aws ec2 run-instances --image-id <ami-id> --instance-type <type> --subnet-id <outpost-subnet-id> # Launch an EC2 instance in Outpost

# Automate Outpost Deployments with CloudFormation

- aws cloudformation deploy --template-file outpost-config.yml --stack-name my-outpost-stack # Deploy Outpost resources using CloudFormation

# Monitor Outposts with CloudWatch

- aws cloudwatch list-metrics --namespace AWS/Outposts # List Outpost-related CloudWatch metrics
- aws cloudwatch get-metric-data --metric-name CPUUtilization --namespace AWS/Outposts # Monitor CPU usage of Outpost instances

# Integrate Outposts with CI/CD

- aws codepipeline list-pipelines # List all CI/CD pipelines
- aws codepipeline start-pipeline-execution --name <pipeline-name> # Start a deployment pipeline for Outposts
- aws codebuild start-build --project-name <build-project> # Start a build process for Outposts workloads
- aws deploy create-deployment --application-name <app-name> --deployment-group-name <group-name> --s3-location bucket=<bucket-name>,key=<app.zip>,bundleType=zip

# Deploy an application to an Outpost

## Security and Compliance for Outposts

- aws iam create-role --role-name <role-name> --assume-role-policy-document file://policy.json # Create an IAM role for Outpost management
- aws secretsmanager list-secrets # List stored secrets for Outposts
- aws secretsmanager get-secret-value --secret-id <secret-name> # Retrieve a stored secret
- aws cloudtrail describe-trails # List AWS CloudTrail logs for security auditing
- aws guardduty list-findings # Detect security threats related to Outposts

# Delete or Deactivate an Outpost

- aws outposts delete-outpost --outpost-id <outpost-id> # Delete an Outpost (must be empty)
- aws outposts cancel-order --order-id <order-id> # Cancel an Outpost order before delivery

- aws outposts delete-outpost --outpost-id <outpost-id> # Delete an Outpost (must be empty)
- aws outposts cancel-order --order-id <order-id> # Cancel an Outpost order before deliv
