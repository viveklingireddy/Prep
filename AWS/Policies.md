## AWS IAM Access Policies Documentation

we create Policies to manage access to aws resources, we attach them to IAM users/ roles to limit access to requested/ limited access required.\ 
*AWS evaluates these policies when an IAM principal (user or role) makes a request. Permissions in the policies determine whether the request is allowed or denied. Most policies are stored in AWS as JSON documents* \

*Managed policies – Standalone identity-based policies that you can attach to multiple users, groups, and roles in your AWS account. There are two types of managed policies:

AWS managed policies – Managed policies that are created and managed by AWS.

Customer managed policies – Managed policies that you create and manage in your AWS account. Customer managed policies provide more precise control over your policies than AWS managed policies.*

[Creating IAM based policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_create.html)

[Learn YAML](https://www.yaml.info/learn/index.html)

##### Policies and the root user

The AWS account root user is affected by some policy types but not others. *You cannot attach identity-based policies to the root user, and you cannot set the permissions boundary for the root user. However, you can specify the root user as the principal in a resource-based policy or an ACL*. A root user is still the member of an account. If that account is a member of an organization in AWS Organizations, the root user is affected by any SCPs(Service control policies) for the account.

The [AWS IAM Access Policies documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html) provides comprehensive guidance on managing access permissions for AWS resources using AWS Identity and Access Management (IAM).

### Key Sections Covered:

1. **Policy Basics:**
   - Understand the fundamental structure and components of IAM policies, including the Principal, Effect, Action, Resource, Condition, etc.

2. **Managed Policies:**
   - Learn about pre-defined managed policies provided by AWS that cover common use cases, enabling permissions for various levels of access, from read-only to full access for specific services.

3. **Inline Policies:**
   - Create policies directly attached to users, groups, or roles, known as inline policies, providing more granular control over permissions.

4. **Policy Variables:**
   - Utilize policy variables to create flexible and reusable policies.

5. **IAM Policy Evaluation Logic:**
   - Understand the logic IAM uses when evaluating policies to determine permissions for entities.

6. **Policy Summaries:**
   - View and interpret policy summaries to ascertain the effective permissions of an IAM entity.

7. **Policy Examples:**
   - Access examples of policy statements for various services and actions, aiding in policy creation and implementation.

This documentation is essential for managing permissions within AWS environments, helping users create, apply, and manage IAM policies effectively to control access to AWS resources securely.

For detailed information, examples, and best practices on AWS IAM Access Policies, visit the [IAM Access Policies Documentation](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html).


- **Example to create a VPC with internetgate way, subnet, route table.**
To create an AWS Identity and Access Management (IAM) policy that grants the necessary permissions for creating a VPC with a subnet, Internet Gateway, and Route Table, you can use the following example policy. This policy assumes that you're creating these resources in a specific region (e.g., us-east-1), and you should adjust the region and resource names accordingly.

This example policy provides full access to the VPC, Subnet, Internet Gateway, and Route Table resources. Ensure that you restrict permissions based on the principle of least privilege in a production environment.

JSON IAM Policy Example:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ec2:CreateVpc",
        "ec2:CreateSubnet",
        "ec2:CreateInternetGateway",
        "ec2:CreateRouteTable",
        "ec2:AttachInternetGateway",
        "ec2:CreateRoute"
      ],
      "Resource": "*"
    },
    {
      "Effect": "Allow",
      "Action": "ec2:Describe*",
      "Resource": "*"
    }
  ]
}
```

This policy includes the following permissions:

ec2:CreateVpc: Permission to create a Virtual Private Cloud (VPC).
ec2:CreateSubnet: Permission to create a subnet within the VPC.
ec2:CreateInternetGateway: Permission to create an Internet Gateway.
ec2:CreateRouteTable: Permission to create a Route Table.
ec2:AttachInternetGateway: Permission to attach an Internet Gateway to the VPC.
ec2:CreateRoute: Permission to create a route in the Route Table.
Additionally, the policy allows the user to describe existing resources (ec2:Describe*) for informational purposes.

Remember to attach this policy to the IAM user, group, or role that needs these permissions. It's crucial to review and tailor the permissions based on your specific use case and security requirements.

### How to Write the policies 

Certainly! Writing AWS Identity and Access Management (IAM) policies involves specifying the actions that are allowed or denied for a set of resources. IAM policies are written in JSON format. Here's a basic guide to help you understand how to write IAM policies:

#### IAM Policy Structure:
  IAM policies consist of a JSON document with a specific structure:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow or Deny",
      "Action": "service:Action",
      "Resource": "arn:aws:service:region:account-id:resource-type/resource-id"
    },
    // Additional statements...
  ]
}
```

**Version**: The IAM policy language version. Use "2012-10-17" for the current version.

**Statement**: An *array* of statements that define the permissions. Each statement consists of Effect, Action, and Resource.

**Effect**: Specifies whether the statement allows or denies access. It can be "Allow" or "Deny".

**Action**: The specific AWS service action or a wildcard (*) to represent all actions.

**Resource**: The Amazon Resource Name (ARN) of the resource to which the policy applies. It can also be a wildcard (*) to represent all resources.

**Example IAM Policy**:
Here's a simple example that allows read-only access to Amazon S3:


```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

This policy allows the s3:GetObject action on objects within the specified S3 bucket.

**Wildcards**:
   You can use wildcards (*) for Action, Resource, or both to represent all actions or resources. For example:

```json

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

- This allows all actions (s3:*) on objects within the specified S3 bucket.

AWS Policy Generator:
   You can use the AWS Policy Generator to visually create IAM policies. It helps you select services, actions, and resources and generates the corresponding JSON policy.

IAM Best Practices:
   Principle of Least Privilege: Assign only the permissions needed to perform specific tasks.

Regularly Review Policies: Periodically review and audit your policies to ensure they align with your security requirements.

Use AWS Managed Policies: Whenever possible, use AWS Managed Policies to leverage predefined sets of permissions.

Remember to thoroughly understand the AWS service actions, resource types, and ARN formats for accurate policy definitions. Always test your policies in a controlled environment before applying them to production resources.






