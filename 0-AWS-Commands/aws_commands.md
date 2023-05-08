# AWS Commands

Here is a list of some common AWS commands organized by section:

### EC2 Commands

- `aws ec2 describe-instances`: lists information about instances
- `aws ec2 start-instances`: starts one or more instances
- `aws ec2 stop-instances`: stops one or more instances
- `aws ec2 terminate-instances`: terminates one or more instances
- `aws ec2 create-key-pair`: creates a new key pair for SSH access to instances
- `aws ec2 create-security-group`: creates a new security group for instances
- `aws ec2 authorize-security-group-ingress`: adds a new rule to a security group to allow traffic

### S3 Commands

- `aws s3 ls`: lists all buckets in an account
- `aws s3 mb`: creates a new bucket
- `aws s3 rb`: removes a bucket
- `aws s3 cp`: copies files to/from S3
- `aws s3 sync`: syncs files between a local directory and S3
- `aws s3api put-object-acl`: sets the ACL for an object
- `aws s3api put-bucket-website`: sets up static website hosting for a bucket

### RDS Commands

- `aws rds describe-db-instances`: lists information about database instances
- `aws rds create-db-instance`: creates a new database instance
- `aws rds delete-db-instance`: deletes a database instance
- `aws rds modify-db-instance`: modifies an existing database instance
- `aws rds create-db-snapshot`: creates a snapshot of a database instance
- `aws rds restore-db-instance-from-snapshot`: restores a database instance from a snapshot
- `aws rds describe-db-snapshots`: lists information about database snapshots

### IAM Commands

- `aws iam create-user`: creates a new IAM user
- `aws iam delete-user`: deletes an IAM user
- `aws iam create-group`: creates a new IAM group
- `aws iam delete-group`: deletes an IAM group
- `aws iam attach-user-policy`: attaches a policy to an IAM user
- `aws iam attach-group-policy`: attaches a policy to an IAM group
- `aws iam list-users`: lists all IAM users in an account
- `aws iam list-groups`: lists all IAM groups in an account
