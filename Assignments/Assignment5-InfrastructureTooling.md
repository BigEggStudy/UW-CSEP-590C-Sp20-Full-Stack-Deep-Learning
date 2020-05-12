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

> To run the training on a cluster of GPU machines, we normally need a **Parameter Server** to do the summarize the gradient and then distribute the updates for the models. This transfer logic can be either synchronized or asynchronized. In sync training, all workers train over different slices of input data in sync, and aggregating gradients at each step. In async training, all workers are independently training over the input data and updating variables asynchronously. And if there have so many parameters that one parameter server cannot handle, we can split the gradients into multiple shards and sent them to respective parameter server.
>
> If we don't want to use parameter server, there have another approach that is called: Multi-node Ring all-reduce, it will let different machines transfer gradient to it's peer during all-reduce and update the model at the end of all-reduce operation complete in those machines.
>
> The different between use Parameter Servers or Multi-node Ring all-reduce are:
> * Parameter Servers are good for compute intensive workloads. (High arithmetic intensity.) And it's have higher node-to-parameter server communication.
> * Multi-node Ring all-reduce are good for communication
> intensive workloads. (Low arithmetic intensity.) and it's have higher node-to-node communication.
>
> In TensorFlow, the way for using Parameter Service should use: `tf.distribute.experimental.ParameterServerStrategy` as the distribute strategy. And the second one for all-reduce, it should use: `tf.distribute.experimental.MultiWorkerMirroredStrategy`.
>
> The Benefit that use a cluster of GPU machines is: It's hard to get a Machines with 64 or 128 GPU in cloud provider, but by using a cluster, it's easier to get similar compute power by using multiple machines with a fewer GPUs.
>
> But when use a distributed training cluster, some special HPC-style hardware will need to be take into consideration, such as: NVLink, InfiniBand networking, and GPUs that support features like GPU Direct RDMA. And beside that, the Hardware Configuration for the cluster will be more complicates.
>
> Reference:
> * [A Gentle Introduction to Multi GPU and Multi Node Distributed Training](https://lambdalabs.com/blog/introduction-multi-gpu-multi-node-distributed-training-nccl-2-0/)
> * [Distributed training with TensorFlow](https://www.tensorflow.org/guide/distributed_training)

## Q4 Your experience
What is your experience, if any, with tooling and/or infrastructure for machine learning?

> Our team use a machine learning model to summaries the description to generate title. That model was trained and coded by another team (applied science team). For our team, because we provided the data, we can still push updates to the model package that update the featurization. I don't know why, but that team seem like don't like use TensorFlow or PyTorch, but write the neural network by their own use C++. And it's quite slow...
>
> After a re-org, we have the ownership for that model and package, so our team start a work that use a Docker hosted image that contains TensorFlow and BERT instead of the custom model and C++. The performance of the new model increased, the accuracy is higher, model is smaller and faster, and now we even start support multi-lingual.... (I think I know why that team got re-org...)
