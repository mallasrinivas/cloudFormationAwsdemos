# XYZ Corporation Web Application Testing Stack

This CloudFormation template deploys a stack for testing a web-based application for XYZ Corporation. The stack includes resources for the web tier, application tier, and database tier.

## Prerequisites

Before deploying this CloudFormation stack, ensure you have the following:

- An AWS account with appropriate permissions to create resources.
- An existing EC2 Key Pair for SSH access to instances.
- Basic understanding of AWS services like EC2, RDS, and CloudFormation.

## Usage

1. **Launch Stack**: Deploy the CloudFormation stack using the provided template.

2. **Parameters**:
   - `KeyName`: Name of an existing EC2 KeyPair to enable SSH access to instances.
   - `WebInstanceType`: EC2 instance type for the web tier (default: `t2.micro`).
   - `AppInstanceType`: EC2 instance type for the application tier (default: `t2.micro`).
   - `DBInstanceType`: RDS instance type for the DB tier (default: `db.t2.micro`).
3. **Outputs**:

   - `WebInstancePublicIP`: Public IP address of the Web instance.
   - `AppInstancePrivateIP`: Private IP address of the App instance.
   - `DBEndpoint`: Endpoint address of the RDS DB instance.

4. **Accessing Instances**:
   - Use the provided public IP address of the Web instance to access the web server.
   - SSH into the application instance using the private IP address and the specified key pair.
   - Connect to the RDS DB instance using the provided endpoint address.

## Additional Notes

- Ensure that the email address specified in the parameters is verified manually in SES before sending test emails.
- The RDS DB instances are not specified as part of the CloudFormation stack, so they won't be deleted when the stack is deleted.
- Make sure to monitor and manage your resources to avoid unexpected charges.

For more information, refer to the [AWS CloudFormation documentation](https://docs.aws.amazon.com/cloudformation/index.html).
