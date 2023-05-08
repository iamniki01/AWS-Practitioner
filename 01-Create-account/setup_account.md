# Setup AWS account

## 1. Create Account

Depending on the requirement, one can create account. Use this [link](https://aws.amazon.com/console/) to create account. Here, I used free tier account for learning purpose(for business, use business account).

To do this, one must give Name, phone number, address and Credit/debit card details. Then the AWS root user account is ready.

## 2. Setup IAM Group

After logging to root user account, it is recommended to create IAM group for authorization and authentication purpose with administrator access.

To create, search service name `IAM` then create group by clicking on `Create Group`

## 3. Add user

After creating a group, create user to work under the group with different credentials, so that no one have right access to root account.

To create, search service name `IAM` then create user by clicking on `Users`, after adding users to the group.

## 4. Add/select region

There are multiple AWS region and each region has multiple availability regions. Setup region on your specific usage.
