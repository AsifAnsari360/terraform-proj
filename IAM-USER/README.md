To create an IAM (Identity and Access Management) user in AWS, follow these steps:

## 1. Sign in to the AWS Management Console:
- Go to the [AWS Management Console.](https://aws.amazon.com/console/)
- Sign in with your AWS root account credentials or as an IAM user with the necessary permissions to create users.
## 2. Navigate to IAM:
- In the AWS Management Console, find and click on IAM under the Security, Identity, & Compliance section.
## 3. Add User:
- In the IAM dashboard, click on Users from the left-hand navigation menu.
- Click on the Add users button.
## 4. Set User Details:
- User name: Enter a unique username for the new user.
- Access type:
  - Programmatic access: If the user needs to access AWS via the CLI, SDK, or API, check this option.
  - AWS Management Console access: If the user needs to access the AWS Management Console, check this option and set a custom password.
  - If you select console access, decide whether to require the user to create a new password at the next sign-in.
## 5. Set Permissions:
- Choose how to assign permissions to the user:
  - Attach policies directly: Select from existing policies such as AdministratorAccess, PowerUserAccess, or AmazonS3FullAccess.
  - Add user to group: Assign the user to a group that already has policies attached.
  - Copy permissions from existing user: Copy permissions from another IAM user.
  - Attach existing policies directly: Attach policies that exist within your account.
- Click Next: Tags.
## 6. Add Tags (Optional):
- You can add metadata to the user by adding key-value pairs (tags). This is optional.
- Click Next: Review.
## 7. Review and Create:
- Review the user's details and permissions.
- Click on Create user.
# 8. Download Credentials:
- On the confirmation screen, you will see an option to Download .csv. This file contains the user's Access Key ID and Secret Access Key.
- Important: This is the only time you can download the secret access key. Save this file securely.
