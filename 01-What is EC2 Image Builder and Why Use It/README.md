## Learning Objectives

### OS and Container Image Objectives

* Keep software packages up-to-date
* Reduce deployment times
* Repeatable builds
* Provide a consistent foundation for development teams to build on top of

### Pain Points

* Build custom container and operating system (Linux, Windows) images without writing custom code
* Need to replicate OS and container images across all AWS regions and entire AWS account hierarchy
* Lack of automated testing limits ability for operations teams to confirm ready for production

### What does EC2 Image Builder do?

* Create repeatable pipelines that installs software packages, updates operating system patches, apply configuration files, and test it
* Provides a generic, automated, and extensible testing phase that enables operations teams to develop their own image tests
* Graphical interface to create OS and container image build automation tasks
* Revision control for build components and automated tests can trigger a fresh build to occur
* Deploys EC2 instances in your AWS account, runs the build/test pipeline, then creates an Amazon Machine Image (AMI)

### Similar Tools

* How have people achieved automated image builds in the past?
  * [Hashicorp Packer](https://www.packer.io/) is an open source tool to automate image builds
* Microsoft developed System Center Configuration Manager (SCCM), to automate enterprise Windows builds
  * Dynamic task sequences allow automation of driver packages, software packages, patching