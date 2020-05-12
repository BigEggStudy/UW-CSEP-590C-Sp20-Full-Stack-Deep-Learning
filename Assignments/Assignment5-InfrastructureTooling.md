# Assignment 5: Infrastructure & Tooling

## Q1 Docker
What is the most meaningful difference between a Docker container and a Virtual Machine?

> From the operation system angle:
> * Docker is container based technology and containers are just user space of the operating system.
> * On the other hand, a Virtual Machine is not based on container technology. It is use both user space and kernel space of an operating system.
>
> So you can use Docker to isolate individual applications, and use Virtual Machines to isolate entire systems.
>
> The benefits of Virtual Machine have:
> * All OS resources available to apps
> * Established management tools
> * Established security tools
> * Better known security controls
>
> The benefits of Dockers have:
> * Reduced IT management resources
> * Reduced size of snapshots
> * Quicker spinning up apps
> * Reduced & simplified security updates
> * Less code to transfer, migrate, upload workloads
>
> And compare them with table we can have
>
> Virtual Machine | Dockers
> --- | ---
> Heavyweight | Lightweight
> Limited performance | Native performance
> Each VM runs in its own OS | All containers share the host OS
> Hardware-level virtualization | OS virtualization
> Startup time in minutes | Startup time in milliseconds
> Allocates required memory | Requires less memory space
> Fully isolated and hence more secure | Process-level isolation, possibly less secure

## Q2 Hardware for training
List a couple of potential pro's and a couple of potential con's for owning your own hardware for training, vs using cloud instances.

> Using cloud Instances have the following pros:
> * Easy for setup the environment and hardware
> * Cloud provider have there SLAs to do the maintenance so you don't need to take care much of the DevOps works, especially when you already have the rest of the infrastructure is in the cloud.
> * When you meet with the data protection regulation, and you are not in that region, you can use cloud provider to keep the data and machine at that place to meet the regulation.
> * When handle the BCDR scenario, most of the cloud provider have a easier way to do the failover and fallback.
>
> Owning hardware have the following pros:
> * Higher security of data and model, because they never leave that machines.
> * You can build what ever machine you like that the cloud provider might not have corresponding SKUs.
> * The price will be cheaper for building you own machine.
> * You can maintain the version and anything in your machine.

## Q3 Running training on a cluster
What are some approaches to running training on a cluster of GPU machines? What are their pros/cons?

## Q4 Your experience
What is your experience, if any, with tooling and/or infrastructure for machine learning?
