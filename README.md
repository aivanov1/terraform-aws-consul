# Consul AWS Blueprint

This repo contains a Blueprint for how to deploy a [Consul](https://www.consul.io/) cluster on 
[AWS](https://aws.amazon.com/) using [Terraform](https://www.terraform.io/). Consul is a distributed, highly-available 
tool that you can use for service discovery and key/value storage. 

This Blueprint includes:

* [install-consul](/modules/install-consul): This module can be used to install Consul. It can be used in a 
  [Packer](https://www.packer.io/) template to create a Consul 
  [Amazon Machine Image (AMI)](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html).
* [consul-cluster](/modules/consul-cluster): Terraform code to deploy a Consul AMI across an [Auto Scaling 
  Group](https://aws.amazon.com/autoscaling/). 



## What's a Blueprint?

A Blueprint is a canonical, reusable, best-practices definition for how to run a single piece of infrastructure, such 
as a database or server cluster. Each Blueprint is created primarily using [Terraform](https://www.terraform.io/), 
includes automated tests, examples, and documentation, and is maintained both by the open source community and 
companies that provide commercial support. 

Instead of having to figure out the details of how to run a piece of infrastructure from scratch, you can reuse 
existing code that has been proven in production. And instead of maintaining all that infrastructure code yourself, 
you can leverage the work of the Blueprint community and maintainers, and pick up infrastructure improvements through
a version number bump.
 
 
 
## Who maintains this Blueprint?

This Blueprint is maintained by [Gruntwork](http://www.gruntwork.io/). If you need help or support, send an email to 
[blueprints@gruntwork.io](mailto:blueprints@gruntwork.io?Subject=Consul%20Blueprint). Gruntwork can help with:

* Blueprints for other types of infrastructure, such as VPCs, Docker clusters, databases, and continuous integration.
* Blueprints that meet compliance requirements, such as HIPAA.
* Consulting & Training on AWS, Terraform, and DevOps.



## How do you use this Blueprint?

Each Blueprint has the following folder structure:

* [modules](/modules): This folder contains the reusable code for this Blueprint, broken down into one or more modules.
* [examples](/examples): This folder contains examples of how to use the modules.
* [test](/test): Automated tests for the modules and examples.

The basic idea for using this Blueprint is to:

1. Use the scripts from the [install-consul](/modules/install-consul) in a Packer template to create a Consul AMI.
1. Deploy that AMI using the [consul-cluster](/modules/consul-cluster) module.

Click on each of the modules above for more details.



## How do I contribute to this Blueprint?

Contributions are very welcome! Check out the [Contribution Guidelines](/CONTRIBUTING.md) for instructions.



## How is this Blueprint versioned?

This Blueprint follows the principles of [Semantic Versioning](http://semver.org/). You can find each new release, 
along with the changelog, in the [Releases Page](../../releases). 

During initial development, the major version will be 0 (e.g., `0.x.y`), which indicates the code does not yet have a 
stable API. Once we hit `1.0.0`, we will make every effort to maintain a backwards compatible API and use the MAJOR, 
MINOR, and PATCH versions on each release to indicate any incompatibilities. 



## License

This code is released under the Apache 2.0 License. Please see [LICENSE](/LICENSE) and [NOTICE](/NOTICE) for more 
details.

