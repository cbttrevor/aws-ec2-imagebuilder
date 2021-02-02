## Learning Objectives

* EC2 Image Builder utilizes two separate Identity & Access Management (IAM) roles
* The **EC2 Image Builder Service-Linked Role (SLR)** is used to grant permissions for your AWS account, to the EC2 Image Builder service itself.
* The **EC2 Instance Profile** role is used to grant the builder EC2 instance access to configuration resources in your account (ie. Amazon S3 Bucket), write logs, etc.
  * EC2 Instance Profile must have access to AWS Systems Manager (SSM) APIs
  * Systems Manager was originally marketed as Simple Systems Manager (SSM), but no longer goes by that name
* While the EC2 Instance Profile is an optional setting on EC2 instances, it is required when using EC2 Image Builder.

### References

* [How EC2 Image Builder works with IAM](https://docs.aws.amazon.com/imagebuilder/latest/userguide/security_iam_service-with-iam.html)