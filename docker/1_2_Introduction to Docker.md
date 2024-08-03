# Introduction to Docker

Welcome to Introduction to Docker. After watching this video you will be able to, 

- define what Docker is, 
- describe the Docker process and underlying technology, 
- list the benefits of Docker containers, and 
- identify the challenges of Docker containers. 

Available since 2013, the official Docker definition paraphrased states that Docker is an open platform for developing, shipping, and running applications as containers. Docker became popular with developers because of its simple architecture, massive scalability, and portability on multiple platforms, environments, and locations. 

Docker **isolates** applications from infrastructure, including the **hardware**, the operating system, and the **container runtime**. 

- Docker is written in the Go programming language. 
- Docker uses Linux kernel's features to deliver its functionality. 
- Docker also uses **namespaces** to provide an isolated workspace called the **container**, and 
- Docker creates a set of namespaces for every container, and each aspect **runs in a separate namespace** with access limited to that namespace. 

## Docker add-ons

Docker methodology has inspired additional innovations, including: 

- **Complementary tools** such as *Docker CLI*, *Docker compose* and *Prometheus*, and various plugins including *storage plugins*. 
- **Orchestration** technologies using *Docker swarm* or *Kubernetes*, and 
- **Development methodologies** using *microservices* and *serverless*. 

## Docker Benefits

Docker offers the following benefits. 

- Docker's **consistent and isolated environments** result in stable application deployments. 
- Deployments occur **in seconds**. 
- Because Docker images are small and reusable, they significantly **speed up** the development process, and 
- Docker **automation** capabilities help eliminate errors, simplifying the maintenance cycle. 
- Docker supports **Agile and CI/CD DevOps** practices. 
- Docker's **easy versioning** speeds up testing, rollbacks, and redeployments. 
- Docker helps **segment applications** for easy refresh, cleanup, and repair. 
- Developers collaborate to **resolve issues faster** and **scale containers** when needed, and 
- Docker images are platform independent, so they are **highly portable**. 

## Challenging use case

Docker is not a good fit for applications with these qualities, 

- require **high performance or security**, are 
- based on **Monolith architecture**, use **rich GUI features**, or 
- perform **standard desktop** or **limited functions**. 

## Recap

In this video, you learned that, 

- Docker is an open platform for developing, shipping, and running applications as containers. 
- Docker speeds up the deployment process across multiple environments. 
- Docker uses namespaces technology to provide an isolated workspace called the container. 
- Docker creates a set of namespaces for every container, and each aspect runs in a separate namespace with access limited to that namespace. 
- Docker supports Agile and CI/CD DevOps practices. And lastly, 
- Docker containers are not a good fit for applications based on monolithic architecture or applications that require high performance security.