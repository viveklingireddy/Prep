## S3 Simple Storage Service 

[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) is a scalable and highly durable cloud storage service provided by Amazon Web Services (AWS). It's designed to store and retrieve any amount of data from anywhere on the web, offering industry-leading scalability, availability, security, and performance.

Key features of Amazon S3 include:

1. **Scalability:** Amazon S3 is designed to scale infinitely, allowing you to store and retrieve any amount of data without worrying about capacity constraints.

2. **Durability and Availability:** S3 offers high durability, with data stored redundantly across multiple facilities and availability zones within an AWS Region, making it highly available and resilient to failures.

3. **Security:** It provides robust security features, including encryption, access control, and bucket policies, allowing you to control access to your data and secure it against unauthorized access.

4. **Various Storage Classes:** Amazon S3 offers multiple storage classes with different performance and pricing characteristics, such as S3 Standard, S3 Intelligent-Tiering, S3 Glacier, S3 Glacier Deep Archive, etc., enabling you to choose the most cost-effective storage class based on your needs.

5. **Lifecycle Management:** S3 allows you to manage the lifecycle of your objects by automatically transitioning them between storage classes or deleting them based on predefined rules, helping to optimize costs.

6. **Versioning and Replication:** Versioning enables you to keep multiple variants of an object in the same bucket, while replication allows you to replicate data across different regions for disaster recovery or compliance needs.

7. **Integration and Compatibility:** It integrates seamlessly with various AWS services, making it a versatile storage solution for various applications and workloads. Additionally, it's compatible with many third-party tools and applications.

Amazon S3 serves a wide range of use cases, including data storage for websites, mobile applications, backups, big data analytics, content distribution, and more.

S3 Everything is stored as an object, you can upload anything files/images/videos etc. limit is 5TB for every object. It can be accessible from anywhere. we can define the acsess to public. 
We can set the IAM policies for buckets, to allow users, specific access etc.  
In S3, data is stored in buckets. These S3/ buckets are 99.99999999 % durable , scalable, provides built in encryption and highly available.
Organizations store larger data sets on S3  
We can host static websites on s3 called static web hoisting

- Newly Directories buckets and new storage type openzone is addedd features.

### How to Create a bucket 

*Buckets naming shouldn't have underscores, camelcase, caps*, Should be 3-63 char.
With theory 
[How to create a bucket in console, cli](https://docs.aws.amazon.com/AmazonS3/latest/userguide/create-bucket-overview.html)

without theory direct steps 
[Direct steps to create bucket in console](https://docs.aws.amazon.com/AmazonS3/latest/userguide/creating-bucket.html)

Bucket Names must be unique across all the AWS accounts, for Naming the Buckets pls read [Buckets Nomenclature](https://docs.aws.amazon.com/AmazonS3/latest/userguide/creating-bucket.html)


You can access the objects with hostname or through S3 Accesspoints [s3accesspoints](https://aws.amazon.com/s3/features/access-points/)  

- Amazon S3 Access Points, a feature of S3, simplify data access for any AWS service or customer application that stores data in S3. With S3 Access Points, customers can create unique access control policies for each access point to easily control access to shared datasets. *Customers with shared datasets including data lakes, media archives, and user-generated content can easily scale access for hundreds of applications by creating individualized access points with names and permissions customized for each application. Any access point can be restricted to a Virtual Private Cloud (VPC) to firewall S3 data access within customers’ private networks, and AWS Service Control Policies can be used to ensure all access points are VPC restricted*. S3 Access Points are available in all regions at no additional cost.

[Documentation of access points use cases](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points-usage-examples.html)

- Getting started with S3 Access Points
You can start creating access points, at no additional cost, on new buckets as well as your existing buckets through the AWS Management Console, the AWS Command Line Interface (CLI), the Application Programming Interface (API), and the AWS Software Development Kit (SDK) client. You can easily add, view, and delete access points as well as edit access point policies through the S3 console and the CLI. You can write an access point policies just like a bucket policy, using IAM rules to govern permissions.

You will also be able to use CloudFormation templates to get started with access points. You can monitor and audit access point operations such as “create access point” and “delete access point” through AWS CloudTrail logs. You can control access point usage using AWS Organizations support for AWS SCPs.

- **S3 Object Ownership** is an Amazon S3 bucket-level setting that you can use both to *control ownership of objects* that are uploaded to your bucket and to *disable or enable access control lists (ACLs)*. By default, Object Ownership is set to the Bucket owner enforced setting, and all ACLs are disabled. With ACLs disabled, the bucket owner owns every object in the bucket and manages access to data exclusively by using policies.

- **Server-side encryption** with Amazon S3 managed keys (SSE-S3) is the base level of encryption configuration for every bucket in Amazon S3. *All new objects uploaded to an S3 bucket are automatically encrypted with SSE-S3 as the base level of encryption setting*. If you want to use a different type of default encryption, you can also specify server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS) or customer-provided keys (SSE-C) to encrypt your data. [For more information, see Setting default server-side encryption behavior for Amazon S3 buckets](https://docs.aws.amazon.com/AmazonS3/latest/userguide/bucket-encryption.html).

- ### How to use access points through CLI  
 Clear explaination please read don't miss
 [Aws Access Points creation](https://docs.aws.amazon.com/AmazonS3/latest/userguide/using-access-points.html)

- Access through AWS MANAGEMENT CONSOLE
[Access point through Console ](https://docs.aws.amazon.com/AmazonS3/latest/userguide/access-points-manage.html)
- bucket policy for static webhoisting enabled 


```{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::viveklingireddy/*"
        }
    ]
}```

