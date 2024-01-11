## AWS Command Line Interface (CLI)

The AWS Command Line Interface (CLI) is a powerful tool provided by Amazon Web Services that enables managing various AWS services and resources from the command line. It allows for automation, scripting, and interacting with AWS without using the AWS Management Console.

### Installation:

- **Install AWS CLI:** Follow the instructions provided in the [AWS CLI installation page](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) for installation on Windows, macOS, Linux, or Unix systems.

### Configuration:
- **Configure AWS CLI:** Use `aws configure` to set up the AWS CLI with your AWS access key, secret key, default region, and output format.

generate the Access key and secret key

When ever we use CLI we need to access  our IAM account, we will access through aws configure and give region 

```bash
aws configure

AWS Access Key ID [None]: AKIAIOSFODNN7EXAMPLE
AWS Secret Access Key [None]: wJalrXUtnFEMMPLEKEY
Default region name [None]: us-east-1
Default output format [None]: json
```
Check your identity `aws sts get-caller-identity`
```bash 
{
    "Account": "123456", 
    "Arn": "arn:aws:sts::123456:assumed-role/role-name/role-session-name",
    "UserId": "AR#####:#####"
}
```

`aws --version`
Launch Instance replace keypair
```bash
aws ec2 run-instances --image-id ami-08e4e35cccc6189f4 --count 1 --instance-type t2.micro --key-name <Key-Pair-Name> --security-groups default
```

terminate instances change instance id
```
aws ec2 terminate-instances --instance-ids i-0d2d47aeec1593cf2

```
For Opening SSH & HTTP to everyone( change security group)

```bash
aws ec2 authorize-security-group-ingress --group-id sg-2b16eb4d --ip-permissions IpProtocol=tcp,FromPort=22,ToPort=22,IpRanges="[{CidrIp=0.0.0.0/0}]"

$ aws ec2 authorize-security-group-ingress --group-id sg-2b16eb4d --ip-permissions IpProtocol=tcp,FromPort=80,ToPort=80,IpRanges="[{CidrIp=0.0.0.0/0}]"
```
### Example Commands:
- **List S3 Buckets:** Lists all the S3 buckets in your AWS account.

  ```bash
  aws s3 ls

Retrieves information about your EC2 instances.
```bash 
aws ec2 describe-instances

```
Creating an S3 Bucket: Creates an S3 bucket with the specified name.
```bash
aws s3 mb s3://bucket-name

```
Managing IAM Users:Lists all the IAM users in your AWS account.
```bash
aws iam list-users
```

