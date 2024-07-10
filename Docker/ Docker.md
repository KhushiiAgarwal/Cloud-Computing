

**Problem statement: Docker installation & build a image from docker hub.**

1. **Install Docker from <https://docs.docker.com/desktop/install/windows-install/>** 

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.001.png)

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.002.png)![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.003.png)

1. **Create a new image Hello World**

- Run on cmd prompt: *docker run hello-world*

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.004.png)

- Hello.c image is downloaded from: <https://github.com/docker-library/hello-world> for the source code of the hello binary included in this image

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.005.png)

- *Docker ps*
- *Docker ps-a* : This command displays all images including exited running ones

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.006.png)


1. **Create an image & containerize it**
- Open cmd and paste
- *docker container create -i -t --name mycontainer hello-world*
- *docker container start --attach -i mycontainer*
- *docker pull hello-world*

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.007.png)

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.008.png)

1. ` `**Remove docker image**
- `*Docker image rm hello-world*`
- If image is running `*docker image rm hello-world -f`*

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.009.png)

1. **Create an additional application (Python Data visualization)**

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.010.png)

- Create a simple python app

  *import numpy as np*

  *import matplotlib.pyplot as pl*

  *x=np.arange(10)*

  *y=x\*\*2*

  *print(“This is the squaring function”)*

  *print(x,y)*

  *pl.plot(x,y)*

  *pl.title('Squaring Function')*

  *pl.xlabel('Numerical')*

  *pl.ylabel('Square')*

  *pl.show()*

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.011.png)

- Create a docker file and ensure to include RUN pip install ~library-name~

*FROM python*

*WORKDIR /app*

*COPY . /app*

*RUN pip install numpy matplotlib*

*CMD ["python", "app.py"]*

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.012.png)

- Now open an integrated terminal by selecting the file from the opened folder. Right click and select open in integrated terminal.
- Type `*docker build -t pythonapp .*`  or any other image name used for creation
- ` *docker run -it pythonapp*` 


  ![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.013.png)


![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.014.png)

- Go to docker and run the file 
- In cmd check all docker images 

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.015.png)

- ` `After using docker images, remove the files using `docker image rm python -f`

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.016.png)

**What is Docker?**

- Docker is a software platform that allows you to build, test, and deploy applications quickly. Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime. Using Docker, you can quickly deploy and scale applications into any environment and know your code will run.

- Docker is written in the Go programming language and takes advantage of several features of the Linux kernel to deliver its functionality. Docker uses a technology called namespaces to provide the isolated workspace called the container. When you run a container, Docker creates a set of namespaces for that container.


![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.017.png)

**Docker Architecture**

- Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers. The Docker client and daemon can run on the same system, or you can connect a Docker client to a remote Docker daemon. The Docker client and daemon communicate using a REST API, over UNIX sockets or a network interface. Another Docker client is Docker Compose, that lets you work with applications consisting of a set of containers.

- ***Docker daemon:*** daemon (dockerd) listens for Docker API requests and manages Docker objects such as images, containers, networks, and volumes. A daemon can also communicate with other daemons to manage Docker services.

- ***Docker client***: is the primary way that many Docker users interact with Docker. When you use commands such as docker run, the client sends these commands to dockerd, which carries them out. The docker command uses the Docker API. The Docker client can communicate with more than one daemon.

- ***Docker registries:*** stores Docker images. Docker Hub is a public registry that anyone can use, and Docker looks for images on Docker Hub by default. You can even run your own private registry.
  **



  **What is Docker Image?**

- Docker images are read-only templates that contain instructions for creating a container. 

- Docker image is a snapshot or blueprint of the libraries and dependencies required inside a container for an application to run

- An image is composed of multiple stacked layers, like layers in a photo editor, each changing something in the environment. Images contain the code or binary, runtimes, dependencies, and other filesystem objects to run an application. The image relies on the host operating system (OS) kernel.

- Docker images are immutable, so you cannot change them once they are created. If you need to change something, create another container with your changes, then save those as another image. Or, just run your new container using an existing image as a base and change that one.

  ![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.018.png)

  **What are Docker containers?**

- A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another.

- When a Docker user runs an image, it becomes one or multiple container instances. The container’s initial state can be whatever the developer wants — it might have an installed and configured web server, or nothing but a bash shell running as root. In practice, though, most images include some preconfigured software and configuration files.

- A container is an isolated place where an application runs without affecting the rest of the system and without the system impacting the application. Because they are isolated, containers are well-suited for securely running software like databases or web applications that need access to sensitive resources without giving access to every user on the system.

![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.019.png)

**What are Docker containers images?**

- A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

- Container images become containers at runtime and in the case of Docker containers – images become containers when they run on Docker Engine.


![](Aspose.Words.e79ac0bb-be5b-4022-beb9-9855eddfebe6.020.png)

**Why use Docker?**

- It guarantees that if a feature functions in the development environment, it will also work in the production and staging environments. Docker eliminates friction between the two teams and eases the work of automating steps such as testing, staging, and deployment.

- Docker works by providing a standard way to run your code. Docker is an operating system for containers. Similar to how a virtual machine virtualizes (removes the need to directly manage) server hardware, containers virtualize the operating system of a server. Docker is installed on each server and provides simple commands you can use to build, start, or stop containers.

- Use Docker containers as a core building block creating modern applications and platforms. Docker makes it easy to build and run distributed microservices architectures, deploy your code with standardized continuous integration and delivery pipelines, build highly-scalable data processing systems, and create fully-managed platforms for your developers

- Docker streamlines the development lifecycle by allowing developers to work in standardized environments using local containers which provide your applications and services. Containers are great for continuous integration and continuous delivery (CI/CD) workflows.


**Why use containers?**

- Containers are an abstraction at the app layer that packages code and dependencies together. Multiple containers can run on the same machine and share the OS kernel with other containers, each running as isolated processes in user space. Containers take up less space than VMs (container images are typically tens of MBs in size), can handle more applications and require fewer VMs and Operating systems.
