## Learning Objectives

* Test phase is executed after the image is taken from the build phase.
* Let's create a Build Component that installs a software package, like Nginx or PowerShell
* We'll also create a test component to ensure that our resulting image matches our expectations
* There are a handful of supported "action modules" that can be invoked in a build or test component
  * PowerShell action module is only supported on the Windows platform, according to the AWS documentation
* Each component is versioned. After a new version is created, the reference must be updated in any recipes pointing to it
  * There is no "Edit" option because a version is idempotent
* Default timeout for each step is 7200 seconds (120 minutes).
  * IMPORTANT: I highly recommend reducing this to something more realistic, so that you fail fast.

### References

* [EC2 Image Builder - Components](https://docs.aws.amazon.com/imagebuilder/latest/userguide/manage-components.html)
* [EC2 Image Builder - Component Document Structure](https://docs.aws.amazon.com/imagebuilder/latest/userguide/image-builder-application-documents.html)
* [EC2 Image Builder - Action Modules](https://docs.aws.amazon.com/imagebuilder/latest/userguide/image-builder-action-modules.html#image-builder-action-modules-general-execution)