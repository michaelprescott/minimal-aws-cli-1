# minimal-aws-cli-1
Minimal setup and usage of aws-cli - 1
About
=====
A minimal setup and usage of aws-cli.


Getting Started
---------------

1. Download and install aws-cli
    * macOS - https://awscli.amazonaws.com/AWSCLIV2.pkg
    * Verify installation `aws --version`
2. Login to your AWS account and create a new Access Key.  Make note
   of your Access Key ID and Secret Key.  You will not be able to
   get your Secret Key again.  If lost, you'll need to create anew.
    * https://console.aws.amazon.com/iam/home?#/security_credentials

Configure Environment
=====================
1. `aws configure`
```
AWS Access Key ID [None]: your-access-key-id
AWS Secret Access Key [None]: your-secret-key
Default region name [None]: us-east-1
Default output format [None]: json
```
2. `cd ~/.aws` aws configure created two files, config and credentials
3. If you work with multiple accounts you can revise create additional profiles.  For example:
.aws/config
```
[default]
region = us-east-1
output = json
[profile yourcompany]
region = us-east-1
output = json
```
.aws/credentials
```
[default]
aws_access_key_id = your-access-key-id
aws_secret_access_key = your-secret-key
[yourcompany]
aws_access_key_id = your-other-access-key-id
aws_secret_access_key = your-other-secret-key
```
Now, to run commands with a selected profile:
`aws s3 ls --profile yourcompany`
or for default profile just:
`aws s3 ls`

Usage
=====
`chmod -R  u+x tasks/*.sh`  # Set permissions to execute various tasks
`tasks/list-all-s3.sh`      # List all S3's

REFERENCES
==========
https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html