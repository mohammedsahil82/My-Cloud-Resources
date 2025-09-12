# Configuration of Services

## In instance CLI

ls    # To see files 
sudo -i  # To direct root


# To install aws
````
snap install aws-cli --classic
````
````
apt install awscli
````

# To configure
````
aws configure
````
Now from Security Crendentials copy AWS Access Key ID & AWS Access Key ID and add here and select region

# 1. Now Create Key pair first
````
aws ec2 create-key-pair --key-name sahil --query "key_material" --output text > sahil.pem
````

# 2. Create Security Group
````
aws ec2 create-security-group --group-name sahil-security --description "rj security group"
````

# 3. Now Give Permission to ports in Security Group
```
aws ec2 authorize-security-group-ingress --group-name sahil-security --protocol tcp --port 80 --cidr 0.0.0.0/0
````

# 4. Now Run Instance with AMI Image
````
aws ec2 run-instances --image-id ami-0360c520857e3138f --count 2 --instance-type t2.micro --key-name sahil --security-groups sahil-security
````

# 5. Create Bucket
````
aws s3 mb s3://sahil-8319113765
````

# 6. Create Object
````
aws s3 cp sahil.pem s3://sahil-8319113765
````

# 7. Enable Bucket Versioning
````
aws s3api put-bucket-versioning --bucket sahil-8319113765 --versioning-configuration Status=Enabled
````
