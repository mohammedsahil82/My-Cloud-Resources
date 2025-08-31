# AWS Cloud
## EC2 (Elastic Compute Cloud)
● aws ec2 describe-instances – List all instances
● aws ec2 start-instances --instance-ids <id> – Start an instance
● aws ec2 stop-instances --instance-ids <id> – Stop an instance
● aws ec2 terminate-instances --instance-ids <id> – Terminate an instance
● aws ec2 create-key-pair --key-name <name> – Create a key pair
● aws ec2 describe-security-groups – List security groups

## S3 (Simple Storage Service)
● aws s3 ls – List buckets
● aws s3 mb s3://<bucket> – Create a bucket
● aws s3 cp <file> s3://<bucket>/ – Upload a file
● aws s3 rm s3://<bucket>/<file> – Delete a file
● aws s3 rb s3://<bucket> --force – Delete a bucket
● aws s3 sync <local-dir> s3://<bucket>/ – Sync local and S3
