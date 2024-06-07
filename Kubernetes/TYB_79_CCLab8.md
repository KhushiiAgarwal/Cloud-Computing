Name : Khushi Agarwal

Roll no:-79

Division: TY-CS-B

**Problem statement Lab 8:** **Deploy a stateless/stateful application on Kubernetes cluster.**

- **Use kubectl to build and manipulate GKE clusters**
- **Use kubectl and configuration files to deploy Pods**
- **Use Container Registry to store and deploy containers**

<a name="_hlk162892018"></a>**Step 1: 1. Deploy GKE clusters**

- Use Cloud Shell to deploy GKE clusters.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.001.png)

*export my\_region=Region*

*export my\_cluster=autopilot-cluster-1*

- Create a Kubernetes cluster:

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.002.png)

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.003.png)

*gcloud container clusters create-auto $my\_cluster --region $my\_region*

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.004.png)

After running for about 5-10mins we see cluster is created with kubeconfig details.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.005.png)

When deployment is complete, the Google Cloud console Kubernetes Engine > Clusters page



**Step2. Connect to a GKE cluster** 

To create a kubeconfig file with the credentials of the current user (to allow authentication) and provide the endpoint details for a specific cluster (to allow communicating with that cluster through the kubectl command-line tool)

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.006.png)

*gcloud container clusters get-credentials $my\_cluster --region $my\_region*

This command creates a .kube directory in your home directory if it doesn't already exist. In the .kube directory, the command creates a file named config if it doesn't already exist, which is used to store the authentication and configuration information. The config file is typically called the kubeconfig file.

*nano ~/.kube/config* 

Press CTRL+X to exit the nano editor.

The kubeconfig file can contain information for many clusters. The currently active context (the cluster that kubectl commands manipulate) is indicated by the current-context property

**Step 3. Use kubectl to inspect a GKE cluster**

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.007.png)

*kubectl config view*

The sensitive certificate data is replaced with DATA+OMITTED.

After the kubeconfig file is populated and the active context is set to a particular cluster, you can use the kubectl command-line tool to execute commands against the cluster. Most such commands ultimately trigger a REST API call against the master API server, which triggers the associated action.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.008.png)

*kubectl cluster-info*


![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.009.png)

*kubectl config current-context*

*kubectl config get-contexts*

Several lines of output indicate details about the cluster you created and indicate which is the active context cluster. In general, this command lists some details of the clusters present in the user's kubeconfig file, including any other clusters that were created by the user as well as any manually added to the kubeconfig file.

![ref1]

*kubectl config use-context gke\_${DEVSHELL\_PROJECT\_ID}\_Region\_autopilot-cluster-1* 

*kubectl create deployment --image nginx nginx-1*

*kubectl get pods*

*kubectl top nodes*

**Step 4. Deploy Pods to GKE clusters**

Kubernetes introduces the abstraction of a Pod to group one or more related containers as a single entity to be scheduled and deployed as a unit on the same node. You can deploy a Pod that is a single container from a single container image. Or a Pod can contain many containers from many container images. 

![ref2]

*kubectl create deployment --image nginx nginx-1*

*kubectl get pods*

![ref3]export my\_nginx\_pod=[your\_pod\_name]

echo $my\_nginx\_pod

![ref4]

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.014.png)![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.015.png)

*kubectl describe pod $my\_nginx\_pod*	

Details of the Pod, as well as its status and conditions and the events in its lifecycle, are displayed.

To be able to serve static content through the nginx web server, you must create and place a file into the container.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.016.png)

*nano ~/test.html*

Add the following text (shell script) to the empty test.html file: *This is title  Hello world*

Press CTRL+X, then press Y and enter to save the file and exit the nano editor.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.017.png)

*kubectl cp ~/test.html $my\_nginx\_pod:/usr/share/nginx/html/test.html*

This command copies the test.html file from the local home directory to the /usr/share/nginx/html directory of the first container in the nginx Pod. You can specify other containers in a multi-container Pod by using the -c option, followed by the name of the container.

*kubectl expose pod $my\_nginx\_pod --port 80 --type LoadBalancer*

A service is required to expose a Pod to clients outside the cluster. Services are discussed elsewhere in the course and used extensively in other labs.

This command creates a LoadBalancer service, which allows the nginx Pod to be accessed from internet addresses outside of the cluster.


![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.018.png)

*kubectl get services*

The Kubernetes service is one of the default services created or used by the cluster. The nginx service that you created is also displayed.You may need to re-run this command several times before the external IP address is displayed.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.019.png)

*curl [http://\[EXTERNAL_IP\]/test.html*](http://[EXTERNAL_IP]/test.html)*

*kubectl top pods*

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.020.png)

<a name="_hlk162892437"></a>**What is Kubernetes?**

<a name="_hlk162892123"></a>Kubernetes, also known as K8s, is an open-source system for automating deployment, scaling, and management of containerized applications. It groups containers that make up an application into logical units for easy management and discovery. Kubernetes can help you deliver and manage containerized, legacy, and cloud-native apps, as well as those being refactored into microservices.

Kubernetes, the container-centric management software, has become the de facto standard to deploy and operate containerized applications. Google Cloud is the birthplace of Kubernetes—originally developed at Google and released as open source in 2014. Kubernetes builds on 15 years of running Google's containerized workloads and the valuable contributions from the open source community. Inspired by Google’s internal cluster management system, Borg, Kubernetes makes everything associated with deploying and managing your application easier. Providing automated container orchestration, Kubernetes improves your reliability and reduces the time and resources attributed to daily operations.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.021.png)

Kubernetes gives you the orchestration and management capabilities required to deploy containers, at scale, for these workloads.Kubernetes orchestration allows you to build application services that span multiple containers, schedule those containers across a cluster, scale those containers, and manage the health of those containers over time. With Kubernetes you can take effective steps toward better IT security.

Kubernetes also needs to integrate with networking, storage, security, telemetry, and other services to provide a comprehensive container infrastructure. Linux containers give your microservice-based apps an ideal application deployment unit and self-contained execution environment. And microservices in containers make it easier to orchestrate services, including storage, networking, and security.

This significantly multiplies the number of containers in your environment, and as those containers accumulate, the complexity also grows. Kubernetes fixes a lot of common problems with container proliferation by sorting containers together into "pods." Pods add a layer of abstraction to grouped containers, which helps you schedule workloads and provide necessary services—like networking and storage—to those containers. 

Other parts of Kubernetes help you balance loads across these pods and ensure you have the right number of containers running to support your workloads.

**What is a Kubernetes cluster?**

A working Kubernetes deployment is called a cluster, which is a group of hosts running Linux® containers. You can visualize a Kubernetes cluster as two parts: the control plane and the compute machines, or nodes.

![](Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.022.png)

Each node is its own Linux environment, and could be either a physical or virtual machine. Each node runs pods, which are made up of containers. 

The control plane is responsible for maintaining the desired state of the cluster, such as which applications are running and which container images they use. Compute machines actually run the applications and workloads. The control plane takes commands from an administrator (or DevOps team) and relays those instructions to the compute machines.

This handoff works with a multitude of services to automatically decide which node is best suited for the task. Services decouple work definitions from the pods and automatically get service requests to the right pod—no matter where it moves in the cluster or even if it’s been replaced. It allocates resources and assigns the pods in that node to fulfill the requested work.

Kubernetes runs on top of an operating system and interacts with pods of containers running on the nodes.The desired state of a Kubernetes cluster defines which applications or other workloads should be running, along with which images they use, which resources should be made available to them, and other such configuration details.

There is little change to how you manage containers using this type of infrastructure. Your involvement just happens at a higher level, giving you better control without the need to micromanage each separate container or node. 

Where you run Kubernetes is up to you. This can be on bare metal servers, virtual machines (VMs), public cloud providers, private clouds, and hybrid cloud environments. One of Kubernetes’ key advantages is it works on many different kinds of infrastructure

` `**Kubernetes Features**

- **Automated rollouts and rollbacks:** Kubernetes progressively rolls out changes to your application or its configuration, while monitoring application health to ensure it doesn't kill all your instances at the same time. If something goes wrong, Kubernetes will rollback the change for you. Take advantage of a growing ecosystem of deployment solutions.

- **Service discovery and load balancing:** No need to modify your application to use an unfamiliar service discovery mechanism. Kubernetes gives Pods their own IP addresses and a single DNS name for a set of Pods, and can load-balance across them.

- **Storage orchestration**: Automatically mount the storage system of your choice, whether from local storage, a public cloud provider, or a network storage system such as iSCSI or NFS.

- **Self-healing**: Restarts containers that fail, replaces and reschedules containers when nodes die, kills containers that don't respond to your user-defined health check, and doesn't advertise them to clients until they are ready to serve.

- **Secret and configuration management:** Deploy and update Secrets and application configuration without rebuilding your image and without exposing Secrets in your stack configuration.

- **Automatic bin packing:** Automatically places containers based on their resource requirements and other constraints, while not sacrificing availability. Mix critical and best-effort workloads in order to drive up utilization and save even more resources.

- **Batch execution:** In addition to services, Kubernetes can manage your batch and CI workloads, replacing containers that fail, if desired.

- **Horizontal scaling:** Scale your application up and down with a simple command, with a UI, or automatically based on CPU usage.

- **IPv4/IPv6 dual-stack:** Allocation of IPv4 and IPv6 addresses to Pods and Services

- **Designed for extensibility:** Add features to your Kubernetes cluster without changing upstream source code.


**Kubernetes vs. Docker**

Docker can be used as a container runtime that Kubernetes orchestrates. When Kubernetes schedules a pod to a node, the kubelet (the service that makes sure each container is running) on that node will instruct Docker to launch the specified containers.

The kubelet then continuously collects the status of those containers from Docker and aggregates that information in the control plane. Docker pulls containers onto that node and starts and stops those containers.

The difference when using Kubernetes with Docker is that an automated system asks Docker to do those things instead of the admin doing so manually on all nodes for all containers.

[ref1]: Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.010.png
[ref2]: Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.011.png
[ref3]: Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.012.png
[ref4]: Aspose.Words.c3e439ee-1e03-4800-ab0f-95e558e1e568.013.png
