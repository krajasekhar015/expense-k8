# Horizontal Pod Autoscaling

- Scaling is of two types. They are:
    1. Horizontal Scaling
    2. Vertical Scaling

- Horizontal Scaling and Vertical Scaling are two approaches to increasing the capacity or performance of a system, typically used in the context of servers or cloud infrastructure. Both aim to handle increased load but do so in different ways.

- Suppose consider there is a building with ground floor and first floor. Due to increase in population we need to build four floors which is called vertical scaling. Otherwise build four individual buildings separetly which is called horizontal scaling.

- Suppose, the old house gets any problem in the basement, then the whole house will be collapsed. 

**1. Horizontal Scaling**
Horizontal scaling is where we create multiple servers based on the traffic with zero downtime

- There is no single point of failure in horizontal scaling

**2. Vertical Scaling**
Vertical scaling is where we can increase the number of resources (such as CPU, RAM, or storage) in the same server

- There is downtime since there is only single machine (Stop the server then increase resources and then restart)

Suppose our application is running and traffic increases on application then we need to increase number of pods.

- In resource utilization, containers have an advantage of consuming resources dynamically. It also has a disadvantage of consuming all the server resources if anything goes wrong. So, we have discusssed about resource section (requests & limits) in docker

- If we don't set resource utilization, then we cannot measure CPU utilization.

**Summary**
|     Aspect      |                           Horizontal Scaling	                         |               Vertical Scaling                               |
|-----------------|--------------------------------------------------------------------------|--------------------------------------------------------------|
|Definition	      | Adding more instances (nodes) to distribute the load	                 | Increasing the resources of an existing instance             |
|How it works	  | Scale-out (more servers) or scale-in (fewer servers)	                 | Scale-up (more resources on one server)                      |
|Scalability	  | Highly scalable, easy to add/remove instances	                         | Limited by the maximum size of the machine                   |
|Cost Efficiency  |	Cost-effective, especially for growing workloads	                     | Potentially more expensive, especially for |large instances  |
|Fault Tolerance  |	Better, since multiple instances can handle failure	                     | Poorer, since it’s a single point of failure                 |
|Complexity	      | More complex, requires load balancing and managing distributed resources | Simpler to manage, less overhead                             |

 
 Before setting horizontal pod autoscaling, there are two conditions:
 * We should have metrics server installed 
 * We should mention resource section inside pod

- If we give `top` command, we can see which process is consuming more resources like CPU, Memory
- If we want to know which pod is consuming more CPU & memory, then use the command 
```
kubectl top pods
```
- Before applying this command, we need to install metrics server.

## Installing Metrics Server

- Go to the following location
```
https://github.com/kubernetes-sigs/metrics-server
```
- Run the following command
```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```


