## Getting Started with AppStream 2.0 workshop template

This repository contains the AWS CloudFormation template to provision the prerequisites for the [Getting started with AppStream 2.0 workshop](https://appstream2.workshop.aws/).

### What is created
- VPC
- 2 private subnets
- 1 public subnet
- Internet gateway, NAT gateway and related routes
- AppStream 2.0 Image builder
- AppStream 2.0 service role (if the CreateAS2Role parameter is set to true)

This template uses an AWS Lambda function to ensure the subnets are created in an avaliability zone supported by AppStream 2.0.

### Instructions
1. Check if you have the AppStream 2.0 service role.
   1. Navigate to the IAM console.
   2. Choose **Roles** in the navigation pane.
   3. Search for **AmazonAppStreamServiceAccess**. If you have this role, change CreateAS2Role to false.
2. Navigate to the AWS CloudFormation console.
    1. This template is supported in us-east-1, us-west-2 and eu-west-1. Verify the Region in the upper right corner.
3. Choose **Create stack, with new resources (standard).**
4. Choose **Upload a template file**.
5. Select **cloudformation.yaml** from the repository.
6. For **Stack name**, enter *AS2-Workshop*
7. For CreateAS2Role, choose true if you don't see the role from step 1. If you do have the role, enter *false*.
8. Choose **Next**
9. On the Configure stack options page, choose **Next**.
10. Select **I acknowledge that AWS CloudFormation might create IAM resources with custom names**.
11. Choose **Create stack**.

Once your stack is created, you can start your workshop.

### Clean up
You can clean up the resources created by deleting the AWS CloudFormation template. For clean up of the workshop resources, refer to the [clean up section of the workshop](https://catalog.us-east-1.prod.workshops.aws/v2/workshops/e324c13e-2ded-4da2-ad9c-f685305156ac/en-US/conclusion).

1. Navigate to the AWS CloudFormation console.
2. Choose the *AS2-Workshop* stack
3. Choose **Delete**.

## Security

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## License

This library is licensed under the MIT-0 License. See the LICENSE file.

