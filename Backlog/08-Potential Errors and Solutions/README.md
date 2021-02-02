## Learning Objectives

Let's review some common errors you might come across and how to resolve them.

### Running Pipeline Fails with 

While running a pipeline, you might receive an error message similar to the following.

> No subnets found for the default VPC 'vpc-11ea4a75'. Please specify a subnet.

#### Resolution

To resolve this error, make sure that you have an Amazon Virtual Private Cloud (VPC) defined in the same region as your EC2 Image Builder pipeline.

### Creating a Build Component Fails

When creating a build component in the AWS Management Console, you might receive the following error when you click the Create button.
```
Failed to create component 
Error message: InvalidParameterValueException: The value supplied for parameter 'data' is not valid. Invalid step name 'Install PowerShell' in phase 'build'. Allowed characters are combinations of numbers [0-9], english letters [a-z,A-Z] and special characters [-_].
```

#### Resolution

In your YAML document for the build component, make sure that the `name` property of each `step` does not have any spaces or unsupported characters in it.

### Timedout Error

After a while, your build might fail with the following message.

> SSM execution 'zzzzzzzzzzz' failed with status = 'TimedOut' in state = 'BUILDING' and failure message = 'Step timed out while step is verifying the SSM Agent availability on the target instance(s). SSM Agent on Instances: [i-zzzzzzzzzzzzz] are not functioning. Please refer to Automation Service Troubleshooting Guide for more diagnosis details.'

#### Cause

The EC2 instance profile that is associated with your Amazon EC2 instance does not have the necessary permissions to access AWS Systems Manager APIs. 

#### Solution

Add the permissions for the EC2 Instance Profile IAM role to access the Systems Manager service. There is a managed AWS IAM policy for this purpose named ``.

### Opening Recipe Results in Error

When you open a recipe in the AWS Management Console, you receive an error message similar to the following.

> Failed to get list of components. Error message: The following required resource 'Component' cannot be found: 'arn:aws:imagebuilder:us-west-2:665453315198:component/asdf/x.x.x'.

#### Cause

This behavior occurs when a build or test component that is referenced by a recipe has been deleted or is inaccessible by IAM policy.

#### Solution

There are several possible solutions for this problem:

1. Re-create the component with the same name and version, that is currently referenced by the recipe
1. Ensure that your IAM credentials, that you're using to log into the AWS Management Console, have access to the component that is inaccessible
1. Create a new version of the recipe that does not have a reference to the component that has been deleted, or is inaccessible