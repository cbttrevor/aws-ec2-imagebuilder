## Learning Objectives

* It's usually easier to understand how each piece of the pipeline works, before trying to create one in the master pipeline wizard.

### Recipes

* A recipe contains references to build components and tests
* There are two types of supported recipes: container images and OS images

### Build Components

* Build components can be used to install software packages onto an OS or into a container or apply configurations
* `Description` and `Change Description` (versioned) fields describe the purpose of the build component
* YAML-based configuration document describes the individual `phases` and `steps` of the build component

### Test Components

* Test Components represent validation steps in the image build pipeline
* Test Components are executed on a separate virtual machine that's deployed using the AMI from the build VM

### Distribution Settings

* You can use the Distribution Settings to distribute images to other AWS regions
* You can also distribute images to other AWS accounts

### Pipeline

* The pipeline ties everything else together.
* Pipeline has a schedule (cron), or manual invocation.
